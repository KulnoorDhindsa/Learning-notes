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