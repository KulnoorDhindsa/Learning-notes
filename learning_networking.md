# Chapter 1
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
1. **Digital Subscriber Line(DSL)**: Residential broadband access that uses existing twisted-pair telephone lines to transmit data at different frequencies than traditional phone calls.
    - *higher frequencies*: 