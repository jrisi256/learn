# How The Internet Works

What happens when you type https:://www.google.com into the search bar of a web browser? Well that request is routed to our Internet Service Provider (ISP). The ISP then sends that request to the Domain Name System (DNS) Server. The DNS is like the phonebook of the Internet. It translates the **domain name** (https://www.google.com) into an **IP (Internet Protocol) address** (e.g. 192.168.1.1). Every device connected to the Internet has its own unique IP address which other machines can use to find that device.

The DNS then sends the IP address back to the ISP who then sends it back to the web browser.

The web browser, which now has the IP *address* of https:://www.google.com sends a request to that IP address. We are now pinging Google's servers. Those servers know, based on the IP address provided, what files to serve up to us (usually HTML, CSS, and/or Javascript).

An important point to mention before getting into too much more detail that despite the increasing *wireless* nature of our connection to the Internet, the backbone of the Internet is very much dependent on a wired infrastructure. Our modem connects to the ISP through cables. The ISP then uses submarine cables to find and connect to wherever the Google servers are which then sends the requested files back to us.

If you're curious to see how your request to access a website is being routed, you can use the **tracert** or **traceroute** commands based on your OS.

Important takeaways for building efficient applications:

1. **The Location of the Server**: The closer the server, the quicker the *hop* will be so to speak.
2. **How Many Trips**: You want to minimize the number of trips needed to get the files/information into the hands of the user.
3. **The Size of the Files**: How big the HTML, CSS, and Javascript files are will play a big role in how efficiently your application works.

## How does information physically get transmitted when trying to connect to the Internet?

First, the WiFi router is connected to the modem (or sometimes you will use an Ethernet cord to connect directly to the modem). The modem uses existing phone lines (in most cases) for translating or **modulating** (adds the digital signal on top of an analog telephone signal) the digital signals into an analog signal so the information can actually be transported using the phone lines (since phone lines can only transport analog signals like the physical sound of your voice).

Once the signals have reached the other end, they're passed through a second modem which demodulates them (separates out the telephone signals and turns them back into a digital form) and then handed over to the ISP servers so they can handle the digital request. The information is then modulated again, sent back to you, and your modem demodulates the information.

### How do cellphones work?

* Cellphones work differently from this since they send and receive information using radio waves. A **microphone** picks up the voice signals and translates them into electrical signals. A **microchip** turns these signals into numbers and are then beamed out of the phone's antenna to the nearest **cellphone tower**. The tower passes on the signal to the **base station** which coordinates all activity within the local part of a cellphone network known as the **cell**. The base station will then determine how to route calls to their ultimate destination.
* Cell towers and base stations are important because otherwise our cellphones would need enormous antennas and giant power supplies to reach anybody not within our immediate vicinity. Think of the problems with walkie-talkies and radio stations. After a certain while, there are too many other signals which interfere, or the distance becomes too great for the signals to reach other.
* *Cells* also serve an important function of allowing many millions of people to be communicating at the same time. If several people in the same area want to use their phones at the same time, naively the signals would interfere with each other, and it would be impossible to call somebody. What one can do is assign each phone call to a slightly different frequency. If you have millions of people in a given area trying to make phone calls though, there may not be enough frequencies to go around. So you make sure your cellphone has a weak enough transmitter so it cannot transmit beyond the current cell (and thus will not interfere with another cell). You can then use the same frequency in multiple cells.

### Circuit switching vs. packet switching

Older modems would use a technique known as **circuit switching** for moving data along the Internet. This technique is basically how phones worked. You would call someone, and if they were free you could talk to them. You could then talk to only them, and they could talk only to you. This is known as *dialup*. While you're using dialup, no one can call you, you'll be billed by the second, and your connection will be very slow.

Nowadays most data is moved using **packet switching**. With circuit switching, you would move the entire set of information all at once. With packet switching, the data is broken up into tiny little pieces called packets. Each packet is told what its ultimate destination is, and then each packet is allowed to travel separately to get there. Each packet may wind up taking totally different routes. When they reach their final destination, they're reassembled. Packet switching is much more efficient because you don't need a permanent connection between the two places which are communicating (like you do with phone conversations). This also means you aren't blocking an entire chunk of the network each time you send a message. As a result, many more people can use the network now at the same time since packets will flow along routes which are more/less busy. This allows for a more even distribution of data across the network as a whole.

### Broadband vs. Dialup

Broadband was a watershed moment in creating the modern Internet. Instead of relying upon dialup which was slow, expensive, and cumbersome, we could now rely upon broadband. The key contribution of broadband internet was it took the connection between your computer and your ISP, and it divided into many, many different channels allowing for information to travel in parallel streams simultaneously down these channels. **Fun side note**: Since most people do more downloading than uploading, more channels are dedicated to downloading hence why downloading is often faster than uploading.

### Fiber Optic

We've basically been using phone lines in ways they weren't intended. The history of the Internet is in many ways then a struggle to transition away from telephone technology to something more suitable for transporting digital information.

For a while, some people were lucky and had access to cable internet which uses the same technology as cable television to transport the digital data. It uses a coaxial cable which contains a copper core insulated with aluminum, a copper shield, and an outer plastic layer to transmit the data.

Nowadays the standard is fiber optic. Fiber optic cables (usually made of glass or plastic) have digital information sent through them as a beam of light or laser light pulses. It has the light bouncing around the cable as if it were a funhouse of mirrors inside of the cable. Some places only have **Fiber to the Cabinet** (FTTC) where their house will be connected to a fiber optic connection cabinet through a copper wire. Other places have **Fiber to the Building** (FTTB) or **Fiber to the Home** (FTTH) which gives the full benefits of fiber optic.

### Modern cellphone technology

Different trends in different parts of the world are causing the infrastructure of the Internet to be developed differently. For example, the increasing power of cellphone networks has made it more cost-effective to deliver mobile broadband over cellphone networks rather than attempting to refit an antiquated telephone network (or in some cases they don't even have a telephone network to use).

Traditionally cellphones had been using circuit-switching technologies to connect to the Internet which is why there were so slow. But starting with 3G networks, packet-switching technologies began to be used which greatly increased the internet speeds which could be achieved on cellphones, and it's been rapidly improving with 4G and 5G networks.