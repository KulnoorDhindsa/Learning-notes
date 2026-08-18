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
UDP in file `protocols.md` in `networking` folder.