## UDP (User Datagram Protocol)

- connectionless protocol
- unreliable
- speeds up communications by not requiring what’s known as a “handshake”, allowing data to be transferred before the receiving party agrees to the communication. This allows the protocol to operate very quickly, and also creates an opening for exploitation.
- commonly used in time-sensitive communications where occasionally dropping packets is better than waiting. Voice and video traffic are sent using this protocol because they are both time-sensitive and designed to handle some level of loss.
- doesn’t have the error checking and ordering functionality
- divides messages into packets, called datagrams, which can then be forwarded by the devices in the network – switches, routers, security gateways – to the destination application/server. While UDP does not number or reassemble the datagrams, it does include port numbers in the datagram header that help distinguish different user requests and an optional checksum capability that can help verify the integrity of the data transferred.