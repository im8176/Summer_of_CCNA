# Basic LAN Setup Lab

## Objective

Build a simple local area network in Cisco Packet Tracer and verify that devices can communicate.

## Tools Used

- Cisco Packet Tracer
- PCs
- Switch
- Ethernet cables

## Network Topology

Screenshot will be added here.

## IP Addressing Table

| Device | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| PC1 | 192.168.1.10 | 255.255.255.0 | N/A |
| PC2 | 192.168.1.11 | 255.255.255.0 | N/A |

## Steps

1. Added two PCs and one switch.
2. Connected both PCs to the switch.
3. Assigned IP addresses to each PC.
4. Tested connectivity using ping.

## Verification

```bash
ping 192.168.1.11
```

## Result

PC1 successfully pinged PC2.

## What I Learned

This lab helped me understand how devices on the same local network communicate through a switch.
