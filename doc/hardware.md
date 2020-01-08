# Pineapple II

## Overview

Pineapple II has followirng ports.

* 4x GeekPort II (Analog and Digital I/O)
* MIDI In
* MIDI Out+ (MIDI Out + SPI)
* DC12V In
* Maintenance (USB)

## GeekPort II

### Type 1 (3.5mm TRRS jack)

| Pinout | Meaning       | Alternative mode |
|--------|---------------|------------------|
| Tip    | Power         | Power            |
| Ring 1 | Analog in     | Digital I/O      |
| Ring 2 | Plug detector | PWM out          |
| Sleeve | GND           | GND              |

### Type 2 (Hirose HR-10A)

| Pinout | Meaning       | Alternative mode |
|--------|---------------|------------------|
| 1      | Power         | Power            |
| 2      | GND           | GND              |
| 3      | Plug detector | PWM out          |
| 4      | Analog in     | Digital I/O      |
| 5      | I2C SDA       | Digital I/O      |
| 6      | I2C SCL       | Digital I/O      |

## Maintenance Port (2.5mm phone jack)

| Pinout | Meaning |
|--------|---------|
| Tip    | D-      |
| Ring 1 | D+      |
| Ring 2 | GND     |
| Sleeve | Vbus    |

## Front LEDs

| LED | Meaning  |
|-----|----------|
| 0/W | Status   |
| 1/R | Analog 1 |
| 2/G | Analog 2 |
| 3/B | Analog 3 |
| 4/Y | Analog 4 |

## MIDI OUT+ (DIN connector)

| MIDI Pin | Meaning | 1/8 Pin |
|----------|---------|---------|
| M1       | Vcc     |         |
| M2       | GND     | Sleeve  |
| M3       | 1-Wire  |         |
| M4       | Source  | Ring    |
| M5       | Drain   | Tip     |
| M6       | XLEDr   |         |
| M7       | XLEDg   |         |
| M8       | XLEDb   |         |

## MIDI IN+ (DIN connector)

| MIDI Pin | Meaning | 1/8 Pin |
|----------|---------|---------|
| m1       | NC      |         |
| m2       | NC      |         |
| m3       | NC      |         |
| m4       | Source  | Ring    |
| m5       | Drain   | Tip     |

## DC Jack

| DC Jack | Meaning |
|---------|---------|
| Center  | DC +12V |
| Sleeve  | GND     |

## Reset SW/LED

| SW/LED | Meaning                          |
|--------|----------------------------------|
| LED    | Power                            |
| SW     | Reset (double-push to boot-load) |

## MPU Pinout

| Pin Group     | Pin    | Arduino Micro | Connect to         | Via                |
|---------------|--------|---------------|--------------------|--------------------|
| **MIDI**      | IN     | D0 (RX)       | m5                 | B06                |
|               | OUT    | D1 (TX)       | M5                 | B11                |
|               | GPIO   |               |                    | B09                |
| **I2C**       | SDA    | D2            | Gx-5               | F05, F11. F17, F23 |
|               | SCL    | D3 (PWM)      | Gx-6               | F06, F12, F18, F24 |
| **Monitor**   | 0      | D13 (PWM)     | LED0, XLEDr        | F25, B12           |
|               | 1      | D4/A6         | LED1               | F27                |
|               | 2      | D5 (PWM)      | LED2, XLEDg        | F29, B13           |
|               | 3      | D8/A8         | LED3               | F31                |
|               | 4      | D11 (PWM)     | LED4, XLEDb        | F33, B14           |
| **Analog**    | 1      | A0            | G1-4/g1-R1         | F04                |
|               | 2      | A1            | G2-4/g2-R1         | F10                |
|               | 3      | A2            | G3-4/g3-R1         | F16                |
|               | 4      | A3            | G4-4/g4-R1         | F22                |
|               | PUP    | D7            | NC                 | NC                 |
| **Detector**  | 1      | A7/D6 (PMW)   | G1-3/g1-R2         | F03                |
|               | 2      | A9/D9 (PWM)   | G2-3/g2-R2         | F09                |
|               | 3      | A10/D10 (PMW) | G3-3/g3-R2         | F15                |
|               | 4      | A11/D12       | G4-3/g4-R2         | F21                |
| **Power**     | DC+12V | VIN           | P1                 | B01                |
|               | GND    | GND           | P2, M2, Gx-2/gx-S  | F02, F08, F14, F20 |
|               |        |               |                    | B02, B05, B08, B20 |
|               | GND+R  | ---           |                    | F26, F28, F30, F32 |
|               |        |               |                    | F34                |
|               | Vcc    | VCC           | M1                 | B07                |
|               | Vcc+R  | ---           | M4                 | B10                |
|               | Vout   | ---           | Gx-1/gx-T          | F01, F07, F13, F19 |
|               | Vdd    | 3V            | ---                | B19                |
| **Reset**     | RST    | RST           | SW1                | B03                |
| **Internal**  | THS    | A4            | Thermal sensor, M3 | B09                |
|               | RLY    | A5            | Thermal breaker    | NC                 |

