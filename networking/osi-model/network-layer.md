# The Network Layer

## IP Addresses

32-bit long numbers made up of 4 octet - 8 bits of data (1 octet) represents number 0 - 255

### IP Datagrams & Encapsulation

Highly structured series of fields that are strictly defined.

2 primary sections are header and payload

![[ipdatagram.png]]

| Datagram Part      | Length  | Definition                                                                                                                   |     
| ------------------ | ------- | ---------------------------------------------------------------------------------------------------------------------------- | 
| Version            | 4-bits  | indicates what version of IP is being used                                                                                   |    
| Header Length      | 4-bits  | indicates how long the entire header is. 20 bytes is the minimumed length of an IP header                                    |     
| Service Type       | 8-bits  | used to specifiy details about quality of service technologies                                                               |     
| Total Length       | 16-bits | indicates the total length of the IP datagram its attached to                                                                |     
| Identificaton      |         | contains information so that the receiving end knows that every packet with the same value is part of the same transmission  |     
| Flag               |         | indicates if a datagram is allowed to be fragmented, or if it has already been fragmented                                    |     
| Fragment Offset    |         | contains values used by the receiving end to take all parts of a fragmented packet and reconstruct them in the correct order |     
| Time to Live (TTL) | 8-bits  | indicates how many router hops a datagram can traverse before its thrown away                                                |     
| Protocol           | 8-bits  | contains data on what transport layer protocol is being used                                                                 |     
| Header Checksum    |         | checksum of the contents of the entire IP datagram header                                                                    |     
| Source IP          | 32-bits | source IP                                                                                                                    |     
| Destination IP     | 32-bits | destination IP                                                                                                               |     
| Options            |         | is optional and used to set special characteristics for datagrams                                                            |     
| Padding            |         | set of zeros to ensure the header is the correct total size                                                                  |                                                                                                                                  |     |     |

### IPv4 Address Classes

There are 3 primary types of address classes:

1. Class A: addresses where the **first octet** is used for the network ID - has 24-bits of host ID space - 16,777,216 different addresses - adddresses begin with 0 - 127
2. Class B: addresses where the **first 2 octets** are used for the network ID - addresses begin with 128 - 191
3. Class C: addresses where the **first 3 octets** are used for the network ID - has 8-bits of host ID space - 256 different addresses - addresses begin with 192 - 223
4. Class D: multicasting IPs - addresses begin with 224 - 239
5. Class E: unassigned IPs - addresses begin with 240 - 255

### Address Resolution Protocol (ARP)

A protocol used to discover the hardware address of a node with a certain IP address.