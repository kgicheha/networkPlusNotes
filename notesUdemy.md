
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

Star Topology
May be referred to as hub and spoke
Considered a hybrid
Used in most large and small networks
All devices are connected to a central device
Swtiched Ethernet networks
	The switch is in the middle


Mesh Topology
Each host is connected to all other hosts
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

Coaxical Cabling 
Coaxial cable has two conductors:
	One center point and a tubular conducting layer
Radio grade (RG) specifies the thickness of the conductors, insulation, and shieling

RG-6 has a resistance of 75-Ohm rating and is commonly used for cabling networks
	Used a threaded F-type connector
Advantages of Coaxical Cables
	Highly resistant to electromagmentic interference (EMI)
	Highly resistance to physical damage

BNC Connector
allows for quick connect and disconnect
Is used to connect the RG cables

Twinaxial Cable
Two twin inner conductors

Twisted Pair Cabling
Twisted cables reduce electromagnetic interference (EMI) and crosstalk
Modern twisted pair has four or more pairs of cables

Unshielded Twisted Pair (UTP)
Unshielded and more susceptible to interference and environmental factors
Has a maximum distance of 100 meters (325 ft)
Uses a RJ-45 connector
Comes in two standards:
	TIA/EIA-568 and TIA/EIA-568B


UTP Category Ratings
Define the speed and length of cables
Type
Distance
Max Bandwidth
Cat 5
100 meters
100 Mbps up to 1 Gbps
Cat 5e
100 meters
1 Gbps (better EMI protection)
Cat 6 
55 meters
10 Gbps (only up to 55 meters with 10GBASE-T network)
Cat 6a
100 meters
10 Gbps (better EMI and crosstalk protection)
Cat 7
100 meters
10+ Gbps
Cat 8
100 meters
25 Gbps (40 Gbps at 30 meters, 40GBASE-T network)

Shielded Twisted Pair (STP)
Acts as a conducting shield by covering the four pairs of signal-carrying wires as a means to reduce electromagnetic interference

Fire Ratings
Cable fire rating is normally clearly marked on the manufacturer’s box
Plenum-rated → most fire resistant→ more expensive than PVC cables
Riser-rated → cable that go in non-plenum spaces and between multiple floors of buldings
PVC or non-plenum rated → not considered fire/smoke resistant 

Ethernet
Ethernet is defined by the IEEE 802.3 standard
The IEEE has defined many versions of Ethernet
The Ethernet standard consists of 3 parts:
	A number → specifies the data transmission speed of the media
Contains a word(most “Base”) → indicates the technology or the method the media uses to transit data → the word “Base” signifies a type of network that uses only one carrier frequency for singaling and required all network stations to share its use
A number of letters → signifies the length or type of the cable tha the media uses in implementation →For example, if the standard contains a letter T in this part, it means the standard uses a twisted-pair cabling. Or if a standard contains a number 5 in this part, it means the standard can span 500 meters long 

Example: 10GBaseT → contains 10 Gigabit speed, uses Cat6 or higher grade UTP cable. 

Ethernet Frames Consists of:
	Preamble → informs the receiving system that a frame is starting and enables synchronisation
Start Frame Delimiter (SFD) → signifies that the destination MAC address field begins with the next byte
	Destination MAC Address → identifies the receiving system
	Source MAC → identifies the sending system
	Type → defines the type of protocol inside the frame, for example IPv4 or IPv6
Data and Pad → contains the payload data. Padding data is added to meet the minimum length requirement for this field (46 bytes)
Frame Check Sequence (FCS) → contains a 32-bit Cyclic Redundancy Check (CRC) which allows detection of corrupted data 
A jumbo frame can carry 9000 bytes

Terminating Twisted Pair
An RJ-455 connector is used to connect to most network cards
Pay attention when crimping to follow the TIA/EIA-568A or 568B

Hubs and Switches
Switches forward frames based on MAC addresses
Switches create and use MAC addresses tables to map ports and host devices
Switches put all hosts in their own collision domain
Hubs use Carrier sense multiple access/ collision detection(CSMA/CD) to avoid collisions
CSMA/CD is used for devices to listen and see who is communicating 

ARP is a method used to get the MAC addresses of hosts
Full-duplex is a communication mode where two devices can talk at the same time
Carrier sense multiple access/ collision avoidance (CSMA/CA) is for collision avoidance rather than detection

Spanning Tree Protocol (STP)
A layer 2 network protocol used to prevent looping within a network topology
Sends frames called Bridge protocol data units (BPDUs)


Chapter 5: Installing a Physical Network

