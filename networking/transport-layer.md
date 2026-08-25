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
---
### UDP: Connectionless Transport
UDP in file `protocols.md` in `networking` folder.

---
### What it takes for Reliable Data Transfer
When the layer *below* a *reliable data transfer layer* isn't reliable (e.g. IP), the task of performing reliable data transfer (even by a reliable data transfer protocol like TCP) gets harder.
- FMSs: (Finite-State Machines) States in which a machine exists at a time (say, when it first started, and when it got valid inputs and developed, it went into a new state)
- rdt: Reliable Data Transfer
- ACKs/NAKs: (Acknowledgements and Negative Acknowledgements) Are *feedbacks* sent to the sender if data arrived safely or with errors to the reciever

1. **rdt1.0: Over Perfectly Reliable Channel**
    - **No bit errors** and *no packet loss*
    - **Design**:
        - Sender and receiver Finite-State Machines (FSMs) have **one state** (no improvements required in the machine, as ZERO chances of error)
        - Sender packages the data and sends it over the channel and reciever recieves the package
        - No NACKs or ACKs
2. **rdt2.0: Over Channel with *Bit Errors***
    - *Bits* may be corrupt (due to any reason, transmission etc) and **NO packet loss**
    - **Design**:
        - *ARQ* (Automatic Repeat reQuest) protocols:
            1. **Error Detection**: Reciever detcts errors (through CheckSum)
            2. **Receiver Feedback**: ACKs and NAKs sent from receiver to sender
            3. **Retransmission**: Retransmission of packet in case of packet error
        - *Delay* is caused as ACKs and NAKs for each packet is sent and recieved over the network, thus crowding it
        - Problem arises when ACKs and NAKs get *possibly* corrupt, leading to failure of confirmation or duplicate packets
3. **rdt2.1: Sequential Numbering on packets**
    - A *sequence* number (BINARY 0 or 1) is added to the headers of the expected ACKs/NAKs, to keep track of the expected bits
    - If a corrupted ACK/NAK is transmitted, then it is discarded and the end system waits for the re-transmission of the ACK/NAK from the sender, and acknowledges it upon recieving it
4. **rdt2.1: NAK-Free Protocol**
    - Instead of a NAK, the ACK for the last recieved packet is sent again (`ACK 1`, `ACK 2` etc) which is understood as a NAK for the currently expected packet
    - This reduces the effort of sending new NAKa over and over again, and only requires usage of ACKs
5. **rdt3.0: Over *lossy channel* with Bit Errors**
    - Channel can now **lose packets (data/ACKs)** along with the sending of **corrupted packets**
    - **Design**: 
        - **Countdown timers** and **premature timeouts** are introduced to detect packet losses
        - This may lead to *duplictae* packets, but the **sequential numbering** of BINARY `0` and `1` identifies the duplicates and proceeds to delete them
    - Also called **alternating-bit protocol** (due to binary sequential numbering alternating from `0` to `1`)
#### Conclusion:
Following components are vital for **reliable transport layer** (like TCP):
- **Checksums**: To detect bit errors in the packets
- **Timers**: Timeouts and retransmission of packets in cacse of packet losses
- **Sequential Numbering**: Allows detection of duplicate packets
- **ACKs**: Informing sender if recieval of packet
---
### Pipeline rdt protocols
`rdt.30` the *alternating-bit* protocol has flaws when performing at high-speeds and across large distances as it is a *stop-and-wait* protocol
- **Transmission Delay**: Even though the network is of *high-speed* (say 1Gbps), suppose its over a large distance, say it takes a 8 microseconds for a packet to be put into the 1Gbps link.
- **RTT**: ROund-Trip Time
- **Sender Utilization**: Fraction of time the sender is actually sending bits into the channel (as sender needs 1 RTT for every packet sent)
    - On rough calculations, only 0.027% of the gigabit link's capacity is being utilized by the user

#### Solution:
Instead of *stop-and-wait* protocol, its better if **multiple packets** are sent over without waiting for ACKs of every packet upon its sending
- BINARY sequential numbering of `0` and `1` won't work as *multiple packets* will be sent
- Buffering (temporary storage of data before transmission) will be required at reciever and sender's end for packets not acknowledged (multiple packet acknowledgements will be sent at once) 
- **2 approaches** are primarily used in these cases

1. **Go-Back-N (GBN) / Sliding-Window protocol**:
    - Multiple packets can be sent in the channel for *pipeline* without ACKs upto a **certain limit** say N
    - Upon recieving ACKs, this *window of N packets* is slid forward (thus its name)
2. **Selective Repeat (SR)**:



