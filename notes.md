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
