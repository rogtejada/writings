## TCP (Transmission Control Protocol)

- Connection-oriented protocol, connection is established and maintained until the application programs at each end have finished exchanging messages.
- reliable protocol, because the protocol ensures that all data is fully transmitted and can be assembled by the receiver in the correct order.
- positioned at the transport layer (layer 4) of the OSI model.
- allows data to be sent in individual segments of up to 1,500 bytes (including headers) in size.
- stablish a connection that enables a two-way transmission of data.
- The TCP stack divides the file into data packets, numbers them and then forwards them individually to the IP layer for delivery. Although each packet in the transmission has the same source and destination IP address, packets may be sent along multiple routes. The TCP program layer in the client computer waits until all the packets have arrived, then acknowledges those it receives and asks for the re-transmission of any it does not -- based on missing packet numbers. The TCP layer then assembles the packets into a file and delivers the file to the receiving application.
- used for organizing data in a way that ensures the secure transmission between the server and client. It guarantees the integrity of data sent over the network, regardless of the amount.
- Three way handshake (SYN, SYN/ACK, ACK) to establish connection
- Both sides of a connection can terminate a TCP connection, and even one-sided termination is also possible. This is also known as a half-open connection, whereby the other side is still allowed to transfer data even if one side has already disconnected.
- two-way termination (FIN, ACK, FIN, ACK)