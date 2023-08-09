
CompTIA Network+ Study Guide  - Mike Meyers UDEMY

Chapter 1: Network Models

OPEN SYSTEMS INTERCONNECTION MODEL aka OSI MODEL
Used to describe the way traffic is moving from one part of the network to another.
Consists of 7 unique protocols 
Way to remember from top to bottom:
All People Seems To Need Data Processing

Layer 1: Physical Layer
	The physics of the network
		Signaling, cabling, connectors
	This layer ensures that the data frames get from one system to another.
	Deals with:
		Cables, fiber, and the signal itself
Layer 2: Data Link Layer
	Allows individual systems to be addressed in such a way that Ethernet frames get to the right spot
		Inspects incoming frames to see if they’re addressed for me based on my MAC address
MAC Address: a unique 48-bit value that’s burned into every network, both hardwires or wireless
The basic network “language”
	The foundation of communication at the data link layer
Data Link Control (DLC) protocols
	MAC (Media Access Control) address on the Ethernet
The “switching” layer
Deals with:
Frames, MAC address, Extended Unique Identifier (EUI-48, EUI-64), Switch

Layer 3: Network Layer
	The “routing” layer
Associated with the Internet Protocol (IP)
	Takes a look at the IP address to ensure that the data is supposed to be sent to you.
		Frames will be broken into smaller pieces to traverse different networks 
	Deals with:
		IP Address, Router, Packet
Layer 4: Transport Layer
	The “post office” layer
		Parcels and letters
	The main job of this layer is to assemble and disassemble different pieces of data as they come in. 
	Protocols used at layer 4:
		TCP (Transmission Control Protocol)
		UDP (User Datagram Protocol)
Used when accessing a webpage, but the page is so large that you can’t send all the data in one single frame
Have to split it up into separate frames and send those individual pieces across the network, where they are put back together on the other side. 
	Deals with:
		TCP Segment, UDP Datagram
Layer 5: Session Layer
	Part of the hosts that actually makes the connection to the remote host
Communication management between devices
	Starts stops, or restarts communications between one endpoint and another
Use control protocols or tunneling protocols to begin communication between the different endpoints
If the IP address gets the data to the right computer, it is the port numbers that are part of your packet that get the data to the right application. 
Deals with:
		Control protocols, tunneling protocols
  
Layer 6: Presentation Layer		
The main job is to make sure that data not only gets to the right application but more importantly, gets it in a format that the application can view
Just before we’re able to view information on our screen, the presentation layer puts the data into a form we can understand
Character encoding
Application encryption 
Often combined with the Application Layer
Deals with:
	Application encryption (SSL/ TLS)

Layer 7: Application Layer
	The layer we see 
The layer provides ways for manipulating the data (information) 
Used by the end-user software such as web browsers and email clients
Provides protocols that allow the software to send and receive information and present meaningful data to the users
	Example:	
HTTP, FTP, DNS, POP3
	Deals with:
		Your eyes

Data Packet
A unit of data is made into a single package that travels along a given network path. 
Are used in the Internet Protocol (IP) transmission for data that navigates the Web, and in other kinds of networks

Frames
Devices on a network send and receive data in discrete chunks called frames (or packets)
	Frames are a maximum of 1500 bytes in size
Frames are created and destroyed inside a network interface card (NIC)

Network Interface Card (NIC)
Acts as a middleman between a computer and a data network. 
Used in Layer 2, the Data Link layer which contains the MAC address
For example, when a user requests a webpage, the computer will pass the request to the network card, which converts it into electrical impulses

MAC Address
A unique 48-bit identifier for a NIC
Frames have a destination and source MAC addresses
NICs use MAC addresses to decide whether or not to process a frame
Use the “ipconfig /all” command prompt to display all current TCP/IP network configuration values 
	The “Physical Address” represents the MAC address
Uses hexadecimal and can use values of 0-9 and A-F

Broadcast vs Unicast
Unicast transmission is addressed to a single device on a network
Broadcast transmission is sent to every device in a broadcast domain
	Broadcast Domain
A division of a computer network in which all nodes/devices can receive broadcast traffic from each other at the data layer link
	The broadcast address looks like this:
		FF-FF-FF-FF-FF-FF

IP Address
A unique address that helps to identify a network connection
Used for routing and transmission of data packets over the internet
Unlike MAC Addresses, IP addresses are not fixed. You can apply your own IP address
	It is assigned by the network administrator or internet service provider(ISP)
IP packets always sit within frames. 
	The IP packet within the frame never changes 
An IPv4 address looks like this: 31.44.17.231

Router
A router connects two computers on two different networks.
Moves data between two or more computer networks
Looks at IP addresses to send data to the proper networks 

Switch
Received incoming data packets and redirects them to their destination on a local area network (LAN)

Default gateway
The connection to your router itself


Packets and Ports
Port numbers help direct packet traffic between the source and destination
Port 80 is for HTTP
Port 20 and port 21 are for File Transfer Protocol (FTP)
Pockets have sequence numbers so the network software can assemble the file correctly

Transmission Contol Protocol (TCP)
Connection-oriented conversation between two computers to make sure that the data gets whole, complete, and in order 
Big pieces of TCP:
Sequencing number → allows you to reassemble everything properly. As well as the acknowledgment that everything is good when a data set comes in. 

User Datagram Protocol (UDP)
Connectionless conversation between two computers
Less reliable compared to TCP, but works quickly


Chapter 2: CABLING AND TOPOLOGY
Physical Topolgy
Actual layout of devices
Logical Topology
How the data flows from host to host

Bus Topology
Early local area networks
	Coaxical cable was the bus
Simple, but prone to errors
	One break in the link disabled the entire network

Ring Topology
Used in many popular topologies
Still used in many Metro Area Networks (MANs) and Wide Area Networks (WANs)
	Dual rings 
	Built-in fault tolerance 


