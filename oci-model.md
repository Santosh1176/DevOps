The OSI Model is an important component of networking, it Solis all the activities and protocols corresponds with a perticular Layer in the OSI Model. Following are examples of some:

- Layer 1 is **Physical Layer**, in which we have UTP (Copper Cabling Standard)
- Layer 2 Ethernet - **The Data Link** Layer. The standard on how bits are transmitted on the copper cable
- Layer 3 IP v4 - **The Network Layee**The standard on how logical addressing works and how routing is done
- Layer 4 TCP - **Transport Layer**Standard of how connections are maintained and how packets are transported.
- Layer 5 - 7, consisting of **The Session Layer**, **Presentation Layer** and **Application Layer**are combined as the application level in the TCP/IP model but they are essentially HTTP, Browser of Choice. 

# A real life brief example of how these Layers interact. 

- *In Real life data does not travel through each layers, so to say. But, it travels through HTTP to IP to Ethernet to bits on the cable.*
- *In Real world Data travels through 5 main layers. Physical, Data Link, Network, Transport, and Application Layer. (Session and Presentation layers are not used)*
*****
So the thing is while your visiting google your having streams of packets go back and forth, if we want to look at the life of a packet let’s look at part of the process of visiting google, the DNS.
We type google.com into our browser, but our computer doesn’t understand this fancy language we just threw in a bar, it’s gotta ask a computer that knows people talk what the heck we’re trying to go to. Our PC has to contact it DNS Server. Our host starts with a payload, our Layer 5-7 info saying hey, this is a DNS message. But how do we want the server to read this DNS message, we’ll we’re gonna use UDP so let’s slap a L4 UDP header on so when the DND server gets this payload he knows hey, these bytes should be interpreted as if they mean these things in this position.
So now what is our IP info, well the source IP is our own probably something like 192.168.0.23, and the dst IP is that out of default DNs server, we’ll use Googles of 8.8.8.8, so this is our starting host and that server is our end host.
Now we need to know where to send this packet right now. And since the Google DNS server is not in our network our switch won’t have a MAC for it, we better send this on to our default gateway router, they know how to get to places outside our network. Assuming we already know our default Gateways MAC we add a L2 header with our MAC as the src and our Routers MAC as the dst. Then we send this frame along the L1
A switch picks up the packet, reads the L2 and says oh, this is for the MAC address of the default Router, ik where that guy is, then sends it along.
Our router gets our frame, “we just got a letter, we just got a letter, we just got a letter, etc.(this is long I get to put in jokes) Anyway the router sees it’s own MAC so it takes off the L2 header we put on and sees oh, this host wants to talk to the Google DNS server at 8.8.8.8, luckily very convenient they server is directly connected to me (realistically there’s a few more routers inbetween but just imagine with me). Let me put a new L2 header on, this one will have my src MAC and the servers dst MAC, now we send it.
The DNS server gets this frame, sees it’s own MAC and opens it up, sees it’s own IP and opens its up, sees UDP and know how to read the data, and then reads the data in the format DNS info.
Then it sends a reply, forms DNS data saying hey host, your person is asking to talk to google.com, google.com can be reached if you send info to this IP address (xxx.xxx.xxx.xxx) then it adds the port (hey this is still UDP) we’re sending it to the IP address of the initial endhost with a L2 pit stop at this MAC router then the router will forward it to the MAC host address