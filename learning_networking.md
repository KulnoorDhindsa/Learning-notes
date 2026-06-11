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