## Board Connectors
### Front Connector (MIL 34p Connector)

| Pin | Meaning    | Connect to |
|-----|------------|------------|
| F01 | Vout       | G1-1/g1-T  | 
| F02 | GND        | G1-2/g1-S  |
| F03 | Detector 1 | G1-3/g1-R2 |
| F04 | Analog 1   | G1-4/g1-R1 |
| F05 | SDA        | G1-5       |
| F06 | SCL        | G1-6       |
| F07 | Vout       | G2-1/g2-T  | 
| F08 | GND        | G2-2/g2-S  |
| F09 | Detector 2 | G2-3/g2-R2 |
| F10 | Analog 2   | G2-4/g2-R1 |
| F11 | SDA        | G2-5       |
| F12 | SCL        | G2-6       |
| F13 | Vout       | G3-1/g3-T  | 
| F14 | GND        | G3-2/g3-S  |
| F15 | Detector 3 | G3-3/g3-R2 |
| F16 | Analog 3   | G3-4/g3-R1 |
| F17 | SDA        | G3-5       |
| F18 | SCL        | G3-6       |
| F19 | Vout       | G4-1/g4-T  | 
| F20 | GND        | G4-2/g4-S  |
| F21 | Detector 4 | G4-3/g4-R2 |
| F22 | Analog 4   | G4-4/g4-R1 |
| F23 | SDA        | G4-5       |
| F24 | SCL        | G4-6       |
| F25 | LED0       | LED0A      |
| F26 | GND        | LED0K      |
| F27 | LED1       | LED1A      |
| F28 | GND        | LED1K      |
| F29 | LED2       | LED2A      |
| F30 | GND        | LED2K      |
| F31 | LED3       | LED3A      |
| F32 | GND        | LED3K      |
| F33 | LED4       | LED4A      |
| F34 | GND        | LED4K      |

### Back Connector (MIL 20p Connector)

| Pin | Meaning        | Connect to |
|-----|----------------|------------|
| B01 | DC12V          | P1         |
| B02 | GND            | P2         |
| B03 | Reset          | SW1        |
| B04 | GND            | SW2        |
| B05 | MIDI IN Hot    | m4         |
| B06 | MIDI IN Cold   | m5         |
| B07 | Vcc            | M1         |
| B08 | GND            | M2         |
| B09 | 1W             | M3         |
| B10 | MIDI OUT Hot   | M4         |
| B11 | MIDI OUT Cold  | M5         |
| B12 | XLEDr          | M6         |
| B13 | XLEDg          | M7         |
| B14 | XLEDb          | M8         |
| B15 | MIDI OUT2 Hot  | NC         |
| B16 | MIDI OUT2 Cold | NC         |
| B17 | MIDI THRU Hot  | NC         |
| B18 | MIDI THRU Cold | NC         |
| B19 | Vdd            | NC         |
| B20 | GND            | NC         |

