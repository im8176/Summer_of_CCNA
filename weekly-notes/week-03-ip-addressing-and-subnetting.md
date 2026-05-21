## New Commands and Skills Practiced

This week I practiced moving through Cisco IOS command modes, setting a privileged EXEC secret, and configuring an interface.

## Cisco IOS Command Mode Navigation

Cisco devices have different command modes. Each mode allows different types of commands.

| Mode | Prompt Example | What It Is Used For |
|---|---|---|
| User EXEC Mode | `Switch>` | Basic limited commands |
| Privileged EXEC Mode | `Switch#` | Verification, troubleshooting, and access to configuration mode |
| Global Configuration Mode | `Switch(config)#` | Device-wide configuration changes |
| Interface Configuration Mode | `Switch(config-if)#` | Configuration changes for a specific interface |

## Commands Practiced

```bash
enable
configure terminal
conf t
exit
end
```

## Setting a Privileged EXEC Secret

I learned that the `enable secret` command is used to protect access to Privileged EXEC Mode.

```bash
enable secret class
```

This command sets an encrypted password that is required when moving from User EXEC Mode to Privileged EXEC Mode.

Example:

```bash
Switch> enable
Password:
Switch#
```

## Configuring an Interface

I practiced entering interface configuration mode and configuring a specific interface.

```bash
interface gigabitEthernet 0/1
description Connection to PC1
no shutdown
```

The `interface` command selects the interface I want to configure. The `description` command adds a label to help identify what the interface connects to. The `no shutdown` command turns the interface on.

## What I Learned

This week helped me understand that Cisco IOS is organized by command modes. I learned that before making configuration changes, I need to move from User EXEC Mode to Privileged EXEC Mode, then into Global Configuration Mode.

I also learned how to set an `enable secret` to protect privileged access and how to enter interface configuration mode to make changes to a specific port.

## What I Can Explain Now

By the end of this week, I can explain:

- The difference between User EXEC Mode, Privileged EXEC Mode, Global Configuration Mode, and Interface Configuration Mode
- How to move between Cisco IOS command modes
- Why `enable secret` is used
- How to enter interface configuration mode
- Why `no shutdown` is used on an interface
- Why interface descriptions are helpful for documentation and troubleshooting
