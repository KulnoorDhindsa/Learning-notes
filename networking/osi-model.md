# OSI-Model
**OSI (Open Systems Interconnection)** is a *layered* architecture, made by **ISO (International Standards Organization)** allowing communications between various network systems, regardless of their structure
## Layered Structure
- Each layer defines set of functions different than those performed in other layers.
- Input data for a layer is output data from the previous layer.
- At the **physical layer**, communication is direct
- Each layer adds own *headers* and *trailers* (control data added to beginning or end of data, containing meta data) to data from previous layer and sends it to the nect layer
>At layer 1 of sending end system, packet is converted into form that is transferable throught the layers and recieved by recieving end system. The recieving machine unwraps message layer by layer.
**Peer -to-peer processes**: Processes that take place at individual layers using protocols of that specific layer
- Transportation of data and network information down the layers from the sending machine, and up the layers to the recieving machine is due to **interface** between each layer. *Interface* specifies the requirement and services provided by following layer.
>As long as layer still provides expected service, method of implementation may be modified without requiring changes in nearby layers. 
## Functions
### Physical Layer
- Coordinates functions required to transmit bit stream over a physical medium.
- Defines characteristics of interface between devices and transmission medium
- Defines type of **encoding** (0's and 1's convert to *electrical* or *optical*) for transmission of *bits* (sequence of 0's and 1's)
- Defines the **transmission rate** or life of a bit
- Concerned with connestion of devices in the medium
    - *point-to-point configuration*: devices connected through dedicated link
    - *multipoint configuration*: devices connected through link shared between multiple devices
- Determines topology of connection
    - *mesh topology*: every device connected to every other device
    - *star topology*: devices connected through central device
    - *ring topology*: every device connected to the next
    - *bus topology*: every device connected through a common link
- Determines transmission mode
    - *simplex mode*: one-way communication (e.g. keyboard, mouse)
    - *half-duplex mode*: two-way communication but not at same time (e.g. walkie talkie)
    - *full-duplex mode* / *duplex*: two communication at any time (e.g. mobile phone)
### Data Link Layer
- **node-to-node delivery**, responsible for transfer of data over a *single network*
- Divides stream of bits into manageable data units called **frames**
- Adds *headers* to frames to define the **physical address** of source address and reciever's address
- Has *flow control* mechanism over the *entire network* where, rate of absoroption of data by reciever is less than rate of data being sent by the sender, so as to not over exert recieving system
- Adds **trailers** for *reliability* (not to loose bits, prevents duplication of bits)
- Determines which devices have control of link when multiple devices are connected to the same link
### Network Layer
- Responsible for transfer of individual bits across *different networks* (links) or *internetworks*
- For bits travelling through *internetworks*, network layer adds **headers** for logical addressing
- Provides connection in *internetworks* (like routers and gateways do)
### Transport Layer
- Responsible for transfer of *entire message* from **source-to-destination**
- Accounts for *realation* between sent packets
- Provides **service-point address** or **port address** in its *header*, so that packets are sent from an application on sender end-system, safely to another application on the reciever end-system
>Network layer gets each packet to correct end system, transport layer gets entire message to correct application of that system.
- Message is divided into tranferable *segments* with *sequence numbers* to re-assemble the packets and request for lost packets from sender on arrival
- Connections
    - **Connection Oriented Transport Layer**: Generates a connection between sender and reciever, and after transfer of all segments, terminates the connection
    - **Connectionless Transport Layer**: Treates each *segment* as individual message that it transports from sender end-system application to reciever end-system application
- End-to-End *flow control* mechanism
- End -to-End *error control* mechanism, where error (damage, delay or duplication) correction is done by **re-transmission**
### Session Layer
- Synchronises interaction between communicating end-systems
- Allows **dialog control**, where *half-duplex* or *full duplex* mode of communication is established between end-systems
- Adds **check-points** (*synchronisation checkpoints*) for large data transfers (e.g. re-transmission from page 501 is better than re-transmission of 1 to 501 pages in a book)
### Presentation Layer
- Responsible for syntax of information exhanges between end-systems
- Presentation layer at sending machine, *translates* information into common bit stream format. Presentation layer at recieving machine converts common format into reciever dependednt format
- Allows **encryption** and **decryption** of information
- Allows **data compression** of text, audio, video etc to allow less bits to be transmitted
### Application Layer
- Allows acces to the network
- Creates **virtual network terminal** for user's end system to talk to the software terminal
- Via FTP, HTTP etc, it allows access, retrieval and modifications of files online on servers
- Allows Mail service (via SMTP and access protocols like IMAP )
- Allows directory service (via DNS)

