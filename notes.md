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

NETWORK TYPES

Peer-to-Peer
All devices are both client and servers
	Everyone talks to everyone
Advantages
	Easy to deploy
	Low cost → no additional servers needed
Disadvantages
	Difficult to administer
	Difficult to secure

Client-Server
Central server
	Clients talk to the server
No client-to-client communication
Advantages
	Performance, administration
Disadvantages
	Cost, complexity

Local Area Network(LAN)
Local is relative
A building or group of buildings
Ethernet and 802.11 wireless
	Any slower and it isn’t local

Metropolian Area Network (MAN)
A network in your city
Larger than a LAN, often smaller than a WAN 
Historically MAN-specific topologies
	Everyone’s moving to the Metro Ethernet
Common to see gov’t ownership
	The “own” the right of way

Wid Area Network (WAN)
Spanning the globe
Generally connects LANs across a distance
	And generally much slower than the LAN
Many different WAN technologies
	Point-to-point serial, MPLS, etc
	Terristrial and non-terrestial


Wireless LAN
802.11 technologies
Mobility 
	Within a building 
	In a limited geographical area
Can expand coverage with additional access points
	Downtown area
	Large campus

Personal Area Network
Your own private network
Bluetooth, 
Automobile
	Audio output
	Intergrate with phone
Mobile phone
	Wireless headset

Campus Area Network (CAN) or Corporate Area Network
Limited geographical area
	A group of buildings
LAN technologies 
	Fiber connected 
	High speed Ethernet
Your fiber is in the ground
	No third party provided


Network Attached Storage(NAS)
Connect to a shared storage device across the network
File-level access

Storage Area Network (SAN)
Looks and feels like a local storage device 
	Block-level access
Very efficient in reading and writing
Easy to make small/block level changes

Both NAS and SAN require a lot of bandwidth
	May use an isolated network and high-speed network technologies




Multiprotocol Label Switching (MPLS)
Learning from ATM and Frame Relay
	Keep the advantages, ditch the disadvantages
Packets through the WAN have a label
	Routing decision are easy
Any transport medium, any protocol inside
	IP packets, Ethernet frames
A common WAN technology
	Ready-to-network

MPLS pushing and popping
Lables are “pushed” onto packets as they enter the MPLS cloud
Labels are “popped” off on the way out



Multipoint Generic Router Encapsulation (mGRE)
Used extensively for Dynamic Multipoint VPN (DMVPN)
Common on Cisco routers
You VPN builds itself
	Remote sites communicate to each other
Tunnels are built dynamically on-demand
	A dynamic mesh
More efficient network since you only create a connection when you’re using communicating between sites 
	Can also send information directly to a site, rather than having to use a main office to communicate


Software Defined Networking in a Wide Area Network
A WAN built for the cloud
Cloud-based applications communicate directly to the cloud
	No need to hop through a central point

WAN TERMINATION

Demarcation point
The point where you connect with the outside world
	WAN provider
	Internet service provider
	The demarc
Used everywhere 
	Even at home 
Central location in a building
	Usually a network interface device
	Can be as simple as an RJ-45 connection
You connect  your Customer promises equipment (CPE)

Smartjack
Network Inferface Unit (NIU)
	The device that determines the demarc
	Network Interface Device, Telephone Network Interface
Smartjack
	More than just a simple interface
	Can be a circuit card in a chassis
Built-in diagnostics
	Loopback tests

VIRTUAL NETWORKS

Network Function Virtulization (NFV)
Replace physical network devices with virtual versions
	Manage from the hypervisor
Same functionality as a physical device
	Routing, switching, load balancing, firewalls
Quickly and easily deploy network functions
	Click and deploy from the hypervisor
Many different deployment options
	Virtual machine, container, fault tolerance, etc. 

The hypervisor
Virtaul Machine Manager
	Manages the virtual platform and guest operating systems
Hardware management
	CPU
	Networking
	Security
Single console control
	One pane of glass

Virtual Switch (vSwitch)
Move the physical switch into the virtual environment
Functionality is similar to a physical switch
	Forwarding options
	Link aggregation
	Port mirroring
	Netflow
