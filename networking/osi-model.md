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

>**P**lease **D**o **N**ot **T**ouch **S**teve's **P**et **A**lligator


