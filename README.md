# zmk-config-totem

ZMK user-config repository for a TOTEM split keyboard using the Seeed XIAO BLE.

## Build target note

This repo tracks current `zmkfirmware/zmk@main` via GitHub Actions.
With newer ZMK/Zephyr 4.1 board-variant rules, the build target must use the ZMK board variant form:

- `xiao_ble//zmk`

instead of the older:

- `xiao_ble`

That change is applied in `build.yaml`.

## GitHub Actions build

Workflow:
- `.github/workflows/build.yml`

Matrix source:
- `build.yaml`

Current build targets:
- `xiao_ble//zmk + totem_left + studio-rpc-usb-uart`
- `xiao_ble//zmk + totem_right`

## Latest verified successful build

GitHub Actions run:
- `24002896964`
- URL: `https://github.com/koalav/zmk-config-totem/actions/runs/24002896964`

Generated firmware files:
- `totem_left-xiao_ble__zmk-zmk.uf2`
- `totem_right-xiao_ble__zmk-zmk.uf2`

## Flashing note

Use the matching UF2 for each half:
- left half -> `totem_left-xiao_ble__zmk-zmk.uf2`
- right half -> `totem_right-xiao_ble__zmk-zmk.uf2`

Typical flow is to put the controller into bootloader mode and copy the UF2 file onto the mounted boot drive for that half.
