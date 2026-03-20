# BGR 7nm Project - Navigation Index

## Quick Links

### Getting Started
- [README.md](README.md) - Main project overview with images
- [QUICKSTART.md](QUICKSTART.md) - Step-by-step guide to run simulations
- [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md) - Complete project summary

### Understanding the Design
- [THEORY.md](THEORY.md) - Circuit theory and design equations
- [results/README.md](results/README.md) - Detailed simulation analysis

### Design Files
- [circuits/bgr_main.sch](circuits/bgr_main.sch) - Xschem schematic
- [spice/bgr_vtc_sweep.spice](spice/bgr_vtc_sweep.spice) - SPICE netlist

### Device Models
- [models/asap_7nm_nfet.sym](models/asap_7nm_nfet.sym) - NFET symbol
- [models/asap_7nm_pfet.sym](models/asap_7nm_pfet.sym) - PFET symbol
- [models/bsimcmg.osdi](models/bsimcmg.osdi) - BSIMCMG model

### Images and Results
- [images/mainbgrckt.png](images/mainbgrckt.png) - Circuit schematic
- [images/mainbgrresults.png](images/mainbgrresults.png) - VTC sweep results
- [images/simdetails.png](images/simdetails.png) - Simulation commands

## Project Structure

```
BGR_7nm_Project/
│
├── INDEX.md                    ← You are here
├── README.md                   ← Start here for overview
├── QUICKSTART.md              ← Run your first simulation
├── THEORY.md                  ← Learn the theory
├── PROJECT_SUMMARY.md         ← Complete summary
│
├── circuits/
│   └── bgr_main.sch          ← Xschem schematic file
│
├── spice/
│   └── bgr_vtc_sweep.spice   ← Ready-to-run SPICE netlist
│
├── models/
│   ├── asap_7nm_nfet.sym     ← NFET device symbol
│   ├── asap_7nm_pfet.sym     ← PFET device symbol
│   └── bsimcmg.osdi          ← FinFET compact model
│
├── results/
│   └── README.md             ← Detailed results analysis
│
└── images/
    ├── mainbgrckt.png        ← Circuit schematic
    ├── mainbgrresults.png    ← Simulation results
    ├── simdetails.png        ← Simulation setup
    └── README.md             ← Image documentation
```

## Recommended Reading Order

### For Beginners
1. Start with [README.md](README.md) to understand what this project is about
2. Read [THEORY.md](THEORY.md) to learn bandgap reference basics
3. Follow [QUICKSTART.md](QUICKSTART.md) to run your first simulation
4. Review [results/README.md](results/README.md) to understand the results

### For Experienced Users
1. Check [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md) for quick overview
2. Go directly to [spice/bgr_vtc_sweep.spice](spice/bgr_vtc_sweep.spice) to run simulation
3. Review [results/README.md](results/README.md) for performance metrics
4. Modify circuit parameters and re-simulate

### For Researchers
1. Read [THEORY.md](THEORY.md) for design equations
2. Study [circuits/bgr_main.sch](circuits/bgr_main.sch) for topology
3. Analyze [results/README.md](results/README.md) for performance data
4. Use as reference for your own designs

## Key Features

✓ Complete working BGR circuit  
✓ Temperature sweep simulation (-25°C to 125°C)  
✓ Comprehensive documentation  
✓ Ready-to-run SPICE netlist  
✓ ASAP 7nm FinFET technology  
✓ Low voltage operation (0.7V)  
✓ Low power consumption (~20µA)  

## Quick Commands

### View Schematic
```bash
cd BGR_7nm_Project/circuits
xschem bgr_main.sch
```

### Run Simulation
```bash
cd BGR_7nm_Project/spice
ngspice bgr_vtc_sweep.spice
```

### View Results
Results are plotted automatically when simulation runs.

## Design Specifications

| Parameter | Value |
|-----------|-------|
| Vref | 310-320 mV |
| VDD | 0.7 V |
| IDD | ~20 µA |
| Temp Range | -25°C to 125°C |
| Temp Coeff | 0.14583 mV/K |
| R1 | 4.59 kΩ |
| R2 | 18.711 kΩ |

## Need Help?

- **Can't run simulation?** → See [QUICKSTART.md](QUICKSTART.md)
- **Don't understand results?** → See [results/README.md](results/README.md)
- **Want to learn theory?** → See [THEORY.md](THEORY.md)
- **Need quick overview?** → See [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md)

## What's Different from VSD Repo?

This project is reorganized for clarity:
- Focused on main BGR circuit only
- Added comprehensive documentation
- Included VTC sweep simulation
- Organized file structure
- Added theory and analysis documents

See [DIFFERENCES_FROM_VSD_REPO.md](DIFFERENCES_FROM_VSD_REPO.md) for details.

---

**Happy Simulating!** 🚀
