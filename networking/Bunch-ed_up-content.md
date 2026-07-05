# Computer Networking - A Top Down Approach

# Chapter 1 - Computer Networks and The Internet
## 1.1 What is the internet?
**End Systems / Hosts**: Devices connected to the internet, they sit at the edge of the Internet.

They are called *Hosts* as the host (or run) various application progams such as Web server programs.

**Communication Links**: The physical media (copper wires, radio waves etc) through which data travels between different end systems.

**Transmission Rate**: Speed of a link, measured in *bits per second(bps)*.

**Packets**: Chunks of data sent by a sender end system with *header bytes*.

*Header bytes*: Initial bytes that contain meta data of the packet (Sender's IP, reciever's IP etc).

**Packet Switches**: Devices like *routers* and *link-layer switches* that forward packets from *incoming communication links* to *outgoing communication links*.

*Route / Path*: Sequence of different end systems, packet switches, communication links followed by a packet.

**Internet Service Provider**: The network of packet switches and links through which end systems access the Internet.
|ISP Tiers|Examples|How they connect|
|---------|--------|----------------|
|Tier 1|AT&T, Lumen, NTT|Own global backbone|
|Tier 2|Regional ISPs, large nationals|Pay Tier 1 for upstreams access|
|Tier 3|Local IP/home ISP|Pay Tier 2 for transit, sell to end users|

*Transit*: The right to send traffic through their network to reach the global internet.

**Protocols**: The set of rules that control the format and order of messages sent and received within the network.

Same protocols need to be followed by different end systems on the Internet for various interoperations.

**Request for Comments(RFCs)**: Technical standards document developed by the Internet Engineering Task Force(IETF).

**Distributed Applications**: Applications involving multiple end systems that exchange data with each other.

**Application Programming Interface(API)**: A set of rules specifying how a program on one end systems asks the Internet to deliver data to another end system.

## 1.2 The Network Edge
*Hosts* or *End systems* are of 2 types:
1. **Clients**: Category of end systems that include dsektop, mobile PCs, smartphones and other user-facing devices.
2. **Servers**: More powerful machines that store and distribute content like Web pages, streaming video and e-mail.

### Internet Access
**Access Networks**: The physical network that connects end sytem to the firt router (*edge router*) on a route to other end systems.

Ways for end systems to gain Internet Acess at **HOME**: 
1. **Digital Subscriber Line(DSL)**: Residential broadband access that uses existing twisted-pair telephone lines to transmit data at different frequencies than traditional phone calls on the same twisted-pair copper wire.
    - *higher frequency*: exploited for DSL data (higher frequency has higher bandwidth capacity, ideal for internet data).
    - *lower frequency*: voice calls, as human voice only physically produces sound in this range.

**Digital Subscriber Line Access Multiplexer**: combines different copper lines and converts DSL signals into IP packets.
```
Internet Backbone
      ↓
   DSLAM  (sits at the telephone exchange, aggregates lines, connects to ISP backbone)
      ↓
  Copper twisted-pair phone line  (the local loop, carries voice + data simultaneously)
      ↓
  Splitter  (separates voice 0-4kHz from data 25kHz-1.1MHz)
      ↓
  DSL Modem  (converts high frequency signals into digital data for the router to understand)
      ↓
  Router  (distributes internet to all devices on local network)
      ↓
  Your devices
  ```
  2. **Cable Internet Access**: Residence obtains internet access from teh same company that provides television network.

**Cable Modem Termination System** is analogus to DSLAM, turns analog signals from cable modems into digital format.

