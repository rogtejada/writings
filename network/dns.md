## DNS (Domain name System)

- is a standard protocol that helps Internet users discover websites using human readable addresses
- convert "domain name" to IP
- server's ip can change without affecting end users
- when a new domain name is registered there is a propagation time to dns servers world-wide to be updated
- allows for multiple hostnames to correspond to a single IP address - this can be used for virtual hosting, when many websites are served from a single host. A single hostname can also resolve to many IP addresses, in order to distribute load to multiple servers.
- Typically, when you connect to a local network, Internet service provider (ISP) or WiFi network, the modem or router sends network configuration information to your local device, including one or more DNS servers. These are the initial DNS servers your device will use to translate host names to IP addresses.
- DNS Resolver is responsible for checking if the host name is available in local cache, and if not, contacts a series of DNS Name Servers, until eventually it receives the IP of the website or service you are trying to reach. (DNS resolution of a hostname to IP address)


---

- DNS resolver
    - also called a recursive resolver
    - receives the query from client (browser and other applications for example)
    - receives a hostname - for example, www.example.com - and is responsible for tracking down the IP address for that hostname.
    - starts by looking in its local cache or that of the operating system on the local device - if the hostname is found, it is resolved immediately.
    - If not found inside the cache, do series of requests until it reaches the authoritative nameserver
- root nameserver
    - first step into resolving host into ip
    - 13 in the world
    - will answer with address for tld
- top level domain nameserver
    - it hosts the last portion of a hostname (.com, .org)
    - will answer with address for authoritative nameserver
- authoritative namerserver
    - the final nameserver, last step
    - return the ip address for the requested hostname back to the DNS resolver
- subdomain nameserver(can exist)

---

- Types of DNS Queries

    - Recursive query: 
        - In a recursive query, a DNS client requires that a DNS server (typically a DNS recursive resolver) respond to the client with either the requested resource record or an error message if it can't find the record.
    - Iterative query: 
        - the DNS client allows a DNS server to return the best answer it can. If the queried DNS server does not have a match for the hostname, it returns a referral to an Authoritative DNS Server at a lower level of the DNS hierarchy. The DNS client then makes a query to the referral address. This process continues with additional DNS servers down the query chain until either an error or timeout occurs.
    - Non-recursive query: 
        - this occurs when a DNS Resolver queries a DNS Name Server for a record, either because the Name Server is authoritative for the record, or the record exists in its cache. DNS servers typically cache DNS records to conserve bandwidth and reduce load on servers further up the hierarchy.

---

- Transfer Protocol
    - DNS primarily uses UDP on port number 53 to serve requests. DNS queries consist of a single UDP request from the client followed by a single UDP reply from the server. TCP is used as fallback, when the response data size exceeds 512 bytes, or for zone transfers. Some DNS resolvers use TCP for all communication.

---

- 8 steps

    1 - A user types ‘example.com’ into a web browser and the query travels into the Internet and is received by a DNS recursive resolver.

    2 - The resolver then queries a DNS root nameserver.

    3 - The root server then responds to the resolver with the address of a Top Level Domain (TLD) DNS server (such as .com or .net), which stores the information for its domains. When searching for example.com, our request is pointed toward the .com TLD.

    4 - The resolver then makes a request to the .com TLD.

    5 - The TLD server then responds with the IP address of the authoritative domain’s nameserver, example.com.

    6 - Lastly, the recursive resolver sends a query to the authoritative domain’s nameserver.

    7 - The IP address for example.com is then returned to the resolver from the nameserver.

    8 - The DNS resolver then responds to the web browser with the IP address of the domain requested initially.




