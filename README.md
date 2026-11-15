# ZMK Config — Charybdis Nano (nice!nano, PMW3610 trackball)

Based on [zmk-config-skeletyl-dartyl](../zmk-config-skeletyl-dartyl), trackball setup from
[280Zo/charybdis-wireless-mini-zmk-firmware](https://github.com/280Zo/charybdis-wireless-mini-zmk-firmware).

## Hardware

- 2x nice!nano, BastardKB wireless flex-PCB matrix (`row2col`), 3x5 + 3/2 thumbs
- **Right half = central** (trackball half, connects to host), left = peripheral
- PMW3610 on right: SCK P0.08 (D0), SDIO P0.17 (D2), CS P0.20 (D3), MOTION P0.06 (D1)
- Matrix pins same as skeletyl; right thumbs are `RC(3,9) RC(3,7)` (pins 20, 6)

## Firmware

- `charybdis_nano_right` — central, with `zmk-usb-logging`
- `charybdis_nano_left`
- `settings_reset` — flash both halves with it before first flash / when pairing breaks

## Layout

Keymap from skeletyl, changes:
- right thumbs: `ENTER` (hold = RSHIFT), `mo 2`; RGUI on LOWER dropped
- `MOUSE` (6): auto-activates on trackball move; `J/K/L` = left/right/middle click, hold `H` = scroll
- `SCROLL` (7): trackball scrolls

Tuning: `config/boards/shields/charybdis_nano/charybdis_nano_pmw3610.dtsi`
(`cpi`, `zip_xy_scaler`, axis `swap-xy`/`invert-*`, auto-mouse timeout).
