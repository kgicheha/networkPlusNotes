OPEN SYSTEMS INTERCONNECTION REFERENCE MODEL aka OSI MODEL
Used to describe the way traffic is moving from one part of the network to another.
Consists of 7 unique protocols 
Way to remember from top to bottom:
All People Seems To Need Data Processing

Layer 1: Physical Layer
	The physics of the network
		Signaling, cabling, connectors
	“You have a physical layer problem”
		Fix the cabling, punch-downs, etc
		Runn loopback tests, test/replace cables, swap adaptor cards
	Deals with:
		Cables, fiber, and the signal itself
Layer 2: Data Link Layer
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
	Frames will be broken into smaller pieces to traverse different networks 
	Deals with:
		IP Address, Router, Packet
Layer 4: Transport Layer
	The “post office” layer
		Parcels and letters
	Protocols used at layer 4:
		TCP (Transmission Control Protocol)
		UDP (User Datagram Protocol)
Used when accessing a webpage, but the page is so large that you can’t send all the data in one single frame
Have to split it up into separate frames and send those individual pieces across the network, where they are put back together on the other side. 
	Deals with:
		TCP Segment, UDP Datagram
Layer 5: Session Layer
	Communication management between devices
	Starts stops, or restarts communications between one endpoint and another
Use control protocols or tunneling protocols to begin communication between the different endpoints
	Deals with:
		Control protocols, tunneling protocols
Layer 6: Presentation Layer		
Just before we’re able to view information on our screen, the presentation layer puts the data into a form we can understand
Character encoding
Application encryption 
Often combined with the Application Layer
Deals with:
	Application encryption (SSL/ TLS)
Layer 7: Application Layer
	The layer we see 
	HTTP, FTP, DNS, POP3
	Deals with:
		Your eyes
  Real-World OSI Model Example: Sending and receiving information in Google Mail
Layer 7: Application 
	Login to Google https://mail.google.com
Layer 6: Presentation
	The data is encrypted in the layer when sending information back and forth
Layer 5: Session 
	Links together the application and presentation layers to the layers below (layers 4 - 1)
Layer 4: Transport
	Uses TCP encapsulation to send the data
Layer 3: Network
	IP addresses that are used from your workstation and the Google email server
Layer 2: Data Link
All the TCP and IP traffic is encapsulated within Ethernet frames, then those frames are sent over the network 
Layer 1: Physical 
	The physical signals that are used to send the frames from one device to another 


DATA COMMUNICATION

Protocol Data Unit (PDU)
	Sometimes known as Transmission units
	A different group of data at different OSI layers

Encapsulation 
Layers 5,6,7: Application Data
Layer 4: TCP Header + Application Data
Layer 3: IP Header + TCP Header + Application Data
Layer 2: Framer Header + IP Header + TCP Header + Application Data + Frame Trailer

Decapsulation
Layer 2: Framer Header + IP Header + TCP Header + Application Data + Frame Trailer
Layer 3: IP Header + TCP Header + Application Data
Layer 4: TCP Header + Application Data
Layers 5,6,7: Application Data

Transmission Control Protocol(TCP)
Communication standard for delivering data and messages through networks
TCP Flags
The header describes or identifies the payload
The TCP Header contains important control information
	Includes a set of bits called TCP flags
The flags control the payload
	SYN - Synchronize sequence numbers
 	PSH - push the data to the application without buffering
	RST - reset the connection
	FIN - last packet from the sender

Maximum Transmission Unit (MTU)
Maximum IP packet to transmit
Fragmentation slows things down
	Losing a framgent loses an entire packet
	Requires overhead along the path
Difficult to know the MTU all the way through
	Automated methods are often inaccurate 
	Especially when ICMP is filtered

IP Fragmentation
The process that breaks packets into smaller pieces
Fragments are always in multiples of 8 because of the number of fragmentation offset bits in the IP header

Troubleshooting MTU
MTU sizes are usually configured once 
	Based on the network infrastructure and doesn’t change often
A significant concern for tunned traffic
	The tunnel may be smaller than your local Ethernet segment
What if you send packets with a Don’t Fragment (DF) set?
	Routers will respond back and tell you to fragment
Troubleshooting using ping
	The maximum size you can send when DF is set is 1472 bites 
	Command
	Windows: ping -f -l 1472 8.8.8.8
		-f represents don’t fragment
		-l represents
		1472 is the bit size you want to send
		8.8.8.8 is the IP address 
	Linux and macOS: ping -D -s 1472 8.8.8.8


NETWORK TOPOLOGIES AND TYPES
Network Topologies
Useful in planning a new network
	The physical layout of a building or campus
Assists in the understanding signal flow
	Helps with troubleshooting problems

Star Topology
May be referred to as hub and spoke
Used in most large and small networks
All devices are connected to a central device
Swtiched Ethernet networks
	The switch is in the middle

Ring Topology
Used in many popular topologies
Still used in many Metro Area Networks (MANs) and Wide Area Networks (WANs)
	Dual rings 
	Built-in fault tolerance 

Bus Typology
Early local area networks
	Coaxical cable was the bus
Simple, but prone to errors
	One break in the link disabled the entire network
Mesh Topology
Multiple links to the same place
	Fully connected
	Partially connected 
Helps deal with redundancy, fault-tolerance, load balancing
Used in wide area networks (WANs)
	Fully meshed and partially meshed
Commonly used in IOT devices

Hybrid Topology
A combination of one or more physical topologies 
Most networks are a hybrid	

Wireless topology
Infrastructure
	All devices communicate through an access point
	The most common wireless communication mode
Ad hoc networking
	No pre-existing infrastructure
	Devices communication amongst themselves
Mesh
	Ad hoc devices work together to form a mesh “cloud”
	Self form and self heal



