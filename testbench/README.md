# Verification Plan
## Features

- **Resetn**:<br/> Active Low Synchronous input that resets the Router. Under reset conditions, the Router FIFOs are made empty and the valid out signals go low indicating that no valid packet is detected on the output data bus.

- **Packet Routing**:<br/>  The packet is driven from the input port and is routed to any one output port, based on the address of the destination network.
  
- **Parity Checking**:<br/> An error detection technique that tests the integrity of digital data being transmitted between Source & Destination. This technique ensures that the data transmitted by Souce network is received by the Destination network without getting corrupted.

- **Sending Packet**:<br/> [Router Input Protocol](https://github.com/theteamonk/router1x3-uvm-verification#router-input-protocol)
  
- **Reading Packet**:<br/> [Router Output Protocol](https://github.com/theteamonk/router1x3-uvm-verification#router-output-protocol)

## Strategies

## Transaction
- **Base Sequence**:<br/> Random: Header, Payload data

## Transactors

## Coverage Model

## Callbacks