>**P**lease **D**o **N**ot **T**ouch **S**teve's **P**et **A**lligator

---
# Application Layer
**Application Architecture**: Designed by a developer to define how the application is structured across different end systems

Application Architecture is mainly of two types:
1. **Client-Server Architecture**: A paradigm where always-on host (*server*) services requests from other hosts (*clients*).
    - No direct communication amongst clients.
    - Servers have **fixed IP address** 
    - **Data Centres**: Large housing of hosts used to create powerful virtual servers
2. **Peer-to-Peer (P2P)**: A paradigm with no reliance on dedicated servers; pair of intermittently connected hosts (**peers**) communicate directly with each other.
    - **self-scalable**: Peers are redistributors and consumers of bits.
3. **Hybrid Architecture**: Applications that combine both client-server and P2P elements (e.g. instant messaging using a server to track IP addresses but sending messages directly between users).

**Process** is a program that runs inside an end system.

Processes communicate with each other across the Internet via **messaging**. A sending process creates and sends *messages*, while a receiving process receives and responds by sending messages back.

In P2P file sharing, the peer that downloads files is the *client*, and the peer that uploads the files is the *server*. So, the same process can be a *client* and *server* too.

In terms of a communication session, the process that *initiates* the communication is the **client**, while the process waiting to be contacted is the **server**.

**Socket**: A software interface through which a process sends and receives messages from the Internet.
>Socket is interface between **applicatio layer** and **transport layer** within an end system.

>Socket is **Application Programming Interface (API)** between application and network layer.

**Addressing Processes**: To identify a receiving process, a sender must specify the **IP address** of the destination host and a **port number** that identifies the specific receiving process on that host.

Different services provided by *Transport Layer Protocol* to applications that invoke it include:
1. *Reliable Data Transfer: Transport Layer Protocol allows reliable data transfer with *no packet loss (due to overflowing buffer or packet being discarded owing to errors)
    - Certain *loss-tolerant applications* don't mind packet loss (e.g. multimedia applications involving audio/video)
2. *Throughput*: Transport Layer Protocol would ensure that available throughput is always at least a minimum amount requested by the application.
    - *Bandwidth-sensitive Applications*: Applications that require a minimum amount of throughput to be effective (e.g. Internet telephony)
    - *Elastic Applications*: Applications that can use as much as or as little throughput as is available (e.g. e-mail, file transfer)
3. *Timing*: Transport Layer Protocol provides timing guarantees to avoid unnatural pauses in conversations or long delays in action and required result.
4. *Security*: Transport Layer Protocol provides various security services to end systems, including encryption and decryption in sending and receiving hosts.

## TCP Services
1. *Connection-oriented Service*: 
    - Handshaking Phase: Before application-level messages begin to flow, TCP has the client and server exchange transport layer control information to alert the client and server for packet transfer.

>No encryption is provided by TCP or UDP. Data passes through unencrypted, thus allowing potential sniffing or intervention at different links between sender and receiver.

>*Secure Socket Layers (SSL)* is a TCP enhancement that provides process-to-process security like encryption and end-point authentication while providing usual TCP services as well.
>>When applications use SSL, cleartext is sent to an SSL socket; SSL encrypts the data and sends it to a TCP socket. This data travels via the Internet to the socket of the receiving end system, where SSL decrypts the data.

2. *Reliable Data Transfer Service*: TCP guarantees the same stream of bytes reaches the receiving socket as it left the sending socket.
3. *Congestion Control Mechanism*: Throttles the sending process when the network is congested and limits each TCP to a specified bandwidth.

## UDP Services
- *Connectionless*, so no handshake before two processes start communicating.
- No guarantee that messages will reach the receiving process in order.
- No congestion control mechanism

|Application|Application-Layer Protocol|Underlying Transport Protocol|
|---------|-----------------------|----------------|
|Electronic Mail|SMPT|TCP|
|Remote Terminal Access|Telnet|TCP|
|Web|HTTP|TCP|
|File Tranfer|FTP|TCP|
|Streaming Multimedia|HTTP|TCP|
|Internet Telephony|SIP|UDP or TCP|

