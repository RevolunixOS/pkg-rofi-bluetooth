# rofi-bluetooth

Rofi front end for `bluetoothctl`. It can show adapter status, toggle power,
scan for devices, change pairable/discoverable state, and pair, trust, connect,
or disconnect individual devices.

The script is based on
[`nickclyde/rofi-bluetooth`](https://github.com/nickclyde/rofi-bluetooth).

## Build and install

```bash
nix build github:RevolunixOS/pkg-rofi-bluetooth
nix profile install github:RevolunixOS/pkg-rofi-bluetooth
```

## Usage

Open the interactive menu:

```bash
rofi-bluetooth
```

Print a short status string for a bar or widget:

```bash
rofi-bluetooth --status
```

## Runtime requirements

- a working BlueZ service and Bluetooth adapter;
- `bluetoothctl`, `rfkill`, `bc`, and standard shell utilities;
- a graphical session capable of opening Rofi.

The current Nix wrapper only adds `rofi-wayland` to `PATH`; the other commands
must be provided by the host. Device pairing and trust changes are persistent
Bluetooth state changes, so verify the selected device before confirming.

## License

See [`LICENSE`](LICENSE) and the preserved upstream attribution in
`src/rofi-bluetooth`.