Deploy from the hypervisor
	Automate with orchestration

Virtual Network Inferface Card (vNIC)
A virtual machine needs a network interface
Configured and connected through the hypervisor
	Enable additional features
	VLAN, aggregation, multiple interfaces

PROVIDER LINKS

Satelliter Networking
Communcation to a satellite
	Non-terrestrial communication
Another way to get internet
High cost relative to terrestrial networking
	50Mbit/s down, 3 Mbit/s up are common
	Remote sites, difficult-to-network sites
High latency
	250 ms up, 250 ms down
High frequencies - 2GHz
	Rain

Copper
Extensive installations
	Relatively inexpensive
	East to instal and maintain
Limited bandwidth availability 
	Physics limits electrical signals through copper

Wide area networks
	Cable modem, DSL
Oftern combined with fiber
	Copprt on the local loop/local building, fiber in the backbone

Digital Subsriber Line (DSL)
	Uses telephone lines
Cable broadband
Called broadband because:
	Transmission across multiple frequencies
	Different traffic types
Data on the “cable” network
	Data Over Cable Service Interface Specification (DOCSIS)
High-speed networking

Fiber
Higher speed data communication
	Uses frequencies of light
Higher installation cost than copper
	Equipement is more costly
	More difficult to repair
	Communcation over long distances
Larger installation in the WAN core
	Support very high data rates
	SONET, wavelength division multplexing

Metro Ethernet or Meto-E
Metropolitian-area network
Connect your sites with Ethernet
	A common standard
The provider network is optical
	Local fiber network
	Wavelength-division multiplexing
	High speed, multiple wavelength of light










CABLES AND CONNECTORS
COPPER CABLING

The importance of cable
Fundamental to network communication
	Incredibly important foundation 
Usually only get one good opportunity at building your cabling infrastructure
	Make it good!
The vast majority of wireless communication uses cables
	Unless you’re an amateur radio operator

Twisted pair copper cabling
Balanced pair operation
	Two wires with equal and opposite signals
	Transmit+, Transmit- / Receive+, Receive-
The twist is the secret!
	Keeps a single wire constantly moving away from the interference
	The opposite signals are compared on the other end
Pais in the same cable have different twist rates

Coaxial cables
Two or more forms share a common axis
Used for television, digital cables

Fiber communication
Transmission by light
No RF signal
	Very difficult to monitor or tap

NETWORK TRANSCEIVERS
Media converter
	Converts signals of one media type to the signals of a different media type
Transceiver
	Transfer and receives data

IP SUBNETTING

BINARY MATH
A bit represented as either 0 or 1
A byte is made of 8 bits
Uses the powers of two
Binary-to-decimal conversion chart
128	64	32	16	8	4	2	1
0	0	0	0	0	0	0	0

Binary to Decimal Example: Binary of 0000010 in decimal
128	64	32	16	8	4	2	1
0	0	0	0	0	0	1	0

0   +	0    +	0    +	0    +	0    + 	0    +	2    +	0  = 2 

Decimal to Binary Example: 154
128	64	32	16	8	4	2	1
1	0	0	1	1	0	1	0

128 +  0   +    0     +   16  +   8    +   0    +      2     +  0 = 154
     
IPv4 ADDRESSING 
Internap Protocol
	OSI Layer 3 address
Every device needs a unique IP address. E.g. 192.168.1.165
Subnet mask
	Used by the local device to determine what subnet it’s on
	E.g. 255.255.255.0
Default gateway
	The router that allows you to communicate outside of your local subnet
	The default gateway must be an IP address on the local subnet
Loopback address
	An address to your self
Ranges from 127.0.0.1 through 127.255.255.254
	An easy way to self-reference (ping 127.0.0.1)
Reserved addresses 
	Set aside for future use or testing
	240.0.0.1 through 254.255.255.254
	All “class E addresses
Virtual IP address (VIP)
	Not associated with a physical network adapter
	Virtual machine, internal router address
Dynamic Host Configuration Protocol
	Provides automatic address and IP configuration for almost all devices

 
