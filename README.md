# Router1x3 SV/UVM Verification
ROUTER is a device that connects two or more networks (or computer LANs) and forwards data packets between computer networks (or from Source Server Network to Destination Client Network). It is an OSI layer 3 routing device. Router 1x3 has one ingress and three egress . As the definition suggests, the packet from a source network is routed to one of the destination networks.<br/>
## Router-Packet
### Packet Format:
The Packet consists of 3 parts i.e. Header, Payload and Parity such that each ID of 8 bits width and the length of the payload can be extended between 1 byte to 63 bytes.<br/>

<img align="center" width="404" height="315" alt="Project-Page-4 drawio" src="https://github.com/user-attachments/assets/8bcba9f0-f5b1-4011-8cea-765b03d19b2e" />

#### <ins>Header</ins>:
The packet header contains two fields Destination Address and Payload Length.<br/>
- *Destination Address*: The destination address of the packet is of 2 bits. The router drives the packets to respective ports based on the destination address of the packets. Each output port has 2-bit unique port address. If the destination address of the packet matches the port address, then the router drives the packet to the output port. The address "**3**" is invalid.<br/>
- *Payload Length*: The length of the data is 6 bits. It specifies the number of data bytes. A packet can have a minimum data size of 1 byte and a maximum size of 63 bytes.<br/>
  - If Length = 1, it means the data length is 1 byte.<br/>
  - If Length = 63, it means the data length is 63 bytes.<br/>
#### <ins>Payload</ins>:
Payload is the data information. Data should be in terms of bytes.<br/>
#### <ins>Parity</ins>:
This field contains the security check of the packet. It is calculated as bitwise parity over the header and payload bytes of the packet (!!! add how it is calculated).<br/>
## Router-Input Protocol

## Router-Output Protocol

## Verification Plan
### Features
#### <ins>Packet Routing</ins>:  
The [packet](https://github.com/theteamonk/router1x3-uvm-verification/edit/main/README.md#router-packet) is driven from the input port and is routed to any one output port, based on the address of the destination network.<br/>
#### <ins>Parity Checking</ins>:
An error detection technique that tests the integrity of digital data being transmitted between Server & Client. This technique ensures that the data transmitted by the Server network is received by the Client network without getting corrupted.<br/>
#### <ins>Reset</ins>:
It is an active low synchronous input that resets the router. Under reset conditions, the router FIFOs are made empty and the valid out signals go low indicating that no valid packet is detected on the output data bus.<br/>
#### <ins>Sending Packet</ins>:
Refer to [Router-Input Protocol](https://github.com/theteamonk/router1x3-uvm-verification/edit/main/README.md#router-input-protocol)
#### <ins>Reading Packet</ins>:
Refer to [Router-Output Protocol](https://github.com/theteamonk/router1x3-uvm-verification/edit/main/README.md#router-output-protocol)
