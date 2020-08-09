## Modelo OSI

- created by ISO
- universal language for computer networking
- based on a concept of seven layers each one stacked upon the next
- data flow from the top level layer (application layer) down the chain, each layer encapsulates the data add add its own information (PCI + SDU = PDU) as a "russian doll". When it arrives the destination it will be uncap.
- Each layer of the OSI model handles a specific job and communicates with the layers above and below itself. 
- Modern Internet doesn’t strictly follow the OSI model (it more closely follows the simpler Internet protocol suite).

---

- Apllication Layer
    - interacts with data from user.
    - software applications are not part of the application layer.
    -  is responsible for the protocols and data manipulation that the software relies on to present meaningful data to the user.

- Presentation Layer
    - makes the data presentable for  applications to consume (translation, encryption, and compression of data).

- Session Layer
    - responsible for opening and closing communication between the two devices.
    - the time between when the communication is opened and closed is known as the session.
    - synchronizes data transfer with checkpoints, meaning that when a big amout of data if beign transfered and a crash happens, it can resume from the last checkpoint.

 - Transport Layer
    - is responsible for end-to-end communication between the two devices. 
    - takes data from the session layer and breaking it up into chunks called segments before sending it to next layer.
    - responsible for flow control. Flow control determines an optimal speed of transmission to ensure that a sender with a fast connection doesn’t overwhelm a receiver with a slow connection.
    - performs error control on the receiving end by ensuring that the data received is complete, and requesting a retransmission if it isn’t.

 - Network Layer
    - is responsible for facilitating data transfer between two different networks.
    - if the two devices communicating are on the same network, then the network layer is unnecessary.
    - breaks up segments from the transport layer into packets, on the sender’s device, and reassembling these packets on the receiving device.
    - finds the best physical path for the data to reach its destination, "routing".

- Data Link Layer
    - facilitates data transfer between two devices on the SAME network.
    - takes packets and breaks them into frames.
    - responsible for flow control and error control in intra-network communication.

 - Physical Layer
    - includes the physical equipment involved in the data transfer, such as the cables and switches.
    - where the data gets converted into a bit stream, which is a string of 1s and 0s.

---


| Layer               | Protocols      |
|:-------------------:|:--------------:|
| application layer   | HTTP, FTP, DNS |
| presentation layer  | EBCDIC, NDR    |
| session layer       | SSH, RCP, SCP  |
| transport layer     | TCP, UDP       |
| network layer       | IP, IPX, ICMP  |
| data link layer     | Ethernet, FDDI |
| physical layer      |                |