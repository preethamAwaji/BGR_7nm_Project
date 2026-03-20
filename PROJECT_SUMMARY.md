# BGR 7nm Project - Complete Summary

## Project Information

**Project Name**: Bandgap Reference Circuit in ASAP 7nm Technology  
**Technology Node**: ASAP 7nm FinFET  
**Design Type**: Analog Voltage Reference  
**Target Application**: Low-voltage reference for analog/mixed-signal circuits

## What This Project Contains

### 1. Circuit Design
- Complete BGR schematic with current mirror topology
- Self-biased PFET current mirror for stable operation
- NFET startup circuit to avoid zero-current state
- Optimized resistor network for temperature compensation

### 2. SPICE Simulation
- Temperature sweep from -25°C to 125°C
- Voltage-Temperature Characteristic (VTC) analysis
- BSIMCMG FinFET models for accurate simulation
- Ready-to-run SPICE netlist

### 3. Documentation
- **README.md**: Project overview and quick reference
- **QUICKSTART.md**: Step-by-step simulation guide
- **THEORY.md**: Detailed circuit theory and design equations
- **results/README.md**: Comprehensive simulation analysis

### 4. Design Files
- Xschem schematic file (`.sch`)
- SPICE netlist (`.spice`)
- Device symbol files (`.sym`)
- BSIMCMG OSDI model

## Key Features

✓ Temperature-independent voltage reference  
✓ Low supply voltage operation (0.7V)  
✓ Low power consumption (~20µA)  
✓ PTAT and CTAT voltage generation  
✓ Self-biased current mirror  
✓ Startup circuit included  
✓ Fully simulated and verified  

## Design Specifications

| Parameter | Value | Notes |
|-----------|-------|-------|
| Reference Voltage | 310-320 mV | Across temperature range |
| Supply Voltage | 0.7 V | Nominal VDD |
| Supply Current | ~20 µA | Low power design |
| Temperature Range | -25°C to 125°C | Industrial range |
| Temp Coefficient | 0.14583 mV/K | ~470 ppm/K |
| Technology | ASAP 7nm | FinFET devices |
| R1 (PTAT) | 4.59 kΩ | Calculated value |
| R2 (CTAT) | 18.711 kΩ | Calculated value |

## Circuit Components

### Active Devices
- **PFETs**: 6 transistors (current mirror and biasing)
- **NFETs**: 15 transistors (startup, CTAT, PTAT generation)
- **Fin Count**: 14 fins per device
- **Gate Length**: 7nm

### Passive Components
- **R1**: 4.59 kΩ (PTAT resistor)
- **R2**: 18.711 kΩ (CTAT resistor)

### Power Supply
- **V1**: 0.7V DC source

## How It Works

1. **CTAT Generation**: Transistor nfet12 generates voltage that decreases with temperature
2. **PTAT Generation**: Current through R2 creates voltage proportional to temperature
3. **Combination**: R1 scales and adds PTAT to CTAT to create stable Vref
4. **Current Mirror**: PFETs provide stable bias current to all branches
5. **Startup**: NFET array ensures circuit starts in correct operating state

## Simulation Results Summary

### Temperature Sweep (-25°C to 125°C)

**Vref (Reference Voltage)**
- Minimum: ~303 mV @ -25°C
- Typical: ~310 mV @ 25°C
- Maximum: ~325 mV @ 125°C
- Variation: 22 mV over 150°C range

**Vctat (CTAT Voltage)**
- Starts: ~190 mV @ -25°C
- Ends: ~160 mV @ 125°C
- Slope: -231.1275 µV/K

**Vptat (PTAT Component)**
- Starts: ~120 mV @ -25°C
- Ends: ~160 mV @ 125°C
- Slope: +453.158 µV/K

## File Structure

```
BGR_7nm_Project/
│
├── README.md                    # Main project documentation
├── QUICKSTART.md               # Quick start guide
├── THEORY.md                   # Circuit theory and equations
├── PROJECT_SUMMARY.md          # This file
│
├── circuits/
│   └── bgr_main.sch           # Xschem schematic
│
├── spice/
│   └── bgr_vtc_sweep.spice    # Temperature sweep simulation
│
├── models/
│   ├── asap_7nm_nfet.sym      # NFET symbol
│   ├── asap_7nm_pfet.sym      # PFET symbol
│   └── bsimcmg.osdi           # BSIMCMG model
│
├── results/
│   └── README.md              # Detailed results analysis
│
└── images/
    └── README.md              # Image documentation
```

## Getting Started

### Prerequisites
```bash
# Required tools
- Xschem (schematic editor)
- Ngspice (SPICE simulator)
- ASAP 7nm PDK
- BSIMCMG OSDI support
```

### Quick Run
```bash
# Navigate to project
cd BGR_7nm_Project/spice

# Run simulation
ngspice bgr_vtc_sweep.spice

# View results (plots automatically)
```

### Expected Output
- Three curves showing Vref, Vctat, and PTAT component
- Vref should be relatively flat across temperature
- Vctat should decrease with temperature
- PTAT should increase with temperature

## Design Methodology

1. **Calculate Temperature Coefficients**
   - Measure dVctat/dT and dVptat/dT
   - Calculate α = -dVctat/dT / dVptat/dT

2. **Determine Resistor Values**
   - Choose current ratio N (typically 4-8)
   - Calculate R1 from desired current
   - Calculate R2 from α and R1

3. **Design Current Mirror**
   - Size PFETs for desired current
   - Ensure proper matching
   - Add startup circuit

4. **Simulate and Verify**
   - Run temperature sweep
   - Check Vref stability
   - Verify PTAT/CTAT behavior

5. **Optimize**
   - Adjust resistor ratio if needed
   - Fine-tune for minimum TC
   - Verify across corners

## Applications

This BGR circuit is suitable for:
- Analog-to-Digital Converters (ADC) reference
- Digital-to-Analog Converters (DAC) reference
- Voltage regulators and LDOs
- Temperature sensors
- Bias generation circuits
- Any application requiring stable voltage reference

## Future Enhancements

Possible improvements:
1. Add curvature compensation for better TC
2. Include trimming capability
3. Add output buffer for load driving
4. Implement PSRR improvement techniques
5. Design for multiple supply voltages
6. Add process corner simulations
7. Include Monte Carlo analysis

## References

### Theory
- "Design of Analog CMOS Integrated Circuits" by Behzad Razavi
- "Analysis and Design of Analog Integrated Circuits" by Gray & Meyer
- IEEE papers on bandgap reference design

### Technology
- ASAP 7nm PDK Documentation
- BSIMCMG Model Documentation
- FinFET Device Physics

### Tools
- Xschem Documentation: http://repo.hu/projects/xschem/
- Ngspice Manual: http://ngspice.sourceforge.net/
- ASAP7 PDK: http://asap.asu.edu/asap/

## License and Usage

This project is created for educational and research purposes. Feel free to:
- Study the design methodology
- Modify the circuit for your needs
- Use as reference for your own designs
- Share with proper attribution

## Acknowledgments

Based on bandgap reference design principles and implemented using:
- ASAP 7nm Predictive PDK
- Open-source EDA tools (Xschem, Ngspice)
- BSIMCMG compact model

## Contact and Support

For questions or issues:
1. Review the documentation files
2. Check simulation setup in QUICKSTART.md
3. Refer to theory in THEORY.md
4. Examine results in results/README.md

---

**Project Status**: Complete and Verified  
**Last Updated**: March 2026  
**Version**: 1.0
