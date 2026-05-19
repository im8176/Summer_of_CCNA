# Week 02: Ethernet and Switching

## Topics Covered

- Ethernet basics
- MAC addresses
- Switches
- Frames
- Collision domains
- Broadcast domains
- ARP
- The MAC address table
- Basic switch forwarding decisions

## Key Terms

| Term | Meaning |
|---|---|
| Ethernet | A common networking standard used for wired local area networks |
| MAC Address | A unique hardware address assigned to a network interface |
| Frame | A Layer 2 data unit used to move data across a local network |
| Switch | A networking device that connects devices on a LAN and forwards frames |
| MAC Address Table | A table a switch uses to remember which MAC addresses are connected to which ports |
| Broadcast | A message sent to all devices in the local network |
| ARP | Address Resolution Protocol, used to find the MAC address that matches an IP address |
| Collision Domain | A network segment where devices could potentially compete to send data |
| Broadcast Domain | A group of devices that receive each other's broadcast traffic |

## What I Learned

This week I learned how Ethernet works at Layer 2 of the OSI model and how switches move traffic inside a local network. I learned that switches use MAC addresses, not IP addresses, to forward frames. I also learned that switches build a MAC address table by reading the source MAC address of incoming frames.

I also learned that ARP is used when a device knows the destination IP address but does not know the destination MAC address. ARP helps devices communicate on a local network by matching IP addresses to MAC addresses.

## How a Switch Forwards Traffic

When a switch receives a frame, it checks the source MAC address and learns which port that device is connected to. Then it checks the destination MAC address.

If the destination MAC address is already in the MAC address table, the switch forwards the frame only out the correct port.

If the destination MAC address is unknown, the switch floods the frame out all ports except the port it came in on.

## Example

PC1 wants to send data to PC2.

1. PC1 checks whether it knows PC2's MAC address.
2. If PC1 does not know the MAC address, it sends an ARP request.
3. The switch receives the frame and learns PC1's MAC address.
4. The ARP request is broadcast to the network.
5. PC2 replies with its MAC address.
6. The switch learns PC2's MAC address.
7. PC1 can now send traffic directly to PC2.
8. The switch forwards the frame only to the port where PC2 is connected.

## Commands Practiced

```bash
ping
ipconfig
arp -a
show mac address-table
show interfaces status
show running-config
```

## Packet Tracer Practice

### Lab Practiced

Basic switch communication between two or more PCs.

### Lab Goal

Connect multiple PCs to a switch, assign IP addresses, and verify that the devices can communicate on the same local network.

### Devices Used

- 1 switch
- 2 or more PCs
- Copper straight-through cables

### Verification Steps

- Checked PC IP addresses
- Used `ping` to test connectivity
- Used switch commands to inspect learned MAC addresses

## What I Struggled With

- Understanding the difference between IP addresses and MAC addresses
- Remembering that switches use MAC addresses to forward frames
- Understanding why ARP is needed before devices can communicate
- Understanding what happens when a switch does not know the destination MAC address

## How I Solved It

I reviewed the difference between Layer 2 and Layer 3. I practiced using Packet Tracer to watch how devices communicate through a switch. I also used commands like `arp -a` and `show mac address-table` to see how devices and switches store address information.

## What I Can Explain Now

By the end of this week, I can explain:

- What a MAC address is
- What an Ethernet frame is
- How a switch learns MAC addresses
- How a switch forwards known and unknown traffic
- What ARP does
- Why devices need both IP addresses and MAC addresses
- The difference between a broadcast and a unicast message

## Troubleshooting Notes

### Possible Issue

PC1 cannot ping PC2.

### Things to Check

- Are both PCs connected to the switch?
- Are the correct cables being used?
- Are both PCs in the same subnet?
- Are the IP addresses typed correctly?
- Are the switch ports active?
- Can the switch see the MAC addresses?

### Useful Commands

```bash
ping
ipconfig
arp -a
show mac address-table
show interfaces status
```
