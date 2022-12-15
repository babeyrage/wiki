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

