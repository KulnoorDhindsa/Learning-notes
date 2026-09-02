# Protocols

# UDP
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
### Segment Structure
- **Header**: UDP attaches *8 byte headers* to data from application layer, making it a **segment**. A UDP header includes the following:
    - **Source Port**: (2 bytes) Sending applicaiton's port number
    - **Destinaiton Port**: (2 bytes) Receiving application's port number
    - **Length**: (2 bytes) Total byte length of the UDP header and data payload
    - **Checksum**:  (2 bytes) Recieving host uses it to detect any *accidental* error in the segment like data corrupted due to **signal loss**
        - UDP *Checksum* **DOES NOT** check for malicious entries in segments, its only a maths formula, easy to fake
- **Data Payload**: The Application layer data being sent (e.g. a DNS query) of variable length (determined by `Length` in the header)
---
# TCP
Its called *connection-oriented* as before the actual sender sends data to reciever, a *handshake* takes place.
- The *handshake* consists of *segments* of information regarding both devices and their ports.
>TCP only runs on end-systems!
- **duplex-service**: If data is being transfered from A to B, then at same time, data can be transfered from B to A
- **point-to-point**: TCP connection is point
