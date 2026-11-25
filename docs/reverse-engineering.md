# Reverse-engineering notes

## Provenance

The included schematic was reconstructed by **physically tracing the PCB lines** on the actual three-button remote. The Bear-Buddy hardware design is by **TomatoCube**; no manufacturer schematic was used, and the PDF is not presented as an official drawing.

The user-supplied PDF is preserved byte-for-byte as [`hardware/IR_Remote_PCB_Traced_Schematic.pdf`](../hardware/IR_Remote_PCB_Traced_Schematic.pdf). Its SHA-256 is recorded in [`hardware/SHA256SUMS`](../hardware/SHA256SUMS).

## Scope

The reconstruction documents the nets needed to understand the MCU, button inputs, IR output driver, programmer interface, reset, and power connections. Firmware references the following pins:

| Function | Pin |
|---|---|
| SW1 | PC4 |
| SW2 | PC2 |
| SW3 | PC1 |
| IR / indicator output | PA2 / TIM1_CH2N |
| SWIO | PD1 |
| SWCLK | PD3 |

## Limitations

- Component tolerances, exact part markings, and production substitutions are not guaranteed.
- Silkscreen or assembly labels may differ between kit revisions.
- The schematic is an engineering aid, not fabrication data.
- Continuity, voltage, polarity, and pin assignments must be checked on the specific board before use.

Do not apply external power or connect a programmer until the board's supply rails and ground have been identified and verified.
