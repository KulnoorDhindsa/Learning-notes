# DNS - The Internet's Directory Service
DNS describes the distributed database and protocol used to translate human-friendly hostnames into the IP addresses that network routers require to identify and locate end systems.
## Services provided by DNS
DNS is application-layer protocol running iver **UDP** on **port 53**
- **Hostname-to-IP-address Translation**: Allows applications like browsers to find 32-bit IP address associated with a URL like `www.example.com`
    - **IP Address** is a 32-bit address containg of 4 bytes, seperated by `.`, each byte between 0 - 255
- **Host Aliasing**: A host can have one **canonical hostname** and one or more **alias names**, which are often more mnemonic
- **Mail Server Aliasing**: DNS allows a company's mail server and Web server to have identical aliased hostnames (e.g. `enterprise.com`), while using different canonical names for the actual mail handling
- **Load Distribution**: For busy sites replicated over multiple servers, DNS can associate a set of IP addresses with one canonical hostname, rotating the order of addresses in each reply to distribute traffic among servers

## How DNS works
DNS is **distributed, hierarchial database** because a single, centralized server would not scale to the size of the modern Internet.
- **The Hierarchy**:
    - **Root DNS Servers**: There are 13 root servers (clusters of replicated servers) that provide the IP addresses of TLD servers
    - **Top-Level Domain (TLD) Servers**: These are responsible for generic domains like `.com`, `.org`, `.edu` and country domains like `.uk` and `.fr`.
    - **Authoritative DNS Servers**: These house the actual DNS records that contain an organization's hostname to IP addresses
- **Local DNS Servers**: While not strictly part of the hierarchy, these act as proxy for hosts (provided by ISPs), forwarding the queries into the hierarchy to resolve addresses
- **Query Types**: Queries can be **recursive** (client requests server to find the answer itself) or **iterative** (the server returns the address (as a referral) of the next server in the chain for the client to contact rather than giving final answer)
- **DNS Caching**: To improve performance and reduce traffic, DNS servers cache mappings they recieve; these are usually discarded after couple of days

>**DNS Poisoning**: A security attack where an attacker sends bogus records to a DNS server to trick into caching false information.

## DNS Records and Messages
The database stores **Resource Records (RRs)** (basic unit of information), which are four-tuples containing: `(Name, Value, Type, TTL)`.
- **Type A**: Name is a hostname, Value is its IP address
- **Type NS**: Name is a domain, Value is the hostname of an authoritative server for that domain
- **Type CNAME**: Name is an alias, Valuse is the canonical hostname
**Type MX**: Name is an alias, Value is the canonical name of a mail server

DNS messages (*queries and replies*) share a unified format consisting of header, a question section, an answer section, an authority section, and an additional informaiton section