**Hybrid Fiber Coax(HFC)**: A broadband network using **fiber optic cable** for backbone (from ISP's headend to home distribution points), then switches to **coaxial cable** into homes and businesses.
- *fiber* carries massize bandwidth for long distances with near-zero signal degradation, but is very expensive to use everywhere.
- Data via HFC is controled by **Data Over Cable Service Interface Specification(DOCSIS)**. 

Coax is a **shared medium**. Frequency is split accordingly:

|Direction|Frequency|Used For|
|----------|------------------|--------------------|
|Downstream|*higher frequency*|Data coming to you|
|Upstream  |*lower frequency* |Data you upload/send|

3. **Fibre To The Home(FTTH)**: An accss technology that provides optical fiber connection directly from central office(CO) to the home.

One fiber leaves the CO, then after reaching close to the homes, it **splits** into home-specific wires via the following two network architechtures:

|**Active Optical Network(AON)**|**Passive Optical Network(PON)**|
|-------------------------------|-------------------------------|
|Electrically active (uses routers and power switches)|Electrically passive (uses unpowered slitters)|
|Dedicated to one user|Shared among many people|
|Larger range (about 100km)|Lower range (about 20-30km)|

4. **Satellite Link**: Areas where DSL, cable and FTTH can't reach, satellite links connect residence to the internet.

Ways for end systems to gain Internet Acess at **Work/Enterprise**:
5. **Ethernet**: Nost prevelant LAN access technology in corporate.

6. **Wireless**: User be wihin tens of kilometers range for wireless transfer of data via cellular telephone network.

Multiple generation wireless (3G, 4G, 5G etc) have been developed with packet-switched wide area wireless Internet access.

### Physical Media
Refers to the mediums (of various shapes, sizes and materials) a bit travels between transmitter-reciever pairs.
- **Guided Media**: Electromagnetic waves are guided along a solid medium (eg. twisted copper wires, fiber optic cables etc).
- **Unguided Media**: Waves propagate in the atmosphere (eg. LAN, satellite links etc).

Common physcial media includes: 
- Twisted-Pair Copper Wire
- Coaxial Cable (guided shared mediums)
- Fiber Optics
- Radio Channels (no physcial medium reqwuired; various types based off of range)
- Satellite Radio Channels ()

|Geostationary Satellites|Low-Earth Orbiting Satellites (LEO)|
|------------------------|-----------------------------------|
|Remain permanently above fixed spots on Earth by revolving in orbit at 36,000 km above Earth's surface|Placed closer to Earth, not upon fixed spots|

## 1.3 The Network Core

### Packet Switching
Data is brocken into smaller chunk 

**packets** to send messages from source to reciever end system.

Packet switches have two main types: **routers** and **link-layer switches**.

- **Store-and-Forward Transmission**: Packet switches require entire packet to be delivered before sending first bit of data through the outbound link.
- **Output buffer**/**Output Queue**: A storage area in a packet switch that stores packets that the router is about to send out.
- **Queuing Delays**: If a packet is to be sent out from an outbound link, but the link is busy with transmission of another packet, the new packet has to wait, thus the delay.
- **Packet Loss**: If the buffer space is all occupied, the new packet has no where to be stored, thus either the arriving packet or already-queued packet will be dropped.
- **IP address**: Address of every end system on the Internet.
- When source end system sends a packet of information, it includes *packet header* which has meta data of that packet, including iIP address of the destination end system. Thus, router knows which communication link to send that packet to.
- **Forward Table**: A data structure in the router that maps destination IP prefixes.
- **Routing Protocols**: Automatically set 
the forwarding tables.

>The Internet is a packet-switching network.

### Circuit Switching
Resources equired (links, transmission rates) are *reserved* before commuinications starts between two end systems.

**Circuit**: A dedicated end-to-end connection established between two hosts when the network reserves a **constant transmission rate** for the duration of the session.

Circuit is efficiently implemented by either of the following two ways:

|**Frequency-Division Multiplexing(FDM)**|**Time-Division Multiplexing(TDM)**|
|-------------------|-----------------|
|Method of implementing a circuit by *dividing the frequency spectrum* of a link into bands, with each band dedicated to a specific connection|Method where *time is divided into frames* of fixed duration, and each frame is divided into time slots; each connection is dedicated one time slot in every frame|

### Network Of Networks
Network of Network refers to the connection of billions of ISPs across the Internet. ISPs include not only telephone or cable companies, but also any type of access provider (eg. universities providing WiFi to students).

**Regional ISPs**: ISPs of a specified region.

**Tier-1 ISPs**: Similar to global transit ISPs, but not present in every city.
Eg, AT&T. Sprint and NTT.

**Point of Presence(PoP)**: A goup of one or more routers in a provider's network where customer ISPs connect to the provider.

**Multi-homing**: The practice of ISP connecting to **two or more** provider ISPs to ensure continued service.

**Peering**: Agreement where nearby ISPs at similar level directly connect their networks to exchange traffic settlement free(**without paying eachother**).

**Internet Exchange Point(IXP)**: Physical meeting points where multiple ISPs peer together.

**Content Povider Networks**: Private networks operated by companies like Google to distribute content to end users while bypassing upper tiers of public interest.

## 1.4 Delay, Loss and Throughput in Packet-Switched Networks

### Delays
**Nodal Delay**: Total delay experienced by packet at a node (router) which is sum of processing, queung, transmissiom and propagation delay.

**Processing Delay**: The time required for a router to examine the packet's header and determine where to direct it. It also includes the time to check for bit-level errors.

**Queung Delay**: The time a packet spends in a queue (buffer) to be transmitted onto a link. Delay ranges from zero to milliseconds based on traffic congestion.

**Transmission Delay**: Time required to transmit all packet bits into the link. It ranges from microseconds to milliseconds.

**Propagation Delay**: Time taken for a bit to travel from beginning of a link to the next router or host. Depends largely on physical medium material.

Other delays include:
- End systems *purposefully* delay sending a packet into *shared medium* as part of protocol.
- **Media Packetization Delay**: Majorly in Voice-over-IP (VoIP), sending end system encodes digitized speech before passing it to the Internet. Time taken for this digitization causes integral delay in packet transmission.

>Propagation Delay is calculated by dividing distance of link by propagation speed of the medium.

**Traffic Intensity**: The ratio *La/R*, where *L* is packet size, *a* is average packet arrival rate, and *R* is transmission rate. Estimates extent of queuing delay.

>If traffic intensity > 1, then the queue will grow without bound.

### Losses
**Packet Loss**: Occurs when a packet arrives at a router's buffer that is already full. With no place to store packet, router **drops** (looses) it.

### Throughput in Computer Networks
**Throughput**: Rate ( bits/second) at which destination host recieves file from sender host.

**Bottleneck Link**: The line in a network path that has the lowest transmission rate, thereby limiting the end-to-end throughput for a file transfer.

## 1.5 Protocol Layers and Their Service Models
**Layering**: Structural process organises functionality of complex systems by dividing them into a series of horizontal levels.
- **Service Model**: Each layer, combined with layers below it, performs services and executes internal actions.
- **Modularity**: Internal implementation can be modifed as long as it provides the **same services** and uses the **same services provided from below layer**.
- **Encapsulation**: (In networking) Each layer receives a **payload** (data) from above, appends its own **header fields** and passes teh resulting package to next layer as new payload.

### Layer Architecture
**Protocol Stack**: The collective name given to protocols belonging to various layers

**Internet Protocol Stack**: The five-layer architecture that organizes the Internet, consists of - **application, transport, network, link and physical layers**.
1. **Application Layer**: The top layer where network applications and their protocols reside. Data at this layer is called **message**. Protocols at this level include:
    - **HTTP** (provides for Web document requst and transfer)
    - **SMTP** (provides for transfer of e-mail messages)
    - **FTP** (provides for transfer of files between two end systems)
2. **Transport Protocol**: Transports application-layer messages between endpoints. Data at this level is called **segment**. Protocol at this level are only two:
    - **TCP** (connection oriented service; flow control; breaks messages intro shorter segments)
    - **UDP** (connectionless service; no flow control; no connection control)
3. **Network Layer**: Moves **datagrams** from one host to another. Protocols at this layer include:
    - **IP** (defines fields in datagrams)
    -*routing protocols* (determine routes taken by datagram between two end systems)
4. **Link Layer**: Responsible for moving packets from one node to the next over a single communication link (eh, Ethernet, WiFi). Data at this level is **frame**.
5. **Physical Layer**: Moves the individual bits within the frame from one node to the next over physical medium.

**OSI RReference Model**: A seven-layer model developed by ISO. In addition to the five Internet layers, it includes the **Presentation Layer** (data interpretation/encryption) and the **Session Layer** (synchronization and recovery).

**Encapsulation**: The process where each layer adds its own **header fields** to the data (**payload**) recieved from the layer above it.

## 1.6 Network Under Attack
**Malware**: Software designed to damage, disrupt or gain unautherized access to a computer system

### Types of Malware (By Spreading Method)
1. **Viruses**: Require user interaction
    - Eg: email attachement containing executable code
    - Often *self-replicating*
2. **Worms**: Don't require specific user interaction
    - Exploits vulnerability in a network application or OS
    - Scans Internet for other hosts running on same vulnerable application

### Types of Malware (By Malicious Activities)
1. **Spyware**: Collects private information from device
    - Eg: collecting passwords, even keystrokes and sending them back to the attacker
2. **Botnet Enrollment**: A compromised host maybe  enrolled in a 'botnet', network of many similarly infected devices
    - **Distributed Denial-of-Service (DDoS)** attacks maybe launched in botnets against other targets.

**Denial-of-Service (DoS) Attacks**: Attacks intended to make a network or server unusable for legitimate users, often by flooding it with traffic.

**Packet Sniffing**: Placing a passive reciever near a transmitter to record copies of every packet flying by, thus revealing sensitive data to the attacker.

**IP Spoofing (Masquerading)**: The specific ability to hand-craft a packet with an arbitrary source address to trick a receiver into believing the message orignated from a trusted source.

## 1.7 History of Computer Networking and the Internet

**Initial Theory**: Telephone network (circuit-switched) dominated, but computers needed *burst of traffic*.

**ARPnet**: The precursor to the Internet, funded by US Defence Research Agwncy (ARPA).

**Network Prolification**: New networks emrged, including **ALOHANet** (a microwave network in Hawaii), DARPA's packet-satellite and radio networks, and teh French **Cyclades**>

**Kahn Principles**: 
- **BEst-effort delivery**: No reliability guarantees at the network layer
- **Stateless routers**: Routers do not maintain state for individual connections
- **Decentralized control**: No global authority managing the network

TCP/IP became official protocol for ARPNet on **Jan 1, 1983**, replacing older NCP.

**Domain Name System (DNS)** was developed to manage hostnames.

**Minitel** was a large-scale data network deployed in France, years before Internet became common.

**The World Wide Web** invented by **Tim Bernerd-Lee**, introduced HTML, HTTP and Web servers/browsers.

The Web was made accessible to non-technical-users by devopment of Mosaic browser (Netscape).

Aggressive deployment of DSL, Cable, **Fiber-to-the-Home (FTTH)** replaces slower dial-up access.

High speed WiFi and cellular data made it possible to stay connected.

Companies like **Google and Microsoft** built private networks to bypass upper-tier ISPs and deliver content almost instantaneously to end users.
---

# Chapter 2 - Application Layer
**Application Architecture**: Designed by developer to define how the application is structured across different end systems

Application Architecture is of mainly two types:
1. **Client-Server Architecture**: A paradigm where always-on host (*server*) services requests from other hosts (*clients*).
    - No direct communication amongst clients.
    - Servers have **fixed IP address** 
    - **Data Centers**: Large housing of hosts used to create powerful virtual server
2. **Peer-to-Peer (P2P)**: A paradigm with no reliance on dedicated servers; pair of intermittently connected hosts (**peers**) communicate directly with each other.
    - **self-scalable**: Peers are redistributors and consumers of bits.
3. **Hybrid Architecture**: Applications that combine both client-server and P2P elements (e.g. instant messaging using a server to track IP addresses but sending messages directly between users).

**Process** is a program that runs inside an end system.

Processes communicate with each other across teh INternet via **messaging**. Sending process creates and sends *messages* while recieving process recieves and responds by sending messages back.

In P2P file sharing, peer that downloads files is *client* ad peer uploading the files is *server*. So, same process can be a *client* and *server* too.

In terms of communication session, the process that *initiates* the communication is **client**, while the process waiting to be contacted is the **server**.

**Socket**: A software interface through which process sends and recieves messages from the Internet.
>Socket is interface between **applicatio layer** and **transport layer** within an end system.

>Socket is **Application Programming Interface (API)** between application and network layer.

**Addressing Processes**: To identify a recieving process, a sender must specify the **IP addredd** of the destination host and a **port number** that identifies the specific recieving process on that host.

Different services provided by *Transport Layer Protocol* to applications that invoke it include:
1. *Reliable Data Transfer: Transport Layer Protocol allows reliable data transfer with *no packet loss (due to over flowing buffer or packet being discarded owing to errors)
    - Certain *loss tolerant applications* don't mind packet loss (e.g. multimedia applications involving audio/video)
2. *Throughput*: Transport Layer Protocol would ensure that available throughput is always atleast a minimum amount requested by the application.
    - *Bandwidth-sensitive Applications*: Applications that require a minimum amount of throughput to be effective (e.g. Interent telephony)
    - *Elastic Applications*: Applicaitons that can use as much as or as little throughput as is available (e.g. e-mail, file tranfer)
3. *Timing*: Transport Layer Protocol provides timing guarantees to avoid unnatural pauses in conversations or long delays in action and required result.
4. *Security*: Transport Layer Protocol provided various security services to end systems including encryption and decryption in sending and recieving hosts.

## TCP Services
1. *Connection-oriented Service*: 
    - Handshaking Phase: Before application-level messages begin to flow, TCP has client and server exchange transport layer control information to alert the client and server for packet transfer.

>No encryption is provided by TCP or UDP. Data passes through un-encrypted thus allowing potential sniffing or intervention at different links between sender and reciever.

>*Secure Socket Layers (SSL)* is a TCP enhancement that provides process-to-process security like encryption and end-point authentication while providing usual TCP services as well.
>>When applications use SSL, cleartext is is sent to SSL socket; SSL encrypts the data and sends it to TCP socket. This data travel via the Internet to the socket of recieving end system, where SSL decrypts the data.

2. *Reliable Data Transfer Service*: TCP guarantees for same stream of bytes to reach receiving socket as it left the sending socket.
3. *Congestion Control Mechanism*: Throttles sending prcoess when network is congested and limits each TCP to specified bandwidth.

## UDP Services
- *Connectionless* so no handshake before two processes start communicating.
- No guarantee that messages will reach receiving process, if in order.
- No congestion control mechanism

|Application|Application-Layer Protocol|Underlying Transport Protocol|
|---------|-----------------------|----------------|
|Electronic Mail|SMPT|TCP|
|Remote Terminal Access|Telnet|TCP|
|Web|HTTP|TCP|
|File Tranfer|FTP|TCP|
|Streaming Multimedia|HTTP|TCP|
|Internet Telephony|SIP|UDP or TCP|

>Internet Telephony applications can often cope with some loss but require minimal rate, UDP is sometimes prefered over TCP.
>>Most firewalls are configured to block most UDP, Internet Telephony applications often designed to use TCP as backup.

## Application Layer Protocols
*Application Layer Protocols* define *type, **syntax, **meaning of information in fields* and *rules* of messages sent among application processes running on different end-systems.

Applicaition Layer Protocol is piece of network application.
- *Web* is client-server application allowing users to obtain documents from Web servers by usinf *HTTP*, Web's application-layer protocol which defines the format and sequence of messages exchanged between browser and Web server.
- *e-mail* application has many componenets, of which *SMTP* is its main application layer protocol.

## The Web and HTTP
**Web Pages**: Collections of *objects*, such as HTML files, JPEG images or video clips.

*Object*: File that is addressable by single **URL**

**Uniform Resource Locator(URL)**: Consists of two components, hostname of the server hosting the object and the object's pathname

**Hyper Text Transfer Protocol(HTTP)**: Web's application-layer protocol that defines how clients request Web pages and how servers transfer them.

>Web browsers implement client side of HTTP.

>Web servers implement server side of HTTP.

**Stateless Protocol**: HTTP is considered stateless because the server maintains **no information** about the clients; if a client requests the same object twice, the server simply sends it again.

## Non-Persistent and Persistent Connections
1. **Non-Persistent Connections**: A mode where each request/response pair is sent over a **seperate TCP connection**.
    - Connection does not persist for other objects
    - Each TCP connection transports one request and one response message before terminating the TCP connection
    - Multiple TCP connections are made for request and response of each object

**Round-Trip Time(RTT)**: Tome takes for packet to go from client to server and back to client.
- Includes packet-propagation delays, queuing delays and packet-processing delays.

**Three-Way Handshake**: The process of establishinh a TCP connection, which takes one RTT before the actual request is sent.
>Three-Way Handshake: 
```
1. Client sends a TCP segment to the server  

2. Server acknowledges and responds with TCP segment

3. Client acknowledges back to server
```
>1 RTT - first two steps of the handshake. 2nd RTT - after the handshake, server sends the HTML file into TCP connection.

2. **Persistent Connections**: Mode where all requests and responses are sent over **same TCP connection**.
    - Server leaves TCP connection open after sending a response

>By default, HTTP uses persistent connections, but can be configured to use non-persistent connections.

## HTTP Request Message Structure
>HTTP uses **TCP** as underlying protocl, ensuring messages arrive intact.

HTTP messages are written in ordinary **ASCII text** and a fixed structure for request and response.

1. **HTTP Request Message Structure**
    - **Request Line**: Top line in structure; has 3 fields:
        - **Method**: **GET** (requests objects), **POST** (sends data like form inputs), **HEAD** (requests only headers, leaving out objects), **PUT** (uploads files) and **DELETE**
        - **URL (uniform resource locator)**: The path to the specific object being requested
        - **Version**: The specific protocl version the cliet is using (e.g. HTTP)
    - **Header Lines**: Provide metadata about the request; e.g:
        - `Host`: Specifies the server address where object resides
        - `User-agent`: Identifies the browser type (e.g. Chrome) making the request
        - `Connection`: The user's preferred language (e.g. English)
        - `Accept-language`: The user's preferred language (e.g. English)
    - **Blank Line**: A mandatory empty line (marked by a carriage return and line feed) seperating the headers from the body
    - **Entity Body**: This section is empty for GET requests but contains data (like form field values) for POST request.
2. **HTTP Response Message Structure**
    - **Status Line**: Top line in structure; contains **Protocol Version** , **Status Code** and **Status Message**
        - **Common Status Code**:
            - `200 OK`: The request succeeded and object is returned 
            - `301 Moved Permanently`: The object has a new URL
            - `404 Not Found`: The requested document does not exist on the server
            - `505 HTTP Version Not Supported`:The server doesn't support the requested version
    - **Header Lines**: Metadata about the server and the returned object
        - `Date`: When the response was created
        - `Source`: The type of server software (e.g. Apache)
        - `Last-modified`: When the object was last changed (crucial for Web caching)
        - `Content-Length`: The size of the object in bytes
        - `Content-Type`: The type of object in the body (e.g. text/html)
    - **Blank Line**: Seperates the header lines from the data
    - **Entity Line**: Bottom line; contains **requested data** (e.g. HTML code or image or audio file)

## Cookies: User-Server Interaction
**Cookies**: A techonology that allows websites to *identify users* and *track* their activites (since HTTP is **stateless** protocol)

1. **A cookie header line** in HTTP **response** message (e.g. `Set-cookie: 1678`)
2. **A cookie header line** in the HTTP **request** message (e.g. `Cookie: 1678`)
3. **A cookie file** kept on user's end system and managed by user's browser
4. **A back-end database** at the web site to store user-specific information

How cookies work:
1. When user visits a site for the first time, server creates **unique identification number** along with an entry in its back-end database using that number
2. Server responds to browser with a message containing `Set-cookie:` header and unique ID
3. Browser then makes a line in local cookie file including **server's hostname** and the ID
4. When user visits the site again and requests a page, browser automatically extracts the ID from cookie file and includes it in the `Cookie:` header in HTTP request.
5. Server receives the ID and tracks the pages, at what time and their exact order the user visited 

Cookies are used in:
- **online shopping carts** to keep track of all items, allowing a collective purchase at the end of the session
- **personalizing requests**, based on the pages viewed by user before
- **associating name, password, card details to cookie ID**, thus not requiring to re-enter information.

>By combining cookies with user-supplied information like name, e-mail, card details, a complete user profile can be made and be sold to third parties as well.

## Web Caching
**Web Cache / Proxy Server**: A network that tries to satisfy HTTP requests on behalf of the origin server.

>Cache is server for the browser (sends request and recieves response from browser) and client for the origin server (sends request to and recieves response from orign server).

How it works:
1. **Request Redirection**: The browser establishes a TCP connection to the Web cache and sends HTTP request there
2. **Checking**
    - If cache has local copy of requested object, it returns it within an HTTP response
    - If cache has no local copy of requested object, as a client, establishes a seperate TCP connection with origin server
3. After recieving object from origin server, cache stores a copy in local storage and forwards a copy to browser

A web cache
- **reduces response time** for requests
- **reduce traffic** on access links bought by *local ISP* or *institutions*

**Hit Rate**: The fraction of requests satisfied directly by a cache

**CDNs (Content Distribution Networks)**: Companies that install many geographically distributed caches to localize traffic

## The Conditional GET
**Conditional GET**: A mechanism that allows a cache to verify if locally copied object has any modifications in the origin server

- **The Request**: The cache sends a request to the origin server including `If-Modified-Since:` header containing the date object was last cached.
- **The Response**: 
    - If object has **not** been modified since, server returns **304 Not Modified** response
    - If object **has** been modifed, server returns updated version in "200 OK" response

## File Transfer: FTP
HTTP and FTP are both file transfer protocols of the application layer.

>Both run on TCP, however FTP has unique architectural approach.

### Overview of FTP
- Allows a user to transfer files to or from a remote account
- **Authentication**: Requires user to provide a **user identification and password** to access the remote account
- **User Interface**: The user interacts with FTP though an 
**FTP user agent**, which communicates with the remote FTP server

### The two-Connection Architecture
FTP's unique architectural structure is **two parallel TCP connections** used to transfer a single file
1. **Control Connection (Port 21)**: Used for sending *control information* like user ID, passwords and commands to change directories or *put* (store) and *get* (retrieve) files
    - >Persistent (single Control Connection remains open for entirity of user's session)
2. **Data Connection (Port 20)**: Used specifically for the actual transfer of file data
    - >Non-Persistent (one Data Connection is for one file transferred within a session)

**Out-of-Band Signaling**: FTP uses seperate connection for control information, it sends control information **out-of-band**

**In-Band Signaling**: HTTP sends request and response headers in the same TCP connection used for file data, making it signal **in-band**.

**Statefulness**: FTP servers **maintain state** about the user by *tracking* user's current directory and previous authentication

### FTP Commands 
FTP commands are from *client to server*; written in **7-bit ASCII** format; *4 uppercase ASCII characters* with *optional arguments*; `[]` means optional
- `USER [username]`: Sends the user ID to server
- `PASS [password]`: Sends the user password
- `LIST`: Asks the server to send back a list of all files in the current remote directory (this list is sent ovver a *data connection*)
- `RETR [filename]`: Used to retrieve (download) a file
- `STOR [filename]`: Used to store (upload) a file to the remote host
### FTP Replies
FTP replies are from *server to client*; each command get a reply; *3-digit number* with *optional message*
- `331` Username OK, password required
- `125` Data Connection already open; transfer starting
- `425` Can't open data connnection
- `452` error writing file

## Simple Mail Transfer Protocol: SMTP
Electronic mail has 3 main components:
1. **User Agents**: These allow users to *read*, *reply*, *forward* and *compose* messages (e.g. Microsoft Outlook, Apple Mail or web-based interfaces like Gmail)

2. **Mail Services**: Manages an **outgoing message queue** for mail being sent
    - core of e-mail infrastructure
    - each recipient has **mailbox**

3. **SMPT**: Uses reliable data transfer to transfer mail from sender's mail server to recipient's server
    - Runs on both client and reciever server

### SMTP: The PUSH Protocol
SMPT defines how mail servers speak to each other to transfer messages

**The Process**: Invloces a three-phase transfer: **Handshaking, Transfer of messages** and **Closure**

**Push Protocol**: SMPT is primarily a **push protocol**, the sending mail server initiates the connection to "push" the file to the reciever.

**Direct Transfer**: Unlike some other protocols, SMPT does not use intermediate mail servers; the connection is a direct TCP link between the sender's and recipient's servers

**ASCII Command/Reply**: SMPT uses 7-bit ASCII for its commands (e.g. `Hello`, `MAIL FROM`, `RCPT TO`, `DATE`, `QUIT`) and status replies (e.g. `250 OK`, `354 Intermediate response`)

### SMTP vs HTTP
Both protocols transfer files over TCP, but
|HTTP|SMTP|
|----|----|
|**Pull Protocol**: Client sends request for pages already uploaded onto the server|**Push Protocol**: Sending mail server pushes file to recieving mail server|
|TCP connection made by machine wanting to *recieve* the file |TCP connection initiated by machine wanting to *send* the file|
|HTTP has no constrictoin|SMTP requires only **7-bit ASCII** format|
|HTTP encapsulates each object in own response message|SMPT places all of message's objects into a single **single message**|

### Mail Merge Format and Access Protocols
**Mail Merge Format**: Format of actual message inside SMTP envelope; includes **header lines** (e.g. `To:`, `From:`, `Subject:`) followed by **message body** seperated by a blank line

**Mail Access Protocols**: Because SMTP is a *push* protocol, it can't be user agent to "pull" messages from a server. Specific protocols include:
1. **POP3 (Post Office Protocol - Version 3)**: A simple "pull" protocol.
    - Operates in **download-and-delete** or **download-and-keep** modes
    - It is **stateless**
2. **IMAP (Internet Mail Access Protocol)**: Allows user to create folders on servers and organize messages
    - It **maintains state** accross sessions
3. **HTTP**: Users using web-based email(Gmail, Yahoo Mail) have user agents as web browser and the transfer between the browser and the mail server happens via **HTTP**
