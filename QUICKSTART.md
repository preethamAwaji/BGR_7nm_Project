# Quick Start Guide

## Prerequisites

- Xschem (Schematic Editor)
- Ngspice (SPICE Simulator)
- ASAP 7nm PDK
- BSIMCMG OSDI model support

## Directory Structure

```
BGR_7nm_Project/
├── circuits/          # Xschem schematic files
│   └── bgr_main.sch
├── spice/            # SPICE netlist files
│   └── bgr_vtc_sweep.spice
├── models/           # Device models and symbols
│   ├── asap_7nm_nfet.sym
│   ├── asap_7nm_pfet.sym
│   └── bsimcmg.osdi
├── results/          # Simulation results and analysis
│   └── README.md
└── images/           # Circuit diagrams and plots
```

## Running the Simulation

### Option 1: Using Xschem + Ngspice

1. Open the schematic in Xschem:
```bash
cd BGR_7nm_Project/circuits
xschem bgr_main.sch
```

2. In Xschem:
   - Press `F5` to generate netlist
   - Press `F6` to run simulation
   - View waveforms in the Ngspice window

### Option 2: Direct Ngspice Simulation

1. Navigate to the spice directory:
```bash
cd BGR_7nm_Project/spice
```

2. Run the temperature sweep:
```bash
ngspice bgr_vtc_sweep.spice
```

3. The simulation will automatically:
   - Load the BSIMCMG OSDI model
   - Sweep temperature from -25°C to 125°C
   - Plot Vref, Vctat, and PTAT component
   - Display results in a graph window

## Understanding the Output

The simulation produces three curves:

1. **Yellow (Vref)**: Final reference voltage
   - Should be relatively flat across temperature
   - Target: ~310-320 mV

2. **Red (Vctat)**: CTAT voltage
   - Decreases with temperature
   - Negative temperature coefficient

3. **Blue (Vref-Vctat)**: PTAT component
   - Increases with temperature
   - Positive temperature coefficient

## Modifying the Design

### Changing Resistor Values

Edit the SPICE file and modify:
```spice
R1 Vref Vctat 4.59K m=1      # PTAT resistor
R2 V3 V4 18.711K m=1         # CTAT resistor
```

### Changing Temperature Range

Modify the `.dc` statement:
```spice
.dc temp -25 125 2           # Start, Stop, Step
```

### Changing Supply Voltage

Modify the voltage source:
```spice
V1 VDD GND 0.7               # Change 0.7 to desired voltage
```

## Troubleshooting

### OSDI Model Not Found
- Ensure `bsimcmg.osdi` is in the `models/` directory
- Check the path in the SPICE file: `pre_osdi ../models/bsimcmg.osdi`

### Convergence Issues
- Try reducing temperature step size
- Adjust initial conditions
- Check for floating nodes

### No Plot Window
- Ensure X11 forwarding is enabled (Linux)
- Use `set hcopydevtype=postscript` for file output
- Check Ngspice installation

## Next Steps

1. Review simulation results in `results/README.md`
2. Experiment with different resistor ratios
3. Analyze supply voltage sensitivity
4. Explore process corner variations
5. Add output buffer stage for driving loads

## Support

For issues or questions:
- Check ASAP 7nm PDK documentation
- Review Ngspice manual
- Consult bandgap reference design literature