NETWORK ADDRESS TRANSLATION (NAT)
Used to increase the number of available IP addresses
NAT overload
	When a single public IP assigned to your router is used by multiple internal hosts concurrently


NETWORK COMMUNICATION
Unicast
	One station sending information to another station (one-to-one)
	
INTRODUCTION TO IP

Transmission Control Protocol (TCP)
Communications standard that enables application programs and computing devices to exchange messages over a network
Receive acknowledgement that the data has been sent 
User Datagram Protocol (UDP)
Connectionless
	No formal open or close to the connection
	No communication acknowledgement back to the sender
Port numbers
Are used for communication, not security

Secure Shell (SSH)
Encrypted communication link - tcp/22
Looks and acts the same as Telnet

Domain Name System (DNS)
Converts names to IP addresses -udp/53
www.professormesser.com = 162.159.246.164
Larger transfers may use tcp/53

Simple Mail Transfer Protocol (SMTP)
Server to server email transfer
tcp/25 (SMTP using plaintext)
tcp/587 (SMTP using TLS encryption)

Internet Message Access Protocol v4 (IMAP4)
 tcp /143 (plaintext), tcp/993(IMAP over TLS)
Inclused management of email inbox from multiple clients

Secure File Transfer Protocol (SFTP)
Used to transfer a file from a device to another in the network
tcp/22

File Transfer Protocol (FTP)
tcp/20 (active mode data), tcp/21 (control)
Transfers files between systems
Authenticated with a username and password
Full-featured functionality (list, add, delete, etc. )
Dynamic Host Configuration Protocol (DHCP)
Automated configuration of IP address, subnet mask, and other options
udp/67, udp/68
Requires a DHCP server
	Server, appliance, integrated into a SOHO router

Hypertext Transfer Protocol (HTTP)
Communicates in the browser
An by other applications
tcp/80 – HTTP
tcp/443 – HTTPS → with encryption

Simple Network Management Protocol (SNMP)
Gather statistics from network devices
	udp/161
SNMP traps
	Sends alerts and notifications from the network devices
	udp/162

Syslog
Standard for message logging
	Diverse systems, consolidated log
	udp/514
Usually a central log collector
	Intergrated into the SIEM
	Need a lot of storage space to store the logs

Remote Desktop Protocol (RDP)
Share a desktop from a remote location over tcp/3389
Can connected to an entire desktop or just a single application

Network Time Protocol (NTP)
Swiches, routers, firewalls, servers, workstations
	Every device has its own clock
	udp/123
Sychronizing the clocks becomes critical
	Log files, authentication information, outage details 

Session Initiation Protocol
Voice over IP (VoIP) signaling
	tcp/5060 and tcp/5061
Setup and manage VoIP sessions
	Call, ring, hang up
Extended voice communication 
	Voice conferencing, instant messaging, file transfer, etc. 

Server Mesage Block (SMB)
Protocol used by Miscrosoft Windows
	File sharing, printer sharing
	Also called CIFS (Common Internet File System)
Direct over tcp/445

Lightweight Directory Access Protocol (LDAP)
tcp/389
Store and retrieve information in a network directory

Databases
	Microsoft SQL Server
	MS-SQL (Miscrosoft Structured Query Language)
	tcp/1433

	Oracle SQL *Net
		Also called Oracle Net or Net8
		tcp/1521

Internet Control Message Protocol (ICMP)
“Text messaging” for your network devices

Generic Routing Encapsulation (GRE)
The “tunnel” between two endpoints
Encapsulate traffic inside of IP
	Two endpoints appear to be directly connected to each other
	No built-in encryption

Virtual Private Networks
Encrpted (private) data tranversin a public network
Concentrator
	Encryption/decryption access device
	Often integrated into a firewall
Many development options
	Specialized cryptographic hardware
	Software-basd options available
Used with client software
	Sometimes built into the OS




Internet Protocol Security (IPSec)
Security for OSI Layer 3
	Authentication and encryption for ever packet
Confidetiality and integrity/ anti-replay
	Encryption and packet signing
Very standardized
	Common to use multi-vendor implementations
