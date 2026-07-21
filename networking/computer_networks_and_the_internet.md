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

The same protocols need to be followed by different end systems on the Internet for various interoperations.

**Request for Comments(RFCs)**: Technical standards document developed by the Internet Engineering Task Force(IETF).

**Distributed Applications**: Applications involving multiple end systems that exchange data with each other.

**Application Programming Interface(API)**: A set of rules specifying how a program on one end system asks the Internet to deliver data to another end system.

---
## 1.2 The Network Edge
*Hosts* or *End systems* are of 2 types:
1. **Clients**: Category of end systems that include desktop, mobile PCs, smartphones and other user-facing devices.
2. **Servers**: More powerful machines that store and distribute content like Web pages, streaming video and e-mail.

### Internet Access
**Access Networks**: The physical network that connects end systems to the first router (*edge router*) on a route to other end systems.

Ways for end systems to gain Internet Access at **HOME**: 
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
  DSL Modem  (converts high-frequency signals into digital data for the router to understand)
      ↓
  Router  (distributes internet to all devices on local network)
      ↓
  Your devices
  ```
  2. **Cable Internet Access**: Residence obtains internet access from the same company that provides television network.

**Cable Modem Termination System** is analogous to DSLAM; it turns analogue signals from cable modems into a digital format.

**Hybrid Fibre Coax(HFC)**: A broadband network using **fibre optic cable** for backbone (from ISP's headend to home distribution points), then switches to **coaxial cable** into homes and businesses.
-*fibre* carries massive bandwidth for long distances with near-zero signal degradation, but is very expensive to use everywhere.
- Data via HFC is controled by **Data Over Cable Service Interface Specification(DOCSIS)**. 

Coax is a **shared medium**. Frequency is split accordingly:

|Direction|Frequency|Used For|
|----------|------------------|--------------------|
|Downstream|*higher frequency*|Data coming to you|
|Upstream  |*lower frequency* |Data you upload/send|

3. **Fibre To The Home(FTTH)**: An access technology that provides an optical fibre connection directly from the central office(CO) to the home.

One fibre leaves the CO, then after reaching close to the homes, it **splits** into home-specific wires via the following two network architectures:

|**Active Optical Network(AON)**|**Passive Optical Network(PON)**|
|-------------------------------|-------------------------------|
|Electrically active (uses routers and power switches)|Electrically passive (uses unpowered slitters)|
|Dedicated to one user|Shared among many people|
|Larger range (about 100km)|Lower range (about 20-30km)|

4. **Satellite Link**: In areas where DSL, cable and FTTH can't reach, satellite links connect residences to the internet.

Ways for end systems to gain Internet Access at **Work/Enterprise**:
5. **Ethernet**: Most prevalent LAN access technology in corporate.

6. **Wireless**: User be within tens of kilometers range for wireless transfer of data via a cellular telephone network.

Multiple-generation wireless (3G, 4G, 5G, etc) have been developed with packet-switched wide-area wireless Internet access.

### Physical Media
Refers to the media (of various shapes, sizes and materials) a bit travels between transmitter-receiver pairs.
- **Guided Media**: Electromagnetic waves are guided along a solid medium (eg., twisted copper wires, fibre optic cables, etc).
- **Unguided Media**: Waves propagate in the atmosphere (eg. LAN, satellite links, etc).

Common physical media include: 
- Twisted-Pair Copper Wire
- Coaxial Cable (guided shared mediums)
- Fibre Optics
- Radio Channels (no physical medium required; various types based on range)
- Satellite Radio Channels ()

|Geostationary Satellites|Low-Earth Orbiting Satellites (LEO)|
|------------------------|-----------------------------------|
|Remain permanently above fixed spots on Earth by revolving in orbit at 36,000 km above Earth's surface|Placed closer to Earth, not upon fixed spots|

---
## 1.3 The Network Core

### Packet Switching
Data is broken into smaller chunks **packets**, to send messages from the source to the receiver end system.

Packet switches have two main types: **routers** and **link-layer switches**.

- **Store-and-Forward Transmission**: Packet switches require the entire packet to be delivered before sending the first bit of data through the outbound link.
- **Output buffer**/**Output Queue**: A storage area in a packet switch that stores packets that the router is about to send out.
- **Queuing Delays**: If a packet is to be sent out from an outbound link, but the link is busy with transmission of another packet, the new packet has to wait; thus the delay.
- **Packet Loss**: If the buffer space is all occupied, the new packet has nowhere to be stored; thus either the arriving packet or an already-queued packet will be dropped.
- **IP address**: Address of every end system on the Internet.
- When a source end system sends a packet of information, it includes a *packet header* which has metadata of that packet, including the IP address of the destination end system. Thus, the router knows which communication link to send that packet to.
- **Forward Table**: A data structure in the router that maps destination IP prefixes.
- **Routing Protocols**: Automatically set 
the forwarding tables.

>The Internet is a packet-switching network.

### Circuit Switching
Resources required (links, transmission rates) are *reserved* before communications start between two end systems.

**Circuit**: A dedicated end-to-end connection established between two hosts when the network reserves a **constant transmission rate** for the duration of the session.

Circuit is efficiently implemented by either of the following two ways:

|**Frequency-Division Multiplexing(FDM)**|**Time-Division Multiplexing(TDM)**|
|-------------------|-----------------|
|Method of implementing a circuit by *dividing the frequency spectrum* of a link into bands, with each band dedicated to a specific connection|Method where *time is divided into frames* of fixed duration, and each frame is divided into time slots; each connection is dedicated one time slot in every frame|

### Network Of Networks
Network of Networks refers to the connection of billions of ISPs across the Internet. ISPs include not only telephone or cable companies, but also any type of access provider (eg., universities providing WiFi to students).

**Regional ISPs**: ISPs of a specified region.

**Tier-1 ISPs**: Similar to global transit ISPs, but not present in every city.
Eg, AT&T, Sprint and NTT.

**Point of Presence(PoP)**: A group of one or more routers in a provider's network where customer ISPs connect to the provider.

**Multi-homing**: The practice of an ISP connecting to **two or more** provider ISPs to ensure continued service.

**Peering**: Agreement where nearby ISPs at a similar level directly connect their networks to exchange traffic settlement-free (**without paying eachother**).

**Internet Exchange Point(IXP)**: Physical meeting points where multiple ISPs peer together.

**Content Provider Networks**: Private networks operated by companies like Google to distribute content to end users while bypassing upper tiers of public interest.

---
## 1.4 Delay, Loss and Throughput in Packet-Switched Networks

### Delays
**Nodal Delay**: Total delay experienced by a packet at a node (router), which is the sum of processing, queuing, transmission, and propagation delay.

**Processing Delay**: The time required for a router to examine the packet's header and determine where to direct it. It also includes the time to check for bit-level errors.

**Queuing Delay**: The time a packet spends in a queue (buffer) to be transmitted onto a link. Delay ranges from zero to milliseconds based on traffic congestion.

**Transmission Delay**: Time required to transmit all packet bits into the link. It ranges from microseconds to milliseconds.

**Propagation Delay**: Time taken for a bit to travel from the beginning of a link to the next router or host. Depends largely on the physical medium material.

Other delays include:
- End systems *purposefully* delay sending a packet into *shared medium* as part of the protocol.
- **Media Packetisation Delay**: Majorly in Voice-over-IP (VoIP), the sending end system encodes digitised speech before passing it to the Internet. Time taken for this digitisation causes integral delay in packet transmission.

>Propagation Delay is calculated by dividing the distance of the link by the propagation speed of the medium.

**Traffic Intensity**: The ratio *La/R*, where *L* is packet size, *a* is average packet arrival rate, and *R* is transmission rate. Estimates extent of queuing delay.

>If traffic intensity > 1, then the queue will grow without bound.

### Losses
**Packet Loss**: Occurs when a packet arrives at a router's buffer that is already full. With no place to store the packet, the router **drops** (loses) it.

### Throughput in Computer Networks
**Throughput**: Rate ( bits/second) at which the destination host receives the file from the sender host.

**Bottleneck Link**: The line in a network path that has the lowest transmission rate, thereby limiting the end-to-end throughput for a file transfer.

---
## 1.5 Protocol Layers and Their Service Models
**Layering**: Structural process organises functionality of complex systems by dividing them into a series of horizontal levels.
- **Service Model**: Each layer, combined with layers below it, performs services and executes internal actions.
- **Modularity**: Internal implementation can be modified as long as it provides the **same services** and uses the **same services provided from the layer below**.
- **Encapsulation**: (In networking) Each layer receives a **payload** (data) from above, appends its own **header fields** and passes the resulting package to the next layer as a new payload.

### Layer Architecture
**Protocol Stack**: The collective name given to protocols belonging to various layers

**Internet Protocol Stack**: The five-layer architecture that organises the Internet, consists of - **application, transport, network, link and physical layers**.
1. **Application Layer**: The top layer where network applications and their protocols reside. Data at this layer is called **message**. Protocols at this level include:
    - **HTTP** (provides for Web document request and transfer)
    - **SMTP** (provides for transfer of e-mail messages)
    - **FTP** (provides for transfer of files between two end systems)
2. **Transport Protocol**: Transports application-layer messages between endpoints. Data at this level is called a **segment**. Protocols at this level are only two:
    - **TCP** (connection oriented service; flow control; breaks messages intro shorter segments)
    - **UDP** (connectionless service; no flow control; no connection control)
3. **Network Layer**: Moves **datagrams** from one host to another. Protocols at this layer include:
    - **IP** (defines fields in datagrams)
    -*routing protocols* (determine routes taken by datagram between two end systems)
4. **Link Layer**: Responsible for moving packets from one node to the next over a single communication link (eh, Ethernet, WiFi). Data at this level is a **frame**.
5. **Physical Layer**: Moves the individual bits within the frame from one node to the next over a physical medium.

**OSI Reference Model**: A seven-layer model developed by ISO. In addition to the five Internet layers, it includes the **Presentation Layer** (data interpretation/encryption) and the **Session Layer** (synchronisation and recovery).

**Encapsulation**: The process where each layer adds its own **header fields** to the data (**payload**) recieved from the layer above it.

---
## 1.6 Network Under Attack
**Malware**: Software designed to damage, disrupt or gain unauthorised access to a computer system

### Types of Malware (By Spreading Method)
1. **Viruses**: Require user interaction
    - Eg: email attachment containing executable code
    - Often *self-replicating*
2. **Worms**: Don't require specific user interaction
    - Exploits vulnerability in a network application or OS
    - Scans the Internet for other hosts running the same vulnerable application

### Types of Malware (By Malicious Activities)
1. **Spyware**: Collects private information from device
    - Eg: collecting passwords, even keystrokes and sending them back to the attacker
2. **Botnet Enrollment**: A compromised host may be  enrolled in a 'botnet', a network of many similarly infected devices
    - **Distributed Denial-of-Service (DDoS)** attacks may be launched in botnets against other targets.

**Denial-of-Service (DoS) Attacks**: Attacks intended to make a network or server unusable for legitimate users, often by flooding it with traffic.

**Packet Sniffing**: Placing a passive receiver near a transmitter to record copies of every packet flying by, thus revealing sensitive data to the attacker.

**IP Spoofing (Masquerading)**: The specific ability to hand-craft a packet with an arbitrary source address to trick a receiver into believing the message originated from a trusted source.

---
## 1.7 History of Computer Networking and the Internet

**Initial Theory**: Telephone network (circuit-switched) dominated, but computers needed *burst of traffic*.

**ARPnet**: The precursor to the Internet, funded by US Defence Research Agency (ARPA).

**Network Proliferation**: New networks emerged, including **ALOHANet** (a microwave network in Hawaii), DARPA's packet-satellite and radio networks, and the French **Cyclades**>

**Kahn Principles**: 
- **Best-effort delivery**: No reliability guarantees at the network layer
- **Stateless routers**: Routers do not maintain state for individual connections
- **Decentralised control**: No global authority managing the network

TCP/IP became the official protocol for ARPANET on **Jan 1, 1983**, replacing the older NCP.

**Domain Name System (DNS)** was developed to manage hostnames.

**Minitel** was a large-scale data network deployed in France, years before the Internet became common.

**The World Wide Web** invented by **Tim Bernerd-Lee**, introduced HTML, HTTP and Web servers/browsers.

The Web was made accessible to non-technical users by the development of the Mosaic browser (Netscape).

Aggressive deployment of DSL, Cable, and **Fiber-to-the-Home (FTTH)** replaced slower dial-up access.

High-speed WiFi and cellular data made it possible to stay connected.

Companies like **Google and Microsoft** built private networks to bypass upper-tier ISPs and deliver content almost instantaneously to end users.

---
---
