# Transport Layer
Responsible for important functions of reliable computer networking, such as multiplexing and demultiplexing traffic, establishing long running connections and ensuring data integrity through error checking and data verification. Handles multiplexing and demultiplexing through ports, which are 16-bit numbers used to direct traffic to specific services running on a networked computer.

### TCP segment
Made up of a TCP header and a data section

![[tcp segment.png]]

| **Segment Part**          | **Size**    | **Function**                                                                                         |
| --------------------- | ------- | ------------------------------------------------------------------------------------------------ |
| Source port           | 16-bits | source port of packet                                                                            |
| Destination port      | 16-bits | destination port for packet                                                                      |
| Sequence number       | 32-bits | used to keep track of where in a sequence of TCP segments the specific segment is supposed to be |
| Acknowledgment number | 32-bits | is the number of the next expected segment                                                       |
| Data offset           | 4-bits  | communicates how long the TCP header for the segment is                                          |
| Control flags         | 6-bits  |                                                                                                  |
| TCP window            | 16-bits | specifies the range of sequence numbers that might be sent before an acknowledgement is received |
| Checksum              | 16-bits | checksum of the contents of the entire TCP segment                                               |
| Urgent                | 16-bits | used to point out particular segments that might be more important than others                   |
| Options               |         |                                                                                                  |
| Padding               |         | sequence of zeros to ensure that the data payload section begins at the expected location                                                                                                 |

### TCP Control Flags & Three-way Handshake
TCP establishes connections, through the use of different TCP control flags used in a very specific order, to send long chains of segments of data. 

1. URG (Urgent): indicates that the segment is urgent
2. ACK (Acknowledge): value of one in this field means that the acknowledgement fields should be examined
3. PSH (Push): the transmitting device wants the receiving device to push currently-buffered data to the application on the receiving end as soon as possible
4. RST (Reset): one side in a TCP connection hasnt been able to properly recover from a series of missing or malformed segments
5. SYN (Synchronize): used when first establishing a TCP connection, and makes sure the receiving end knows to examine the sequence number field
6. FIN (Finish): when set to one, the transmitting computer doesnt have any more data to send and the connection can be closed

![[three-way-handshake.png]]

### TCP Socket States
A socket is the instantiation of an endpoint in a potential TCP connection.

States:
1. LISTEN - TCP socket is ready and listening for incoming connections
2. SYN_SENT - synchronisation request has been sent, but the connection hasnt been established yet
3. SYN_RECEIVED - socket previously in a listener state has received a synchronisation request and sent a SYN_ACK back, but hasnot received the final ACK from the client
4. ESTABLISHED - TCP connection is in working order and both sides are free to send each other data
5. FIN_WAIT - FIN has been sent, but the corresponding ACK from the other end hasnt been received yet
6. CLOSE_WAIT - the connection has been closed at the TCP layer but the application hasnt released its hold on the socket
7. CLOSED - connection has been fully terminated and no further communication is possible

### Connection-oriented and Connectionless Protocols
Connection-oriented protocol establishes a connection and uses this to ensure that all data has been properly transmitted. Connectionless protocols doesnt rely on connections and doesnt support the concept of an acknowledgement.