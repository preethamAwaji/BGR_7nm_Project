# Images Directory

This directory contains the circuit schematics and simulation results for the BGR project.

## Available Images

1. **mainbgrckt.png** - Main BGR circuit schematic showing:
   - PFET current mirror array (top)
   - NFET startup circuit (bottom)
   - Resistors R1 (4.59k) and R2 (18.711k)
   - Voltage nodes: Vref, Vctat, V1, V3, V4
   - Complete circuit topology with all connections

2. **mainbgrresults.png** - Temperature sweep simulation results showing:
   - Yellow curve: v(Vref) - Reference voltage (~310-320mV)
   - Red curve: v(Vctat) - CTAT voltage (decreasing with temp)
   - Blue curve: v(Vref)-v(Vctat) - PTAT component (increasing with temp)
   - X-axis: Temperature from -40°C to 140°C
   - Y-axis: Voltage in mV

3. **simdetails.png** - SPICE simulation commands showing:
   - `.dc temp -25 125 2` - Temperature sweep command
   - `.control` block with simulation control
   - `plot v(Vctat) v(Vref)-v(Vctat) v(Vref)` - Plot commands
   - Complete simulation setup

## Image Details

All images are from actual simulation runs and circuit schematics created in Xschem.

- Format: PNG
- Source: Xschem schematic capture and Ngspice simulation
- Technology: ASAP 7nm FinFET
