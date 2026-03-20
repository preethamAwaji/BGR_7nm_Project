# BGR 7nm Project - File Structure

## Complete Organization

```
BGR_7nm_Project/
│
├── 📄 README.md                      # Main project overview with images
├── 📄 INDEX.md                       # Navigation guide
├── 📄 QUICKSTART.md                  # Quick start guide
├── 📄 THEORY.md                      # Circuit theory and equations
├── 📄 PROJECT_SUMMARY.md             # Complete project summary
├── 📄 DIFFERENCES_FROM_VSD_REPO.md   # Comparison with original repo
├── 📄 GITHUB_UPLOAD_GUIDE.md         # GitHub upload instructions
├── 📄 UPLOAD_SUCCESS.md              # Upload confirmation
├── 📄 .gitignore                     # Git ignore rules
│
├── 📁 circuits/                      # Circuit schematics
│   └── bgr_main.sch                 # Main BGR schematic (Xschem)
│
├── 📁 spice/                         # SPICE simulation files
│   └── bgr_vtc_sweep.spice          # Temperature sweep netlist
│
├── 📁 models/                        # Device models and symbols
│   ├── asap_7nm_nfet.sym            # NFET symbol file
│   ├── asap_7nm_pfet.sym            # PFET symbol file
│   └── bsimcmg.osdi                 # BSIMCMG compact model
│
├── 📁 images/                        # Circuit diagrams and results
│   ├── mainbgrckt.png               # BGR circuit schematic
│   ├── mainbgrresults.png           # VTC sweep results
│   ├── simdetails.png               # Simulation commands
│   ├── vtc_sweep_results.jpg        # Additional results
│   └── README.md                    # Image documentation
│
└── 📁 results/                       # Simulation analysis
    └── README.md                    # Detailed results analysis
```

## File Count by Category

| Category | Count | Description |
|----------|-------|-------------|
| Documentation | 8 | Markdown files in root |
| Circuit Files | 1 | Xschem schematic |
| SPICE Files | 1 | Simulation netlist |
| Device Models | 3 | Symbols and OSDI model |
| Images | 5 | PNG/JPG files + README |
| Results | 1 | Analysis documentation |
| **Total** | **19** | **All project files** |

## Directory Purpose

### Root Directory (/)
Contains all main documentation files that users see first:
- Project overview (README.md)
- Getting started guides
- Theory and background
- Project metadata

### circuits/
Xschem schematic files for circuit design and editing.

### spice/
SPICE netlist files ready for simulation with Ngspice.

### models/
Device models and symbol files required for simulation:
- FinFET device symbols
- BSIMCMG compact model

### images/
All visual content including:
- Circuit schematics
- Simulation results
- Setup screenshots

### results/
Detailed analysis and interpretation of simulation results.

## File Sizes

| File/Directory | Size | Notes |
|----------------|------|-------|
| models/bsimcmg.osdi | ~500 KB | Largest file |
| images/*.png | ~200 KB | Circuit images |
| circuits/bgr_main.sch | ~10 KB | Schematic |
| spice/*.spice | ~8 KB | Netlist |
| Documentation | ~50 KB | All markdown files |

## Access Patterns

### For Quick Start
1. README.md → Overview
2. QUICKSTART.md → Run simulation
3. spice/bgr_vtc_sweep.spice → Execute

### For Learning
1. INDEX.md → Navigation
2. THEORY.md → Understand concepts
3. circuits/bgr_main.sch → View design
4. results/README.md → Analyze results

### For Development
1. circuits/bgr_main.sch → Edit schematic
2. spice/bgr_vtc_sweep.spice → Modify simulation
3. models/ → Device parameters

## File Dependencies

```
bgr_main.sch
    ├── requires: models/asap_7nm_nfet.sym
    ├── requires: models/asap_7nm_pfet.sym
    └── generates: spice netlist

bgr_vtc_sweep.spice
    ├── requires: models/bsimcmg.osdi
    └── generates: simulation results

README.md
    ├── references: images/mainbgrckt.png
    ├── references: images/mainbgrresults.png
    └── references: images/simdetails.png
```

## Git Status

✅ All files tracked by Git  
✅ Proper .gitignore in place  
✅ Clean working directory  
✅ Synced with GitHub  

## Repository URL

https://github.com/preethamAwaji/BGR_7nm_Project

---

**Last Updated:** March 20, 2026  
**Total Files:** 19  
**Organization:** ✅ Complete
