## DNS (Domain name System)

- convert "domain name" to IP

- DNS resolver
    - receives the query from client
    - do series of requests until it reaches the authoritative nameserver
- root nameserver
    - first step into resolving host into ip
    - 13 in the world, will answer with address for tld
- top level domain nameserver
    - it hosts the last portion of a hostname (com)
    - will answer with address for authoritative nameserver
- authoritative namerserver
    - the final nameserver, last step
    - return the ip address for the requested hostname back to the DNS resolver
- subdomain nameserver(can exist)

- 8 steps
    1 - A user types ‘example.com’ into a web browser and the query travels into the Internet and is received by a DNS recursive resolver.

    2 - The resolver then queries a DNS root nameserver.

    3 - The root server then responds to the resolver with the address of a Top Level Domain (TLD) DNS server (such as .com or .net), which stores the information for its domains. When searching for example.com, our request is pointed toward the .com TLD.

    4 - The resolver then makes a request to the .com TLD.

    5 - The TLD server then responds with the IP address of the authoritative domain’s nameserver, example.com.

    6 - Lastly, the recursive resolver sends a query to the authoritative domain’s nameserver.

    7 - The IP address for example.com is then returned to the resolver from the nameserver.
    
    8 - The DNS resolver then responds to the web browser with the IP address of the domain requested initially.

- Often DNS lookup information will be cached either locally inside the querying computer or remotely in the DNS infrastructure.
        
https://www.cloudflare.com/learning/dns/what-is-dns/




