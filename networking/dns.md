# DNS (Domain Name System)
- DNS, the Internet's *directory service* is the *distributed database* and *protocol* used to translate human-friendly hostnames into the IP addresses that network routers require to identify and locate end systems.
---
## Services Provided by DNS

> DNS is an *application-layer* protocol that runs over **UDP** on **port 53** (falling back to TCP for larger responses).

- **Hostname-to-IP-Address Translation**: Lets application-layer protocols like HTTP, SMTP, and FTP resolve a hostname (e.g. `www.example.com`) to the 32-bit IP address needed to open a connection.
    - **IP address**: a 32-bit number consisting of 4 bytes separated by `.`, each byte ranging from 0 to 255.
    - Resolution flow:
```mermaid
      graph LR
         A[Client requests<br/>hostname resolution] --> B[Browser extracts<br/>hostname]
         B --> C[Client sends query<br/>to DNS server]
         C --> D[Server replies<br/>with IP address]
         D --> E[Browser connects<br/>via TCP:80]
```
- **Host Aliasing**: A host can have one **canonical hostname** and one or more **alias names** that are typically easier to remember.
- **Mail Server Aliasing**: DNS lets a company's mail server and web server share the same alias (e.g. both reachable via `enterprise.com`), even though each maps to a different canonical hostname behind the scenes.
- **Load Distribution**: For a site replicated across multiple servers, DNS maps one canonical hostname to a *set* of IP addresses, rotating their order in each reply to spread traffic across the replicas.
---
## How DNS works
DNS is **distributed, hierarchial database** because a single, centralized server would not scale to the size of the modern Internet.
- **The Hierarchy**:
    1. **DNS Recursor (Resolver)**: Recieves intial query from web browser; tracks IP address; caches answers for quick responses in the future; thus is like librarian for computer
    - **Root DNS Servers**: There are 13 root servers (clusters of replicated servers) that provide the IP addresses of TLD servers
    - **Top-Level Domain (TLD) Servers**: These are responsible for generic domains like `.com`, `.org`, `.edu` and country domains like `.uk` and `.fr`.
    - **Authoritative DNS Servers**: These house the actual DNS records that contain an organization's hostname to IP addresses
- **Local DNS Servers**: While not strictly part of the hierarchy, these act as proxy for hosts (provided by ISPs), forwarding the queries into the hierarchy to resolve addresses
- **Query Types**: Queries can be **recursive** (client requests server to find the answer itself) or **iterative** (the server returns the address (as a referral) of the next server in the chain for the client to contact rather than giving final answer)
- **DNS Caching**: To improve performance and reduce traffic, DNS servers cache mappings they recieve; these are usually discarded after couple of days

>**DNS Poisoning**: A security attack where an attacker sends bogus records to a DNS server to trick into caching false information.
---
## DNS Records and Messages
The database stores **Resource Records (RRs)** (basic unit of information), which are four-tuples containing: `(Name, Value, Type, TTL)`.
- **Type A**: Name is a hostname, Value is its IP address
- **Type NS**: Name is a domain, Value is the hostname of an authoritative server for that domain
- **Type CNAME**: Name is an alias, Valuse is the canonical hostname
**Type MX**: Name is an alias, Value is the canonical name of a mail server

DNS messages (*queries and replies*) share a unified format consisting of header, a question section, an answer section, an authority section, and an additional informaiton section


