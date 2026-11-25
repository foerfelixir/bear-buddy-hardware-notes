# CH32V003J4M6 pin map

These are the firmware-relevant pins on the Bear-Buddy IR remote. Confirm the physical package numbering against the traced schematic and your own board.

| MCU pin | Package pin | Firmware use | Notes |
|---:|---:|---|---|
| VDD | 1 | Supply | Verify the board's regulated MCU rail before connecting a programmer |
| PC1 | 2 | SW3 | Active-low button input, internal pull-up |
| PC2 | 3 | SW2 | Active-low button input, internal pull-up |
| PC4 | 5 | SW1 | Active-low button input, internal pull-up |
| PA2 / TIM1_CH2N | 12 | IR / indicator output | Active-low; timer generates the 38 kHz carrier |
| PD1 / SWIO | 13 | Programming/debug | WCH-LinkE in WCH-LinkRV / RISC-V mode |
| PD3 / SWCLK | 14 | Programming clock | Connect with common ground |
| NRST | 7 | Reset | Active low |
| VSS | 20 | Ground | Common with programmer and supply |

Button priority is SW1 > SW2 > SW3. The IR output gates the timer rather than generating the carrier in software.

## Programming

- Remove the battery before connecting the debugger.
- Confirm supply voltage and common ground.
- Flash source-backed `.bin` images at `0x08000000`.
- Configurable and Samsung builds provide a six-second SWIO window after reset/release; hold a button during Detect/Program.
- The NEC 200 ms build has only a three-second startup window and no post-release window.
