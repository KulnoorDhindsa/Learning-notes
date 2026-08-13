# Transport Layer
Transport layer protocols converts the application-layer packets **segments**.

TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) provide different set of transport-layer services to applications.

Transport-layer provides logical communication between *processes* running on different hosts, network-layer provides logical communication between *hosts*.

IP is *Internet's network-layer protocol*, which tries to deliver *all* the segments between communicating hosts, with *no guarantees*.

**Sockets** act as doors allowing data to pass from network to process and process to network. 

**Multiplexing** and **De-multiplexing** are *transport layer functions* that turn host-to-host IP delivery into process-to-process further socket-to-socket delivery running on the two communicating end systems.

The specific sockets involved in *multiplexing* and *de-multiplexing* are marked with **source port number fields**