>Internet Telephony applications can often cope with some loss but require minimal rate; UDP is sometimes preferred over TCP.
>>Most firewalls are configured to block most UDP; Internet Telephony applications are often designed to use TCP as backup.

## Application Layer Protocols
*Application Layer Protocols* define *type, **syntax, **meaning of information in fields* and *rules* of messages sent among application processes running on different end-systems.

Application Layer Protocol is a piece of network application.
- *Web* is a client-server application allowing users to obtain documents from Web servers by using *HTTP*, Web's application-layer protocol which defines the format and sequence of messages exchanged between browser and Web server.
- *e-mail* application has many componenets, of which *SMTP* is its main application layer protocol.

## The Web and HTTP
**Web Pages**: Collections of *objects*, such as HTML files, JPEG images or video clips.

*Object*: File that is addressable by single **URL**

**Uniform Resource Locator(URL)**: Consists of two components: the hostname of the server hosting the object and the object's pathname

**Hypertext Transfer Protocol(HTTP)**: Web's application-layer protocol that defines how clients request Web pages and how servers transfer them.

>Web browsers implement the client side of HTTP.

>Web servers implement the server-side of HTTP.

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
    - **Blank Line**: Separates the header lines from the data
    - **Entity Line**: Bottom line; contains **requested data** (e.g. HTML code or image or audio file)

## Cookies: User-Server Interaction
**Cookies**: A techonology that allows websites to *identify users* and *track* their activites (since HTTP is **stateless** protocol)

1. **A cookie header line** in HTTP **response** message (e.g. `Set-cookie: 1678`)
2. **A cookie header line** in the HTTP **request** message (e.g. `Cookie: 1678`)
3. **A cookie file** kept on the user's end system and managed by the user's browser
4. **A back-end database** at the website to store user-specific information

How cookies work:
1. When a user visits a site for the first time, the server creates a **unique identification number** along with an entry in its back-end database using that number
2. The server responds to the browser with a message containing a `Set-cookie:` header and the unique ID
3. The browser then makes a line in the local cookie file including ** the server's hostname** and the ID
4. When the user visits the site again and requests a page, the browser automatically extracts the ID from the cookie file and includes it in the `Cookie:` header in the HTTP request.
5. The server receives the ID and tracks the pages, at what time and their exact order the user visited 

Cookies are used in:
- **online shopping carts** to keep track of all items, allowing a collective purchase at the end of the session
- **personalising requests**, based on the pages viewed by the user before
- **associating name, password, card details to cookie ID**, thus not requiring re-entering information.

>By combining cookies with user-supplied information like name, e-mail, card details, a complete user profile can be made and be sold to third parties as well.

## Web Caching
**Web Cache / Proxy Server**: A network that tries to satisfy HTTP requests on behalf of the origin server.

>Cache is server for the browser (sends request and receives response from browser) and a client for the origin server (sends request to and receives response from origin server).

How it works:
1. **Request Redirection**: The browser establishes a TCP connection to the Web cache and sends an HTTP request there
2. **Checking**
    - If the cache has a local copy of the requested object, it returns it within an HTTP response
    - If the cache has no local copy of the requested object, it establishes a separate TCP connection with the origin server
3. After receiving the object from the origin server, the cache stores a copy in local storage and forwards a copy to the browser

A web cache
- **reduces response time** for requests
- **reduce traffic** on access links bought by *local ISP* or *institutions*

**Hit Rate**: The fraction of requests satisfied directly by a cache

**CDNs (Content Distribution Networks)**: Companies that install many geographically distributed caches to localise traffic

## The Conditional GET
**Conditional GET**: A mechanism that allows a cache to verify if a locally copied object has any modifications in the origin server

- **The Request**: The cache sends a request to the origin server including an `If-Modified-Since:` header containing the date the object was last cached.
- **The Response**: 
    - If object has **not** been modified since, server returns **304 Not Modified** response
    - If object **has** been modified, server returns updated version in "200 OK" response

## File Transfer: FTP
HTTP and FTP are both file transfer protocols of the application layer.

>Both run on TCP; however, FTP has a unique architectural approach.

### Overview of FTP
- Allows a user to transfer files to or from a remote account
- **Authentication**: Requires user to provide a **user identification and password** to access the remote account
- **User Interface**: The user interacts with FTP through an 
**FTP user agent**, which communicates with the remote FTP server