Two core IPSec protocols
	Authentication Header (AH)
	Encapsulation Security Payload (ESP)
Authentication Header (AH)
	Hash of the packet and a shared key
		MD5, SHA-1, or SHA-2 are common
		Adds the AH to the packet header
Encapsulation Security Payload (ESP)
	Encryptes the packet
		MD5, SHA-1, or SHA-2 for hash, and 3DES or AES for encryption
	Adds a header, a trailer, and an Integrity Check Value

NETWORK ARCHITECHTURE 

Three-tier architecture
Core
	The “center” of the network
	Web servers, databases, applications
	Many people need access to this
Distribution
	A midpoint between the core and the users
	Communication between switches
	Manage the path to the end users
Access 
	Where the users connect
	End stations, printers

Software Defined Networking (SDN)
Networking devices have different functional planes of operation
	Data, control, and management planes
Split the functions into separate logical units
	Extend the functionality and management of a single device	
	Perfectly built for the cloud
Infractructer layer/data plane
	Process the network frames and packets
	Forwarding, trunking, encrypting, NAT
Control layer/ Control plane
	Managees the actions of the data plane
	Routing tables, session tables, NAT tables
	Dynamic routing protocol updates
Application layer/ Management plane
	Configure and manage the device

CLOUD MODELS

Infrastructure as a Service (IaaS)
Sometimes calles Hardware as a Service (HaaS)
Outsource your equipment 

Software as a Service (SaaS)
On-demand software
	No local installation
	Why manage your own email distribution? Or payroll?
Central management of data and applications
	Your data is out there
A complete application offering 
	No development work required
Example: Google Mail, office365

Platform as a Service (PaaS)
No servers, no software, no maintenance team, no HVAC
	Someone else handles the platform, you handle the development
You don’t have to direct control of the data, people, or infrastructure
	Trained security professionals are watching your stuff
A company gives you the building blocks and you put them together
	Develop your app from what’s available on the platform
Example SalesForce.com



Cloud deployment Models
Public
	Available to everyone over the internet
Community
	Several organizations share the same resources
Private
	You own virtualized local data center
Hybrid
	A mix of public and private

Desktop as a Service (DaaS)
Basic application usage
	Applications actually run on a remote server
	Virtual Desktop Infrastructure (VDI), 
Local device is a keyboard, mouse, and screen

DESIGNING THE CLOUD
Elasticity
	Scale up or down as needed


NETWORK IMPLEMENTATIONS
BALANCING THE LOAD
Distribute the load 
	Multiple servers
	Invisible to the end-user
Large-scale implementations
	Web server farms, database farms
Fault tolerance
	Server outages have no effect
	Very fast convergence
Intrusion Detection Systems/Intrusion Prevention System
	Watches network traffic
Proxies
Sits between the users and the external network
Receives the user requests and sends the request on their behalf
Useful for caching information, access control, URL filtering, content scanning

NETWORK OPERATIONS 

Simple Network Management Protocol (SNMP)
Internet Standard protocol for collecting and organizing information about managed devices on IP networks 
Traffic Logs
Views traffic information from routers, switches, firewalls, etc.
	Identify traffic flows
	View traffic summaries
Can be very detailed 
	Every flow from every device
Importance historical information
	Monitoring, post-event analysis

NETWORK SECURITY
CIA TRIAD
The fundamentals of security → Confidentiality, Integrity, Availability 

Confidentiality 
Prevents disclosure of information to unauthorized individuals or systems
Certain information should only be known to certain people
Use Encryption
Encode messages so only certain people can read it
Implement access controls
Selectively restrict access to a resource
Use steganography
Conceal information within another piece of information
Commonly associated with hiding information in an image		

Integrity
Messages can’t be modified without detection  
Data is stored and transferred as intended
	Any modification to the data would be identified
Use Hashing 
	Map data of an arbitrary length to data of a fixed length
Use digital signatures
	Mathematical scheme to verify the integrity of data
Use certificates
	Combine with a digital signature to verify an individual
Non-repudiation
	Provides proof of integrity, can be asserted to be genuine

