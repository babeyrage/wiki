IP address is a layer 3 logical address assigned by an administrator, and used to identify specific devices on a network. An IP address is a 32bit number, comprised of 4 binary octets. 

IPv4:
* Layer 3 or network layer protocol
* Connectionless Protocol
	* TCP is connection oriented
* Packets treated independently
	* may take different paths 
		* Load balancing
		* Bandwidth
		* Hop-count
* Hierarchical addressing structure to enable routing
	* Network and Host portion
* Best effort delivery 
* No data recovery features 

Network Address Portion (Network ID):
* identifies a specific network
* routers maintain routing tables that contain the network
* look at destination of IP address and match to network address

Host Address Portion (Host ID):
* identifies a specific endpoint on a network
* server, printers, PCs etc

Address Classes:
* Class A, B & C - unicast traffic
* Class D - multicast traffic
* Class E - reserved for future or experimental purposes

Class A:
* Start with a binary 0
* Binary range: 0.0.0.0 to 127.255.255.255 / actual range: 1.0.0.0 to 126.255.255.255
* 127.0.0.1 is reserved for loopback address
* First octet denotes the network, and the remaining 3 octets denote the hosts

Class B:
* Starts with binary 10 (1 & 0 not 10)
* Binary range: 128.0.0.0 to 191.255.255.255
* First 16 bits denotes the network, and the last 2 octets denotes the hosts