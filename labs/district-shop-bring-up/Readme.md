# Skill Lab 01: District Shop Bring-Up

## Objective

Build and secure a small micro-campus network for District Shop Delta-7 using Cisco Packet Tracer.

This lab focused on basic Cisco device deployment, including device identity, security hardening, management addressing, interface configuration, saving configurations, and verification.

## Scenario

Castle Rysen has opened District Shop Delta-7 and needs its micro-campus network brought online. The site includes two access switches and one WAN edge router. The goal is to configure the devices with secure access, management IP addresses, and proper documentation so the management team can reach the network from the bunker.

## Devices Used

| Device | Hostname | Role |
|---|---|---|
| Switch 1 | DS-07-SW1 | Access switch and management switch |
| Switch 2 | DS-07-SW2 | Access switch for WAP and server drops |
| Router 1 | DS-07-RTR1 | WAN edge router and management gateway |

## Addressing Table

| Device | Interface | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|---|
| DS-07-SW1 | VLAN 1 or Management SVI | 192.168.10.11 | 255.255.255.0 | 192.168.10.1 |
| DS-07-SW2 | VLAN 1 or Management SVI | 192.168.10.12 | 255.255.255.0 | 192.168.10.1 |
| DS-07-RTR1 | Inside Interface | 192.168.10.1 | 255.255.255.0 | N/A |

## Security Requirements

| Security Item | Configuration |
|---|---|
| Banner | `Castle Rysen Ops: Authorized engineers only.` |
| Enable Secret | `CrC0ffee!` |
| Console Password | `VaultAccess` |
| VTY Password | `ShelterAccess` |
| Password Encryption | Enabled with `service password-encryption` |
| Remote Access | SSH only |

## Skills Practiced

- Setting device hostnames
- Configuring login banners
- Setting an encrypted enable secret
- Securing console access
- Securing VTY remote access lines
- Limiting VTY lines to SSH
- Enabling password encryption
- Configuring switch management IP addresses
- Configuring switch default gateways
- Configuring router interface IP addresses
- Adding interface descriptions
- Bringing interfaces online with `no shutdown`
- Comparing running and startup configurations
- Saving configurations to non-volatile memory
- Reloading a device to confirm saved settings remain active

## Configuration Summary

### Device Identity

Each device was renamed to match its role in the District Shop network.

```bash
hostname DS-07-SW1
hostname DS-07-SW2
hostname DS-07-RTR1
```

### Warning Banner

A login banner was configured on each device.

```bash
banner motd #Castle Rysen Ops: Authorized engineers only.#
```

### Enable Secret

Privileged EXEC access was protected with an encrypted enable secret.

```bash
enable secret CrC0ffee!
```

### Password Encryption

Password encryption was enabled to hide plain-text passwords in the configuration.

```bash
service password-encryption
```

### Console Security

Console access was secured with a password and login requirement.

```bash
line console 0
password VaultAccess
login
exit
```

### VTY Security

Remote access lines were secured with a password, login requirement, and SSH-only transport.

```bash
line vty 0 4
password ShelterAccess
login
transport input ssh
exit
```

### Switch Management Interface

Each switch was assigned a management IP address and brought online.

DS-07-SW1:

```bash
interface vlan 1
ip address 192.168.10.11 255.255.255.0
no shutdown
exit
ip default-gateway 192.168.10.1
```

DS-07-SW2:

```bash
interface vlan 1
ip address 192.168.10.12 255.255.255.0
no shutdown
exit
ip default-gateway 192.168.10.1
```

### Router Inside Interface

The router inside interface was assigned the management gateway address.

```bash
interface g0/0
description Link to DS-07-SW1
ip address 192.168.10.1 255.255.255.0
no shutdown
exit
```

Note: The exact router interface may be different depending on the Packet Tracer device model. Use the interface that connects to DS-07-SW1.

## Interface Documentation

| Device | Interface | Description |
|---|---|---|
| DS-07-SW1 | Port to router | Link to DS-07-RTR1 |
| DS-07-SW1 | Port to switch | Link to DS-07-SW2 |
| DS-07-SW2 | Uplink port | Link to DS-07-SW1 |
| DS-07-SW2 | WAP port | Existing WAP drop |
| DS-07-SW2 | Server port | Existing server drop |
| DS-07-RTR1 | Inside interface | Link to DS-07-SW1 |

## Verification Commands

The following commands were used to verify the configuration:

```bash
show running-config
show startup-config
show ip interface brief
show interfaces description
show clock
copy running-config startup-config
reload
```

## Verification Checklist

- Hostnames show as `DS-07-SW1`, `DS-07-SW2`, and `DS-07-RTR1`
- Banner displays the Castle Rysen warning message
- `enable secret` appears encrypted in the running configuration
- Console password requires login
- VTY password requires login
- VTY access is limited to SSH
- Password encryption is enabled
- DS-07-SW1 management IP is `192.168.10.11/24`
- DS-07-SW2 management IP is `192.168.10.12/24`
- Both switches use `192.168.10.1` as the default gateway
- Router inside interface uses `192.168.10.1/24`
- Interfaces are active with `no shutdown`
- Running configuration was saved to startup configuration
- Device settings remained active after reload

## Packet Tracer File

Add the Packet Tracer file for this lab in this folder.

Example:

```markdown
[Download the Packet Tracer lab](file-name-here.pkt)
```

Replace `file-name-here.pkt` with the actual file name after uploading it.

## Screenshots

Add screenshots showing:

- Network topology
- Successful management IP configuration
- `show ip interface brief`
- `show running-config` showing encrypted enable secret
- `show startup-config`
- Successful reload verification

## What I Learned

This lab helped me practice bringing a small network online from a basic starting point. I learned how to configure device identity, secure access, set management IP addresses, configure router and switch interfaces, and verify that the configuration was saved correctly.

I also practiced using Cisco IOS command modes and learned why saving the running configuration is important. If the configuration is not copied to startup configuration, the device may lose its settings after a reload.

## Troubleshooting Notes

During this lab, common issues to check included:

- Incorrect interface selected on the router
- Switch management VLAN interface not active
- Missing `no shutdown` command
- Missing switch default gateway
- Passwords not requiring login because `login` was not configured
- VTY lines not limited to SSH
- Running configuration not saved before reload

## Final Result

District Shop Delta-7 was successfully brought online with hardened device access, management IP addresses, documented interfaces, saved configurations, and verified connectivity.