Availability 
Systems and networks must be up and running
Information is accessible to authorized users
Always at your fingertips
Use redundancy
Build services that will always be available  
Fault tolerance 
	The system will continue to run, even when a failure occurs
Patching
	Stability, close security holes

SECURITY CONCEPTS

Vulnerabilities
A weakness in a system
	Allows the bad guys to gain access or cause a security breach
Some vulnerabilities are never discovered or discovered after years of use
Many different vulnerability types
	Data injection
	Broken authentication process
	Sensitive data exposure
	Security misconfiguration



Zero-day attacks
Many applications have vulnerabilities 
	We just haven't found them
Someone is working hard to find the next big vulnerability
	The good guys share these with the developer
Attackers keep these yet-to-be-discovered holes to themselves
	They want to use these vulnerabilities for personal gain
Zero-day
	The vulnerability has not been detected or published 
	Zero-day exploits are increasingly common

Threat
A threat can exploit a vulnerability
	It may be intentional (attacker) or accidental (fire, flood, etc)
	Many of these threats are external to the organization
A resource can have a vulnerability
	A threat agent can exploit the vulnerability 
	The threat agent takes a threat actor to exploit the vulnerability 
The result is a loss of security 
	Data breach, systems failure, data theft

Insider Threats
Implement a zero-trust policy

Vulnerability Databases
Researchers find vulnerabilities 
	Everyone needs to know about them
Common Vulnerabilities and Exposures (CVE)
	A community-managed list of vulnerabilities
Sponsored by the U.S. Department of Homeland Security (DHS) and Cybersecurity and Infrastructure Security Agency (CISA)  
U.S. National Vulnerability Database (NVD)
	A summary of the CVEs
	Also sponsored by DHS and CISA 
NDV provides additional details over the CVE list
	Patch availability and severity scoring

Exploits
Taking advantage of a vulnerability
	Gain control of a system
	Modify data
	Disable a service


Least privilege
Rights and permissions should be set to the bare minimum
	You only get exactly what’s needed to complete your objective
All user accounts must be limited
Applications should run with minimal privileges
Don’t allow users to run with administrative privileges 
Limits the scope of malicious behavior

Role-Based Access Control (RBAC)
You have a role in your organization
Administrators provide access based on the role of the user
Rights are gained implicitly instead of explicitly 
In Windows, use Groups to provide role-based access control
	Example: You are in the shipping and receiving, so you can use the shipping software
Example: You are the manager, so you can review shipping logs 	

Zero Trust
Many networks are relatively open on the inside
	Once you’re through the firewall, there are few security controls
Zero trust is a holistic approach to network security
	Covers every device, every process, and every person
Everything must be verified
	Nothing is trusted
Multifactor authentication, encryption, system permissions, additional firewalls, monitoring and analytics, etc

DEFENCE IN DEPTH
Layering The Defense
Physical controls
	Keep people away from the technology
	E.g. door locks, fences, cameras
Technical controls
	Hardware and software to keep things secure
	Firewalls, active directory authentication, disk encryption
Admintrative controls
	Policies and procedures
	Onboarding and offboarding 
	Backup media handling

Logical Segmentation with VLANs
Virtual Local Area Networks(VLANs)
	Separated logically instead of physically
	Cannot communicate between VLANs withough a Layer 3 device/ router

Screened subnet
Previously known as a Demilitarized zone (DMZ)
	An additionals layer of security between the internet and you
	Public access to public resources


Separation of duties
Split knowledge
	No one person has all the details
	Half of a safe combination
Dual control
	Two people must be present to perform the business function
	Two keys open a safe

Network Access Control
IEEE 802.X  - Port-based Network Access Control (NAC)
We’re talking about physical interfaces
	Not TCP or UDP ports
Makes extensive use of EAP and RADIUS
	EAP - Extensible Authentication Protocol
	RADIUS - Remote Authenitcation Dial In User Service
Administrator enable/disable
	Disable your unused ports
Check for duplicated MAC addresses

Honeypots
Attract the bad guys
	An trap them there
The “attacker” is probably a machine
	Makes for interesting recon
Honeypots
	Create  a virtual world to explore
