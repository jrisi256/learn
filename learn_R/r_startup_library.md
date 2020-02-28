# Renvirons, Rprofiles, and Libraries

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
* On Unix/GNU-Linux versions of R, there is a file `R_HOME/etc/Renviron` which is read very early in the start-up process. It contains environment variables set by R in the configure process. Values in that file can be overridden in site or user environment files. The Renviron file SHOULD NOT be changed itself.
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
6. If `R_PROFILE_USER` is undefined (by default it is), check R's current working directory for `.Rprofile`. Generally speaking this is where a project's `.Rprofile` will be stored.
7. If no `.Rprofile` is found in R's current working directory, check the user's home directory `~/.Rprofile`.

Similar to Renvirons, a site-wide Rprofile and EITHER an R project Rprofile or user Rprofile can be loaded at the same time. You cannot have a project Rprofile and a user Rprofile loaded at the same time.

## Links for better understanding Rprofiles and Renvirons

* [Official documentation from R concerning its start-up process around Rprofiles and Renvirons](https://stat.ethz.ch/R-manual/R-devel/library/base/html/Startup.html)
* [Excerpt from the *Efficient R Programming* book concerning Rprofiles and Renvirons](https://csgillespie.github.io/efficientR/set-up.html#r-startup)
    + Here is an [additional excerpt](book.https://csgillespie.github.io/efficientR/3-3-r-startup.html#r-startup) from an older (I think) version of the book.
* [Deeper dive on Rprofiles and Renvirons provided by RStudio](https://rviews.rstudio.com/2017/04/19/r-for-enterprise-understanding-r-s-startup/). It goes into some interesting use cases for Rprofiles and Renvirons.
* [Excerpt from the *What They Forgot To Teach You About R* Book concerning Rprofiles and Renvirons](https://rstats.wtf/r-startup.html). It has a very useful (although intimidating at first glance) diagram of R's start-up process.
* [For the curious who are interested in using environment variables in the OS](https://devconnected.com/how-to-set-and-unset-environment-variables-on-linux/)
* [Useful list of environment variables which affect R](https://stat.ethz.ch/R-manual/R-devel/library/base/html/EnvVar.html)

## Libraries
What is a library? In the words of [Hadley Wickham](http://r-pkgs.had.co.nz/package.html), a library is simply a directory containing installed packages (side-note this link is very useful, in general, because it gives a very good overview of packages and the different types of packages).

Why should you be concerned with libraries? The power of R largely comes from its extensibility through packages. Managing your libraries is important then to ensure all of your packages play nice together which ensures your code works.

### Where are my packages currently being stored?

* The **library search path** (or where R looks for your installed packages) is initialized at start-up from a variety of different sources each taking a different priority. This means if one happens to have multiple versions of an R package installed, libraries with higher priority will have their version of the package loaded. It also means when packages are being installed, they will be installed into the library with the highest priority.
    1. The library paths specified by the environment variable `R_LIBS` take the highest precedence. The use case for this environment variable is a bit unclear to me. It seems as if the most appropriate use case is if there are site libraries that you want to take precedence over users' libraries.
        + By default, `R_LIBS` is unset.
    2. The library paths specified by the environment variable `R_LIBS_USER` are next highest. This should point to a user's respective libraries.
        + By default (on GNU-Linux systems), this is set to `~/R/R.version$platform-library/x.y` where *x.y* refers to the version of R being used (e.g. 3.4).
    3. Next in terms of priority are the library paths specified by the R variable `.Library.site`. How it gets set:
        
        + Is the environment variable `R_LIBS_SITE` set? If so, set the value of `.Library.site` to `R_LIBS_SITE`.
        + If `R_LIBS_SITE` is not set, `.Library.site` defaults to `R_HOME/site-library`.
        + If `R_HOME/site-library` does not exist, `.Library.site` does not get set. As a result, there are no site libraries.
        
        &nbsp;
    4. Last in terms of priority is the path returned by the R variable `.Library` which is `R_HOME/library`. Generally speaking this is where the default R packages (which came in the initial R download and installation) are kept.
        + The value for `.Library` cannot be changed.
* To see your library search path, you can use the `.libPaths()` function in an R session. When you don't provide any arguments, it will provide the current library search path which will generally look like `unique(c(R_LIBS, R_LIBS_USER, .Library.site, .Library))` with the first item having the highest priority. You can also do `.libPaths(new)` which designates a **new** directory to include in your library search path. Interestingly the library search path looks like `unique(c(new, .Library.site, .Library))` after providing an argument for `new`. This means the directories designated by `R_LIBS` and `R_LIBS_USER` are no longer part of the search path.

### Notes on libraries

* I've seen some places on the internet suggesting you set `Library.site` in an `.Rprofile` or `Rprofile.site`. In my experience, this does not work well and leads to odd behavior so I wouldn't recommend it. However, it could be because I don't have a complete enough understanding of R's start-up processes. In any case, I encourage further experimentation and maybe someone can achieve better results than I was able to using this method.
* I have additionally seen some places on the internet suggesting you set `libPaths()` directly in an Rprofile. For example, `libPaths(c("path1", "path2"))` or even `.libPaths(c("path1", .libPaths()))`. This method does technically work and generally does not lead to the odd behavior which can sometimes happen when trying to set `.Library.site` directly. However, I'm not exactly sure what this approach offers over setting these values directly using the environment variables mentioned above. Since the R environment variables are provided, it makes more sense to me to use them. I also wouldn't recommend mixing methods either because (at least for me) it would get too confusing to keep track of everything.
* All of the environment variables should be a colon-separated list of directories. All the directories must also be valid otherwise R **silently** ignores them. In other words, R will not display any messages or warnings that a path was not valid (does not exist). This is a subtle but important point. I've banged my head against the wall so many times because a library was not showing up in .libPaths() only to realize I had typed in the path incorrectly.
    + This also leads to interesting behavior when running R as a sudo user. For example, if `R_LIBS_USER` is the default `~/R/R.version$platform-library/x.y` then this path will be invalid when run as sudo (since your ~ directory is different as yourself vs. root, and I'm assuming this library does not exist in root's home directory). As a result, it will not show up in your .libPaths(). Of course, this also depends on which version of GNU-Linux one is using since different operating systems treat `sudo` and `su` differently. As of the time of this writing for example, if I ran `sudo R` on Ubuntu 18.04 my `R_LIBS_USER` libraries still showed up. If I ran `sudo su` then `R`, my `R_LIBS_USER` libraries did not show up. Contrast this with Red Hat 8 where both `sudo R` and then `sudo su` followed by `R` resulted in my `R_LIBS_USER` libraries not showing up.
* Only **one** version of each R package can be installed and accessed in a given library at a time.
* An R library is tied to a specific version of R meaning unexpected behavior can result in trying to load a package from a library associated with a version of R different from the one you are using.
* On some GNU-Linux systems, there are a bunch of site libraries defined by default under `R_LIBS_SITE`. I was confused as to what was the difference between all of them so I after some searching, I found [the answer](https://stat.ethz.ch/pipermail/r-help/2003-October/041178.html) which I will document here:

    + `/usr/lib/R/library` is for the default R packages which are installed using the OS package manager when downloading/installing R itself.
    + `/usr/lib/R/site-library` is for R packages installed using using the OS package manager (yum, apt, etc.).
    + `/usr/local/lib/R/site-library` is for R packages installed using R.
        
### Links for better understanding libraries
* [A fellow R user who was just as confused as I was when I first started learning about libraries has their questions answered](https://community.rstudio.com/t/help-regarding-package-installation-renviron-rprofile-r-libs-r-libs-site-and-r-libs-user-oh-my/13888)
* [This is for Windows but still very informative for understanding libraries, and it also has a helpful video](http://www.quintuitive.com/2018/03/31/package-paths-r/)
* [Official R documentation concerning libraries and the library search path](https://stat.ethz.ch/R-manual/R-devel/library/base/html/libPaths.html)