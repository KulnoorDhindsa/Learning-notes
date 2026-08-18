# Transport Layer
Transport layer protocols converts the application-layer packets **segments**.

TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) provide different set of transport-layer services to applications.

Transport-layer provides logical communication between *processes* running on different hosts, network-layer provides logical communication between *hosts*.

IP is *Internet's network-layer protocol*, which tries to deliver *all* the segments between communicating hosts, with *no guarantees*.

**Sockets** act as doors allowing data to pass from network to process and process to network. 

**Multiplexing** and **De-multiplexing** are *transport layer functions* that turn host-to-host IP delivery into process-to-process further socket-to-socket delivery running on the two communicating end systems.

The specific sockets involved in *multiplexing* and *de-multiplexing* are marked with **source port number fields** and **destination port number fields**.

>Port numbers are *16-bit* numbers ranging from 0 to 65535. Those between 0 to 1023 are **well-known port numbers**, that is reserved for HTTP (@ port number 80) and FTP (@ port 21).

>Port numbers are usually assigned from 1024 and onwards, that are not being used by any other UDP port in the host.

Each socket could be assigned a port number, through which data transfers to processes.

Client side of application **allows** transport layer  to *automatically* assign port numbers, server side of application **assigns** a specific port number **on its own**.

>UDP socket is identified by **destination IP address** and **destination port number**.

>TCP socket is identified by **4 tuples**, *source IP*, *source port number*, *destination IP* and *destination port number*.

>*Port Scanning* refers to process of determining if a port is active/open on a host, meaning that it can be attacked.

### UDP: Connectionless Transport
Takes *messages* from application processes, attaches the required *metadata* like *source and destination IP addresses and port numbers* as *8 byte headers* (no trailers) to the front of the message.

It makes **best-effort attempt** to ensure that all the packages are sent safely from sending end-system to recieving end-system, with **NO guarantee**.

>All the small packets or *messages* have the same metadata i.e. the same source and destination IP address and port numbers

>**NO handshake** happens here (inlike in TCP), thus its *connectionless*.

UDP is still used as:
- **NO** handshake or transmission *delay*
- Sends data *instantly* (after encasing data into a *UDP segment*), preventing older data from blocking or lagging incoming data
    - TCP has **congestion control mechanism**, if a packet *drops*, TCP stops the message and waits for that data to be re-transmitted and *acknowledged* by destination host/port
- UDP has **smaller Headers** (8 byte headers) compared to TCP (20 byte headers)
- UDP is used in:
    - **Live-Videos**: Dropping some part of the videos/voice and continuing the rest is preffered over stopping the entire stream
    - **Online Gaming**: Faster updates and more coordination with inputs and outputs
    - **DNS**: Quick lookups prefer faster single-response and reply methods rather than maintaining long sessions over the Network.
    - **RIP (Routing Information Protocol) routing table updates**: Digital maps or database stored inside a router (used as GPS) using RIP which lists all known *network destinations*, IP address of next router (NEXT HOP), total number of routers (hops) a packet passes to get to its destination (Metric / Next HOP)
>Servers responsible for a single application supports many active clients when application runs on UDP rather than TCP
- UDP is NOT used in:
    - **HTTP**: Reliability is more credible for web-pages rather than speed
    - **Few Streaming videos**: Where reliability and error-free delivery out-weigh the speed and cost of UDP services
        - TCP is **fire-wall friendly**