Structures cabling defines how we install cabling
TIA standards specify wiring standards for structured cabling
Patch panels terminate one end of horizontal runs
RJ-45 crimps are used only on patch cables
Horizontal runs are terminated with 110-punch-downs
Patch panels and RJ-45 connectors also have Cat ratings
The primary equipment room is called the Main Distribution Frame (MDF)
IDF is a smaller version of the MDF, and usually sits in another location that eventually routes back to the MDF
The demarcation point can be any where in your organization
Rack-mounted equipment is standardized at 19” wide and a multiple of 1 ¾ “ tall (called a U or unit)
The demarc separates the telecom company’s property from your responsibility. 
A 66-punchdown blockis a very old patch panel, typically used in a non-VOIP telephone systems’
A 110-punchdown block patch panel is the way to distribute copper wired networks
A fiber distribution patch panel is used to distribute fiber-optic networks
Continuity testing will show if the cable has any breaks
A time domain reflector(TDR) will show the length of the cable and help pinpoint mid-cable breaks 

Patch cables and wall outlets are the most common part of structured cabling to fail
Loopback adapters test the network card’s ability to send and receive
Loop back address is 127.0.0.1
Use ping 127.0.0.1 to check whether the network interface card is working

Multimeters test a variety of metrics such as voltage, current, resistance, and frequency
Voltage monitors track and record drops in voltage which can show problems with power
Time domain reflectometers (TDRs) are great tools to chck for breaks in horizontal runs

Tone generators and tone probes are used to locate cables and connections
Tone generators create the signal for the probe
Tone probes translate the signal into an audible tone

For jitters in VOIP and video streaming, consider buffering or increasing speed.
Make sure the patch cable specification is up-to-date with the network speed
If switch lights are not blinking, try different ports or check if it’s an uplink port  

Horizontal runs go through the plenum space
The equipment room is where all devices eventual connect to
The work area is where an end-user would be 

Chapter 6: TCP/IP Basics
IP Address
Unique number that identifies a device on the internet, acting as the device’s logical address to identify that network connection. 
Assigned to every device connected to the Interne so the internet knows where to send your emails and data to
It corresponds to Layer 3, the network layer of the OSI model. 

IP Address Classes
IP addresses are broken into 5 different classes
Class A: reflects the network portion in the first octet, and leaves octets 2,3,and 4 for the network manager to divide into hosts and subnets as needed. Used for networks with more than 65k hosts
	Range: 0-126
Class B: claims the first two octets for the network, leaving the remaining part of the address, octets 3 and 4 for networks with 256 to 56k hosts
	Range: 192-223
Class C: claims the first three octets wit the hosts and subnets in the remaining 8 bits of octet 4. Class C is reserved to networks with fewer than 254 hosts
	Range: 224-239
Class D: reserved for multicasting
Class E: reserved for research by the Internet Engineering Task Force (IETF)
Examples of IP address classes
	Class A: 255.0.0.0
	Class B: 255.255.0.0
	Class C: 255.255.255.0

Each computer on a TCP/IP network must have a unique IP address
IPv4 addressed are written as four octets, such as 192.168.4.12
Each octet represents a binary string
	Example 192, represents 11000000
Decimal to binary Example → 224
128 64 32 16 8 4 2 1
1      1   1   0  0 0 0 0

Address Resolution Protocol (ARP)
Protocol at the data link layer that a computer uses when it knows the IP address but need the MAC address
ARP requests are broadcast over a network
Broadbact address for ARP:
	FF:FF:FF:FF:FF:FF
ARP cache command: arp -a

Subnet Masks
A 32-bit address that separates an IP address into network address and host address that identify the host device operating on that network
The “255” address is always assigned to a broadcast address, and the “0” address is always assigned to a network address. Neither can be assigned to hosts, as they are reserved for those special purposes
When organization need additional subnetworking, subnetting divides the host element of the IP address further into a subnet. 
Each host needs to have a subnet mask
The host uses the subnet mast to know if the destination is on the local network or a remote network
Each host knows the default gateway so that it can forward traffic to remote networks
Subnets masks have all 1s on the left and all 0s on the right
The more subnets you have the less hosts are available 

Subnet example:
172.16.3.0 /24 subnet mask will be 255.255.255.0
	3 octets are taken

Classless Inter-Domain Routing (CIDR)
Way to combine several class-C address ranges into single network or route


Dynamic Host Configuration Protocol (DHCP)
A client/server protocol that automatically provides an IP host with its IP address and other related configuration information such as subnet mask and default gateway
Each broadcast domain must have only one DHCP server
The DHCP server must be run within the broadcast domain
Every modem operating system comes with DHCP enabled by default
Command prompt to display network information
	Ipconfig for Windows/masOS
	Ifconfig in Linux

Special IP Addresses
Private IP Address/ Internal IP Addresses → only shares information within network
Any IP address that starts with a 10.X.X.X
Any IP address from 172.16.x.x - 172.31.x.x
Any IP address 192.168.x.x
Loop back address → only communicates with itself
	Ipv4 →127.0.0.1
	Ipv6 → ::1
Automatic Private IP Addressing (APIPA) → indicates the DHCP server is down
	169.254.x.x

Virtual machines can be a source of duplicate MAC address errors


Chapter 7: Routing
