# The History of the Internet

It's important to understand how we got where we are today. What problems were people in the past trying to solve? What does that mean for the problems we are trying to solve today?

https://www.vox.com/a/internet-maps -> Good little overview of how the *internet* was first created. ARPANET (military project connecting a few universities which continued to grow and grow). One important point to mention is the creation of the **TCP/IP** or Transmission Control Protocol and Internet Protocol which together describe how two computers can communicate. This was an important step to allow for the growth of the Internet because it allowed for the network to grow without there needing to be some central, governing authority in charge of authorizing each new addition to the network. TCP/IP sets standards on how messages are to be sent, how data can be *chunked* or turned into packets, how to reassemble the packets of data as they arrive, how to ensure the right person receives the right data and confirm it was received, how to request new information if it got corrupted, and so on and so forth.

Other protocols like **UDP** are used in other situations (e.g. Skype) because it has looser rules around corrupted packets. It allows for the video stream to continue on streaming without attempting to request again the packets which may been dropped. For video calls, it's usually OK if a few packets are dropped here and there. TCP is much more robust, but the robustness comes with much more overhead in terms of messages being sent back and forth yet the same amount of information is being transmitted.

Another particular problem which faced the network (although it was primarily driven by the academic end users) was how to share files and communicate efficiently since each of the individual networks tended to have their own protocols and ways of doing things. So Tim Berners-Lee invented the World Wide Web (or WWW). 

## What is the World Wide Web?

It's an agreed upon language and set of protocols for communicating. Documents and resources are identified with URLs (Uniform Resource Locators) which may have hyperlinks interleaved within them and are accessible over the Internet. Resources are transferred using the Hypertext Transfer Protocol (HTTP), and they may be accessed using a web browser. Resources may also be published by a web server. Web pages are hypertext documents formatted in Hypertext Markup Language (HTML).

Tim Berners-Lee was actually the first web developer. He created the first website!

https://www.youtube.com/watch?v=guvsH5OFizE&list=PL8dPuuaLjXtNlUrzyH5r6jN9ulIgZBpdo&index=32 -> Great overview of the World Wide Web. Previous video is also useful for understanding TCP/IP.

## Pain Points of Modern Web Development

1. **Different Browsers** Each browser handles webpages slightly differently. It used to be much worse in the past though, and today it is much better.
2. **Tablets, Computers, Phones**: We have to make sure our website works on many different types of screen configurations.