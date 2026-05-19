# Common Networking Commands

This file documents networking and Cisco IOS commands I have learned during my Summer of CCNA studies.

## Cisco IOS Command Modes

Cisco devices use different command modes. Each mode gives access to different commands.

| Mode | Prompt Example | Purpose |
|---|---|---|
| User EXEC Mode | `Switch>` | Basic limited commands |
| Privileged EXEC Mode | `Switch#` | More advanced show and troubleshooting commands |
| Global Configuration Mode | `Switch(config)#` | Used to make configuration changes |

## Commands Learned

| Command | Mode | Purpose |
|---|---|---|
| `enable` | User EXEC Mode | Moves from User EXEC Mode into Privileged EXEC Mode |
| `configure terminal` | Privileged EXEC Mode | Moves into Global Configuration Mode so changes can be made to the device |
| `conf t` | Privileged EXEC Mode | Short version of `configure terminal` |

## Command Examples

### Enter Privileged EXEC Mode

```bash
enable
```

Example prompt change:

```bash
Switch>
Switch#
```

### Enter Global Configuration Mode

```bash
configure terminal
```

Short version:

```bash
conf t
```

Example prompt change:

```bash
Switch#
Switch(config)#
```

## What I Learned

The `enable` command is used to access Privileged EXEC Mode. This gives more control over the device than basic User EXEC Mode.

The `configure terminal` command, or `conf t` for short, is used to enter Global Configuration Mode. This is where configuration changes are made to a Cisco device.

## Notes

- `enable` does not configure the device by itself. It only changes the command mode.
- `configure terminal` is used after entering Privileged EXEC Mode.
- `conf t` is the shortened version of `configure terminal`.
