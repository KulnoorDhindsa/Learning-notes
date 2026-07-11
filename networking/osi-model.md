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

>**P**lease **D**o **N**ot **T**ouch **S**teve's **P**et **A**lligator
