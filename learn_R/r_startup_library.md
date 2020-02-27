# R Start-up, Renvirons, Rprofiles, and Library Paths

## Renvirons

What are Renviron files? They are files which specify certain R-specific environment variables. During the R start-up process, R will read in operating system (OS) environment variables (which can be accessed with `Sys.getenv("VAR_NAME")`). Then it will also read in Renviron files for additional environment variables specific to R (these variables can also be accessed with `Sys.getenv()`). As far as I can tell, R treats OS environment variables and environment variables from Renviron files the same.

Renviron files are **plain-text files** meaning they are not R code. Each line takes the form of `name=value`. You can comment out things with `#`.

Finally, there will be **user-level** and **site-level** Renvirons (and Rprofiles and libraries). **User-level** refers to the individual user and how only the individual user starting the given R session will have access to the specified resources. **Site-level** refers to all users across a given site and how all of them will have access to the specific resources (mainly useful for admins who are managing an environment for a group of users).

### Renviron start-up process

1. Was `--no-environ` set on the command line? If so, do not search for site and user files to process environmental variables.
2. If `--no-environ` was not set, check the environment variable `R_ENVIRON` for the path to the site environment file.
    + I assume `R_ENVIRON` has to be an OS environment variable because I'm not sure where else you could set it. I suppose you could set it in `R_HOME/etc/Renviron`, but everywhere I've read says you should not edit that file.
3. If `R_ENVIRON` is unset (which by default it is), go to `R_HOME/etc/Renviron.site` and check for environment variables to set for your R session.
    + Sometimes `Renviron.site` will exist by default and other times it will not. Do no worry either way if it is set up or not.