### The two-Connection Architecture
FTP's unique architectural structure is **two parallel TCP connections** used to transfer a single file
1. **Control Connection (Port 21)**: Used for sending *control information* like user ID, passwords and commands to change directories or *put* (store) and *get* (retrieve) files
    - >Persistent (single Control Connection remains open for entirety of user's session)
2. **Data Connection (Port 20)**: Used specifically for the actual transfer of file data
    - >Non-Persistent (one Data Connection is for one file transferred within a session)

**Out-of-Band Signaling**: FTP uses seperate connection for control information; it sends control information **out-of-band**

**In-Band Signaling**: HTTP sends request and response headers in the same TCP connection used for file data, making it signal **in-band**.

**Statefulness**: FTP servers **maintain state** about the user by *tracking* user's current directory and previous authentication

### FTP Commands 
FTP commands are from *client to server*; written in **7-bit ASCII** format; *4 uppercase ASCII characters* with *optional arguments*; `[]` means optional
- `USER [username]`: Sends the user ID to the server
- `PASS [password]`: Sends the user password
- `LIST`: Asks the server to send back a list of all files in the current remote directory (this list is sent over a *data connection*)
- `RETR [filename]`: Used to retrieve (download) a file
- `STOR [filename]`: Used to store (upload) a file to the remote host
### FTP Replies
FTP replies are from *server to client*; each command get a reply; *3-digit number* with *optional message*
- `331` Username OK, password required
- `125` Data Connection already open; transfer starting
- `425` Can't open data connection
- `452` Error writing file

## Simple Mail Transfer Protocol: SMTP
Electronic mail has 3 main components:
1. **User Agents**: These allow users to *read*, *reply*, *forward* and *compose* messages (e.g. Microsoft Outlook, Apple Mail or web-based interfaces like Gmail)

2. **Mail Services**: Manages an **outgoing message queue** for mail being sent
    - core of e-mail infrastructure
    - each recipient has **mailbox**

3. **SMTP**: Uses reliable data transfer to transfer mail from sender's mail server to recipient's server
    - Runs on both client and receiver server

### SMTP: The PUSH Protocol
SMTP defines how mail servers speak to each other to transfer messages

**The Process**: Invloces a three-phase transfer: **Handshaking, Transfer of messages** and **Closure**

**Push Protocol**: SMTP is primarily a **push protocol**, the sending mail server initiates the connection to "push" the file to the receiver.

**Direct Transfer**: Unlike some other protocols, SMTP does not use intermediate mail servers; the connection is a direct TCP link between the sender's and recipient's servers

**ASCII Command/Reply**: SMTP uses 7-bit ASCII for its commands (e.g. `Hello`, `MAIL FROM`, `RCPT TO`, `DATE`, `QUIT`) and status replies (e.g. `250 OK`, `354 Intermediate response`)

### SMTP vs HTTP
Both protocols transfer files over TCP, but
|HTTP|SMTP|
|----|----|
|**Pull Protocol**: Client sends request for pages already uploaded onto the server|**Push Protocol**: Sending mail server pushes file to recieving mail server|
|TCP connection made by machine wanting to *recieve* the file |TCP connection initiated by machine wanting to *send* the file|
|HTTP has no constrictoin|SMTP requires only **7-bit ASCII** format|
|HTTP encapsulates each object in own response message|SMPT places all of message's objects into a single **single message**|

### Mail Merge Format and Access Protocols
**Mail Merge Format**: Format of actual message inside SMTP envelope; includes **header lines** (e.g. `To:`, `From:`, `Subject:`) followed by **message body** separated by a blank line

**Mail Access Protocols**: Because SMTP is a *push* protocol, it can't be a user agent to "pull" messages from a server. Specific protocols include:
1. **POP3 (Post Office Protocol - Version 3)**: A simple "pull" protocol.
    - Operates in **download-and-delete** or **download-and-keep** modes
    - It is **stateless**
2. **IMAP (Internet Mail Access Protocol)**: Allows users to create folders on servers and organise messages (move messages, delete messages, etc)
    - It **maintains state** accross sessions
    - Allows user to obtain **part of the message** sent. When a low-bandwidth connection is there between the user agent and the mail server, viewing the contents instead of the attached file (which would take time to download) conveys the message as well
3. **HTTP**: Users using web-based email(Gmail, Yahoo Mail) have user agents as web browsers, and the transfer between the browser and the mail server happens via **HTTP**
