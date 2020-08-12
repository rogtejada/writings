## TCP/IP model (internet protocol suite)

- is named after two of the most common protocols – TCP (transmission Control Protocol) and IP (internet Protocol).
- designed and developed by department of Defense (DoD)
- provides end-to-end data communication specifying how data should be packetized, addressed, transmitted, routed, and received
- "concise" version of the OSI model, consists of four layers


---
- Layers

    - Application
        - defines standard Internet services and network applications that anyone can use.
        - application + presentation + session of OSI.
    - Transport
        - establishes basic data channels that applications use for task-specific data exchange.
        - provides end-to-end message transfer services that are independent of the structure of user data and the logistics of exchanging information for any particular specific purpose and independent of the underlying network.
        - The protocols in this layer may provide error control, segmentation, flow control, congestion control, and application addressing (port numbers).
        - transport of OSI
    - Networking
        - sends data from the source network to the destination network(routing).
        -  has the responsibility of sending packets across potentially multiple networks. With this functionality, the internet layer makes possible internetworking, the interworking of different IP networks, and it essentially establishes the Internet.
        - network of OSI
    - Datalink
        - provides error control and "framing".
        - data link of OSI


---


| Layer            | Protocols       |
|:----------------:|:---------------:|
| application      | HTTP, FTP, SMTP |
| transport        | TCP, UDP        |
| networking       | IP, ICMP        |
| datalink         | Ethernet, ARP   | 