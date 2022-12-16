# OSI Model
Open Systems Interconnection (OSI) model is the most rigorously defined. There are 7 layers in the OSI model which has 2 layers between the transport and application layer. The fifth layer in the OSI model is the session layer and is responsible for faciliatating the communication between applications and the transport layer. It takes the application layer data that's been unencapsulated from all layers below, and hands it off to the presentation layer. The presentation layer is responsilbe for making sure that the unencapsulated application layer data is actually able to be understood by the application in question.

| #   | Layer Name                         | Protocol          | Protocol Data Unit | Addressing  |
| --- | ---------------------------------- | ----------------- | ------------------ | ----------- |
| 5   | [[application-layer\|Application]] | HTTP, SMTP, etc   | Messages           | NA          |
| 4   | [[transport-layer\|Transport]]     | TCP/UDP           | Segment            | Port #'s    |
| 3   | [[network-layer\|Network]]         | IP                | Datagram           | IP address  |
| 2   | Data Link                          | Ethernet, Wi-Fi   | Frames             | MAC address |
| 1   | Physical                           | 10 Base T, 802.11 | Bits               | NA          |
