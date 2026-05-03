# Bipolar-Pulse-Power-Supply-Unit-for-Electrochemical-Machining-ECM-
## Overview
This project presents the design and simulation of a two-stage bipolar high-voltage pulsed power source (BHVPPS) for electrochemical machining (ECM) applications. The work was carried out to an external commercial specification provided by TextureJet Ltd., targeting a bipolar square-wave output of ±150 V / ±20 A at frequencies up to 330 kHz with a minimum pulse width of 0.5 µs.The converter topology, based on the work of Malviya and Veerachary (2020), combines a front-end boost stage with a Marx-style capacitor discharge network to generate high bipolar voltages from a low DC input (12.5 V). The full design was validated through time-domain simulation in LTspice using ideal voltage-controlled switches.

## How it works
### Operating Principle
The BHVPPS operates through six switching modes per cycle to produce a complete bipolar pulse:
(+V) → (0 V) → (−V) → (0 V) → (+V) → ...
```
Mode 1 — Positive pulse delivery: Boost switch S_B and all positive switches S_Pi are on. The inductor charges from the input while the series-connected capacitors deliver a positive voltage pulse across the load.
Mode 2 — Dead time: Only S_B conducts. The inductor continues charging; capacitors hold their voltage; the load sees zero volts.
Mode 3 — Negative pulse delivery: Mirrors Mode 1 with reversed polarity via the negative switches S_Ni.
Mode 4 — Dead time: Same as Mode 2.
Mode 5 — Capacitor recharge: S_B turns off and the charging switches S_Ci turn on. The inductor's stored energy is transferred to the stage capacitors, which are connected in parallel and charged equally.
Mode 6 — Hold: All switches off; capacitors hold their voltages until the next cycle begins.
```
