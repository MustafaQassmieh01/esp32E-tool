# MQ-LAB board target

Custom Bruce target for the 2.4-inch ESP32 touchscreen board used by MQ-LAB.

## Confirmed hardware

- ESP32-D0WD-V3 rev 3.1
- 4 MB flash
- 320x240 SPI TFT
- Resistive touch controller
- microSD slot

### Display

| Signal | GPIO |
|---|---:|
| MISO | 12 |
| MOSI | 13 |
| SCLK | 14 |
| CS | 15 |
| DC | 2 |
| Backlight | 21 |

### Resistive touch

| Signal | GPIO |
|---|---:|
| MISO | 39 |
| MOSI | 32 |
| CLK | 25 |
| CS | 33 |
| IRQ | 36 |

### microSD

| Signal | GPIO |
|---|---:|
| CS | 5 |
| SCLK | 18 |
| MISO | 19 |
| MOSI | 23 |

## Touch calibration

Current measured values:

```text
X min: 480
X max: 3580
Y min: 350
Y max: 3760
```

These were measured on the physical MQ-LAB unit and may need small adjustment on another panel.

## Build

```bash
pio run -e MQ-LAB
```

## First hardware validation

1. Confirm the Bruce UI renders correctly.
2. Confirm touch orientation and button accuracy.
3. Confirm SD detection.
4. Then validate external PN532, CC1101 and nRF24 modules one at a time.
