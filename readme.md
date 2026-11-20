# Diode Reverse Recovery & RC Snubber Simulation (MATLAB/Simulink)

This project simulates diode reverse recovery in an inductive AC circuit using **Simscape Electrical** in **MATLAB/Simulink (R2024b)**. It demonstrates the turn-off voltage spike and ringing caused by stored charge (`Reverse Current`) interacting with an inductor, and shows how adding a parallel **RC Snubber** damps the transient.

## Model Overview

- **File:** `Dynamic_turnoff.slx`
- **Environment:** MATLAB / Simulink R2024b (Simscape Electrical)
- **Main Components:**
  - AC Voltage Source
  - Diode (with reverse recovery dynamics)
  - Series Resistor & Inductor load
  - Parallel RC Snubber across the inductor
  - Voltage & Current Sensors connected to a Scope

## Simulation Results

1. **Before Adding the RC Snubber:**
   - During diode turn-off (~0.57 ms), reverse recovery current interacts with the inductor, producing a sharp voltage spike reaching **~67 V** followed by sustained high-frequency ringing.
2. **After Adding the RC Snubber:**
   - Placing a series RC branch in parallel with the inductor absorbs the fast transient, dropping the peak spike to **~17 V** and damping the oscillation almost immediately.

## How to Run

1. Open `Dynamic_turnoff.slx` in MATLAB/Simulink (R2024b or later with Simscape Electrical installed).
2. Click **Run** and open the **Scope** block to inspect the inductor voltage and circuit current waveforms.
