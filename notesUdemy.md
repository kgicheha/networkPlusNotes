
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
