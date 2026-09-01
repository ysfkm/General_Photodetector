# General PD

## Summary
- General-purpose photodetector board with 50MHz bandwidth: photodiode bias stage → first-stage TIA → DC/AC signal splitter → second-stage op-amps per path (DC and AC), with onboard ±12V/±5V regulation.
- Two variants sharing the same board/topology: a **Si version** (Hamamatsu S5971, 320–1060nm) and an **InGaAs version** (G12181-003K, 900–1900nm) with adjusted gain and feedback networks for the different photodiode characteristics.

## Specs
- **Input:** +15V, -15V, Laser incident on photodiode
- **Output:** DC & AC amplified signals
- **Power Regulators:** +12V, -12V, +5V, -5V
- **Description:** General purpose photodetector board with a bandwidth of 50MHz, consists of the photodiode bias stage, first stage TIA, a DC/AC splitting circuitry, then second stage op-amps for each path. Gain specified on the schematics.
- **Power Connectors** (Not from JLCPCB so specifically stated here):
  - Male Housing: F02-3P from Jinhua
  - Female Housing: F03-3P from Jinhua
- **PCB:** 45mm x 32mm / 4 Layer

## Si Version

### Photodiode: Hamamatsu S5971
- **Range:** 320~1060nm
- **Bandwidth:** 100MHz
- **Cj at 12V reverse bias:** ~2.75pF
- **Responsivity:** 0.64A/W @ Peak (920nm)

### First stage TIA: OPA818IDRGR
- No compensation R at non-inverting input needed (R2 in MPQ)

### Second stage op-amps
- **DC Path:** OPA211AIDRGR
- **AC Path:** OPA657U/2K5

### Power Regulators
- **+12V:** L7812ABUTR
  - Max current: 100mA
- **-12V:** L7912ACUTR
  - Max current: 100mA
- **+5V:** L7805ABUTR
  - Max current: 100mA
- **-5V:** L7905ABUTR
  - Max current: 100mA

## InGaAs Version

### Photodiode: G12181-003K
- **Range:** 900nm~1900nm
- **Bandwidth:** Typical 90MHz, Minimum 40MHz
  - Prompts the tradeoff of gain for bandwidth
- **Responsivity:** Typical 1.1A/W, Minimum 0.9A/W
- **Capacitance:** 25pF at 0V bias, ~10pF at 0.5V bias
- Different responsivity so slightly different gain for DC path
  - R5 = 4.585k
- Different feedback network required due to diode has lower bandwidth
  - R1 = 1.65k
  - R6 = 689
- Lower bias ~0.7V bias through resistive divider
  - Network: R10 = 6.2k & R11 = 1k
- No changes to rest of circuit
