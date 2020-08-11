# Decentralized VPN DApp
A decentralized VPN dApp built with Arcblock's Forge's SDK

## Project Rough Idea

Some nodes choose to be VPN servers (they can be entry nodes, intermediate nodes, or exit nodes), an entry node is chosen at random and is bound to the user for a month (the user cannot use other nodes as entry nodes during this period for security reasons), then a few nodes (preferrably three) will be chosen to be intermediate nodes, and an exit node near a location indicated by the user will be chosen. These nodes will form a circuit where the user's traffic is directed through the entry node, through the intermediate nodes, and out of the exit node. The user will sign an agreement to pay a certain amount of tokens per megabytes of traffic to each of the nodes before connecting to the circuit.

### Specifications

- The connections between the nodes could be established via shadowsocks or openvpn, but a way to disguise traffic as "noise" or similar to regular traffic would be better.
- Nodes volunteering to be VPN servers would have to redirect traffic to multiple other nodes if these nodes are part of more than one circuit
- A smart contract would have to be designed to collect tokens from the user and distribute them evenly among the VPN server nodes

### Possible Problems to be Dealt

- Routing traffic through multiple nodes
- Setting up the smart contract
  - Measuring the amount traffic directed through the nodes
- Connecting the user to the circuit
- Making sure that traffic is actually directed through the nodes

## Pros of This DApp

- It is almost impossible to shut down this VPN service, giving people in countries with censored Internet connections a reliable VPN service
- The use of tokens to reward VPN server nodes encourages other nodes to be VPN server nodes
- The use of a circuit instead of a single node ensures that a malicious node (or a few malicious nodes, to an extent) cannot access or change the traffic data if the connections are encrypted

## Cons of This DApp

- Internet connections of the nodes may be unreliable
  - The Internet connectivity of nodes could be considered during the node selection process
- Routing traffic through a circuit may slow down connection speed
  - A choice to use a single node may be added, with a warning stating that using a single node may compromise security
