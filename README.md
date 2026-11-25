# Bear-Buddy IR Remote Hardware Notes

Private hardware documentation for the three-button CH32V003J4M6 IR remote included with the **Box 10 — Bear-Buddy DIY Desk Companion**, an awesome hardware kit designed by **TomatoCube**.

**Status:** private; not approved for public release.

## Schematic provenance

[`hardware/IR_Remote_PCB_Traced_Schematic.pdf`](hardware/IR_Remote_PCB_Traced_Schematic.pdf) was **reverse-engineered by physically tracing the PCB lines** on the actual remote. It is not a manufacturer-supplied schematic.

Verify every net against your own board before powering, programming, or fabricating hardware. See [`docs/reverse-engineering.md`](docs/reverse-engineering.md) for the evidence scope and limitations.

SHA-256:

```text
ccaeb465eab585a40274a1d206f8a9c4a2bba270ec970f4cf2d7012d7149bb2d
```

## Contents

- [`hardware/IR_Remote_PCB_Traced_Schematic.pdf`](hardware/IR_Remote_PCB_Traced_Schematic.pdf) — original traced schematic.
- [`hardware/SHA256SUMS`](hardware/SHA256SUMS) — artifact checksum.
- [`docs/pin-map.md`](docs/pin-map.md) — MCU pin functions used by the firmware.
- [`docs/reverse-engineering.md`](docs/reverse-engineering.md) — provenance, scope, and verification guidance.
- [`docs/credits.md`](docs/credits.md) — TomatoCube design credit and upstream references.

## MCU and firmware interface

The target is a WCH **CH32V003J4M6**. The firmware uses SW1/PC4, SW2/PC2, SW3/PC1, PA2/TIM1_CH2N for active-low IR output, and PD1/SWIO for programming.

Source-backed firmware lives in the separate private [Bear-Buddy IR remote repository](https://github.com/foerfelixir/bear-buddy-ir-remote).

## Credits

Special thanks to **TomatoCube** for the Bear-Buddy kit, hardware design, and detailed tutorial and documentation. The IR remote is part of the kit.

[Box 10 — Bear-Buddy DIY Desk Companion](https://github.com/TomatoCube18/Docs/tree/main/Box%2010%20-%20Bear-Buddy%20DIY%20Desk%20Companion)

## License

Hardware documentation and the traced schematic are provided under **Creative Commons Attribution-ShareAlike 3.0 Unported**; see [`LICENSE`](LICENSE). This does not imply endorsement by TomatoCube or WCH.