4. Next check the `R_ENVIRON_USER` environment variable for the path to the user environment file.
    + This can be set either in the site-level environment file (although it wouldn't make much sense to set the same user file for all users), or it can be set using an OS level environment variable (probably the better way to do it).
5. If the `R_ENVIRON_USER` environment variable is unset (which by default it is), then check R's current working directory for a `.Renviron` file. Generally this is where an R project's `.Renviron` file will be pulled in.
6. If R's current working directory does not have a `.Renviron` file, look in the user's home directory, `~/.Renviron`.

### Notes on Renvirons

* You may be asking yourself, "What is this `R_HOME` I keep seeing pop up?" `R_HOME` is an environment variable set by R. It is simply the top-level directory for your R installation or R's *home*. You can find out the `R_HOME` path by typing `Sys.getenv("R_HOME")` in an R session, typing `R.home()` in an R session, or by typing `R RHOME` in the terminal.
* A site-wide file and EITHER an R project or user Renviron can be loaded at the same time. You cannot have a project Renviron and a user Renviron loaded at the same time.
* On Unix/Linux versions of R, there is a file `R_HOME/etc/Renviron` which is read very early in the start-up process. It contains environment variables set by R in the configure process. Values in that file can be overriden in site or user environment files. The Renviron file SHOULD NOT be changed itself.
* What sorts of things do people put in their Renviron files? Generally people put API keys or other sensitive information so they can share code without exposing that sensitive information (anywhere in the code which needs the key you can use `Sys.getenv("API_KEY")`). For other use cases refer to the [links at the bottom of the section](#links-for-better-understanding-rprofiles-and-renvirons).
* The above note should indicate you generally (but not always) do not want to share your Renviron file through something like Github. You can add your Renviron to your `.gitignore` file.
* You should not set-up/use your Renviron file in such a way so as to reduce the portability/reproducibility of your code.

## Rprofiles

After the Renviron files are read and processed, R moves on to processing Rprofiles. What are Rprofiles? Unlike Renvirons, Rprofiles are **R scripts**, and as a result you write R code in them. What kind of R code is usually included in an Rprofile? Sometimes people put fun things in their Rprofiles to customize their R experience. Other times people use them when they're working on a team so everybody is downloading packages from the same repository. Use cases vary, but one can gain a better idea of what Rprofiles are used for by exploring the [links at the bottom of the section](#links-for-better-understanding-rprofiles-and-renvirons).

It's also widely discouraged from adding R code to your Rprofile which would limit the portability/reproducibility of your code (e.g. defining a function which you use again and again across many different projects).

### Rprofile start-up process

1. Was `--no-site-file` set at the command line? If so, do not search for a site-wide Rprofile.
2. If it was not set, check the `R_PROFILE` environment variable for the location of the site-wide Rprofile.
    + You can set this value at the OS level, or in one of your `.Renviron` or `Renviron.site` files. I suppose the benefits of setting this variable at the OS level is it will be easier for non-R processes to access this variable. Alternatively one could set it in an `.Renviron` or `Renviron.site` file to keep all R-related items together. Either way is fine, and it'll work the same no matter how it's set-up.
3. If `R_PROFILE` is unset (which it is by default) check `R_HOME/etc/Rprofile.site`. This file may or may or may not exist by default to start. It is no cause for concern either way.
4. Was `--no-init-file` set at the command line? If so, do not look for a user Rprofile.
5. If it was not set, check the value of the environment variable `R_PROFILE_USER` for the path to the user's Rprofile.
    + Like above for `R_PROFILE`, you can set this at the OS level, or in one of your `.Renviron` or `Renviron.site` files.
6. If R_PROFILE_USER is undefined (by default it is), check R's current working directory for `.Rprofile`. Generally speaking this is where a project's `.Rprofile` will be stored.
7. If no `.Rprofile` is found in R's current working directory, check the user's home directory `~/.Rprofile`.

Similar to Renvirons, a site-wide Rprofile and EITHER an R project Rprofile or user Rprofile can be loaded at the same time. You cannot have a project Rprofile and a user Rprofile loaded at the same time.

## Links for better understanding Rprofiles and Renvirons

* [Offical documentation from R concerning its startup process concerning Rprofiles and Renvirons](https://stat.ethz.ch/R-manual/R-devel/library/base/html/Startup.html)
* [Excerpt from the *Efficient R Programming* book concerning Rprofiles and Renvirons](https://csgillespie.github.io/efficientR/set-up.html#r-startup)
    + Here is an [additional excerpt](book.https://csgillespie.github.io/efficientR/3-3-r-startup.html#r-startup) from an older (potentially newer?) version of the book.
* [Deeper dive on Rprofiles and Renvirons provided by RStudio](https://rviews.rstudio.com/2017/04/19/r-for-enterprise-understanding-r-s-startup/). It goes into some interesting use cases for Rprofiles and Renvirons.
* [Excerpt from the *What They Forgot To Teach You About R* Book concerning Rprofiles and Renvirons](https://rstats.wtf/r-startup.html). It has a very useful (although intimidiating at first glance) diagram of R's startup process.
* [For the curious who are interested in using environment variables in the OS](https://devconnected.com/how-to-set-and-unset-environment-variables-on-linux/)
* [Useful list of environment variables which affect R](https://stat.ethz.ch/R-manual/R-devel/library/base/html/EnvVar.html)

## Libraries
What is a library? In the words of [Hadley Wickham](http://r-pkgs.had.co.nz/package.html), a library is simply a directory containing installed packages (side-note this link is very useful, in general, because it gives a very good overview of packages and the different types of packages).

Why should you be concerned with libraries? The power of R largely comes from its extensibility through packages. Managing your libraries is important then to ensure all of your packages play nice together which ensures your code works.

### Where are my packages currently being stored?

* The **library search path** (or where R looks for your installed packages) is initialized at start-up from a variety of different sources each taking a different priority. This means if one happens to have multiple versions of an R package installed, libraries with higher priority will have their version of the package loaded.
    1. The library paths specified by the environment variable `R_LIBS` take the highest precedence. The use case for this environment variable is a bit unclear to me. It seems as if the most appropriate use case is if there are shared libraries you want to take precedence over individuals' libraries.
    2. The library paths specified by the environment variable `R_LIBS_USER` is the next highest. This should point to a user's respective libraries.
    3. The library paths specified by `R_LIBS_SITE` are next highest in terms of priority. This should point to a set of shared libraries. One can access the value for `R_LIBS_SITE` by typing `.Library.site` in an R session.
    4. Last in terms of priority is the path returned by `.Library` which is the *library* subdirectory of R_HOME. Generally speaking this is where the default R packages (came in the initial R download and installation) are kept.
* All of the environment variables should be a colon-separated list of directories. All the directories must be valid otherwise R silently ignores them.
* To see your library search path, you can use the `.libPaths()` function in an R session. When you don't provide any arguments, it will provide the current library search path in order of descending priority. #################### what about new?
 
 
 
* .Library.site is a (possibly empty) character vector giving the location(s) of the site library(ies), the "site-library" subdirectory of R_HOME.
    + On some linux systems, there are a bunch of site libraries which can cause a lot of confusion:
        + /usr/lib/R/library is for the core R packages which are installed using apt when downloading/installing R itself.
        + /usr/lib/R/site-library is for R packages installed using using the OS package manager (yum, apt, etc.).
        + /usr/local/lib/R/site-library is for R packages installed using R.
* By default, R_LIBS is unset and R_LIBS_USER is set to directory `R/R.version$platform-library/x.y`.
* .Library.site can be set via the environment variable R_LIBS_SITE (non-empty colon-separated list of library trees).

* R_LIBS_USER
    + intended to list libraries for a single user, doesn't affect other users.
* R_LIBS_SITE
    + Intended to list libraries shared by multiple users.
* libPaths()
    + Shows libraries in the search paths.
* R_LIBS
    + Environment variable to be read at start-up. Not entirely sure what the purpose is.

* Only 1 version of each R package can be installed and accessed in a library at a time.
* An R library is tied to a specific version of R.
* R can search through multiple libraries, and libraries can be shared across projects and users.

## Links
* https://community.rstudio.com/t/help-regarding-package-installation-renviron-rprofile-r-libs-r-libs-site-and-r-libs-user-oh-my/13888
* http://www.quintuitive.com/2018/03/31/package-paths-r/
* https://stat.ethz.ch/R-manual/R-devel/library/base/html/libPaths.html
* https://stat.ethz.ch/pipermail/r-help/2003-October/041178.html
* https://environments.rstudio.com/libraries.html