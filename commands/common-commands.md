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
| `clock set HH:MM:SS MONTH DAY YEAR` | Privileged EXEC Mode | Manually sets the device date and time |
| `show clock` | Privileged EXEC Mode | Displays the current date and time on the device |

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
### Set the Date and Time

The `clock set` command is used to manually set the date and time on a Cisco device.

```bash
clock set 14:30:00 June 15 2025
```

This example sets the clock to:

```text
2:30 PM on June 15, 2025
```

### Verify the Date and Time

```bash
show clock
```

The `show clock` command displays the current date and time configured on the device.

## What I Learned

The `enable` command is used to access Privileged EXEC Mode. This gives more control over the device than basic User EXEC Mode.

The `configure terminal` command, or `conf t` for short, is used to enter Global Configuration Mode. This is where configuration changes are made to a Cisco device.

The `clock set` is used from Privileged EXEC Mode, not Global Configuration Mode.
- The time is entered in 24-hour format.
  
The `show clock` is used to verify the current date and time.
- Setting the correct time is useful because logs and troubleshooting messages depend on accurate timestamps.

## Notes

- `enable` does not configure the device by itself. It only changes the command mode.
- `configure terminal` is used after entering Privileged EXEC Mode.
- `conf t` is the shortened version of `configure terminal`.
