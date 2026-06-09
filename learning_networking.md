# Chapter 1
## 1.1 What is the internet?
**End Systems / Hosts**: Devices connected to the internet, they are the end-points of the networking web.

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

**Protocols**: The set of rules that control the format and order of messages sent and received within the network.

Same protocols need to be followed by different end systems on the Internet for various interoperations.

**Request for Comments(RFCs)**: Technical standards document developed by the Internet Engineering Task Force(IETF).

**Distributed Applications**: Applications involving multiple end systems that exchange data with each other.

**Application Programming Interface(API)**: A set of rules specifying how a program on one end systems asks the Internet to deliver data to another end system.
