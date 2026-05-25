# Week 04: Device Security and Management

## Topics Covered

- Cisco IOS command modes
- Device hostnames
- Login warning banners
- Enable secrets
- Password encryption
- Console line security
- VTY line security
- SSH-only remote access
- Switch management IP addresses
- Switch default gateways
- Router interface configuration
- Interface descriptions
- Saving configurations
- Verifying startup and running configurations
- Reload testing

## Lab Completed: District Shop Bring-Up

This week I completed the District Shop Bring-Up lab in Cisco Packet Tracer.

The lab required me to bring a small micro-campus network online using two access switches and one WAN edge router. I configured device identity, secured local and remote access, assigned management IP addresses, configured router and switch interfaces, saved the configurations, and verified that the settings remained active after reload.

## Devices Configured

| Device | Hostname | Role |
|---|---|---|
| Switch 1 | DS-07-SW1 | Access switch and management switch |
| Switch 2 | DS-07-SW2 | Access switch for WAP and server drops |
| Router 1 | DS-07-RTR1 | WAN edge router and management gateway |

## Addressing Used

| Device | Interface | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|---|
| DS-07-SW1 | Management SVI | 192.168.10.11 | 255.255.255.0 | 192.168.10.1 |
| DS-07-SW2 | Management SVI | 192.168.10.12 | 255.255.255.0 | 192.168.10.1 |
| DS-07-RTR1 | Inside Interface | 192.168.10.1 | 255.255.255.0 | N/A |

## Commands Practiced

```bash
enable
configure terminal
hostname
banner motd
enable secret
service password-encryption
line console 0
password
login
line vty 0 4
transport input ssh
interface vlan 1
ip address
ip default-gateway
description
no shutdown
show running-config
show startup-config
show ip interface brief
copy running-config startup-config
reload
```

## What I Learned

This week I learned how to perform a basic Cisco device bring-up for a small network. I practiced moving through Cisco IOS command modes, setting device hostnames, securing privileged access, configuring console and VTY passwords, and enabling password encryption.

I also learned how to configure management IP addresses on switches using a switch virtual interface, also called an SVI. I learned that switches need a default gateway when they need to communicate outside their local network.

On the router, I practiced assigning an IP address to the inside interface, adding an interface description, and using `no shutdown` to bring the interface online.

## Security Skills Practiced

- Configured hostnames for device identification
- Added a warning banner
- Configured an encrypted enable secret
- Secured console access
- Secured VTY access
- Limited VTY access to SSH
- Enabled password encryption
- Verified passwords were hidden in the running configuration

## Management Network Skills Practiced

- Configured switch management IP addresses
- Configured switch default gateways
- Configured router inside interface addressing
- Added interface descriptions
- Verified interface status
- Saved the running configuration
- Compared running and startup configurations
- Reloaded a device to confirm saved settings remained active

## Verification Commands Used

```bash
show running-config
show startup-config
show ip interface brief
show interfaces description
show clock
copy running-config startup-config
reload
```

## What I Struggled With

- Remembering which commands are entered in Global Configuration Mode
- Remembering which commands are entered under line configuration mode
- Making sure I used the correct interface before assigning an IP address
- Remembering to use `no shutdown`
- Remembering to save the running configuration before reloading the device

## How I Worked Through It

I worked through the lab step by step and used verification commands to confirm each part of the configuration. I checked the running configuration to make sure hostnames, banners, secrets, and passwords were applied correctly. I also checked interface status to make sure the management interfaces and router inside interface were active.

## What I Can Explain Now

By the end of this week, I can explain:

- How to rename a Cisco device
- How to configure a login warning banner
- Why `enable secret` is used
- Why `service password-encryption` is used
- How to secure console access
- How to secure VTY access
- What an SVI is used for
- How to configure a switch management IP address
- Why a switch needs a default gateway
- How to configure a router interface
- Why `no shutdown` is important
- How to save a Cisco device configuration
- How to verify that the saved configuration matches the running configuration

## Reflection

This week helped me understand how a network device is prepared for use before it is placed into production. The lab combined several important fundamentals, including identity, security, interface configuration, management addressing, verification, and saving configurations. It also showed me that entering commands is only part of the job. I also need to verify the work and make sure the configuration will survive a reload.
