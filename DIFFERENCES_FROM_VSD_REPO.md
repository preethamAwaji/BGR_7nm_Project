# Differences from VSD Repository

## Overview

This BGR_7nm_Project is a reorganized and focused version derived from the [avsdbgr_7nm](https://github.com/sumanthdasari97/avsdbgr_7nm.git) repository. It's designed to be more accessible and focused on the main BGR circuit with VTC sweep analysis.

## Key Differences

### 1. Project Structure

**VSD Repo:**
```
avsdbgr_7nm/
├── xschem/
│   ├── Circuits/
│   │   ├── BGR_Current_mirror.sch
│   │   ├── CTAT_IDEAL_CURRENT_SOURCE.sch
│   │   ├── PTAT_Current_Mirror.sch
│   │   └── PTAT_IDEAL_CURRENT_SOURCE.sch
│   └── Spice_Files/
│       ├── BGR_Current_mirror.spice
│       ├── CTAT_IDEAL_CURRENT_SOURCE.spice
│       ├── PTAT_current_mirror.spice
│       └── PTAT_IDEAL_CURRENT_SOURCE.spice
├── bsimcmg.osdi
├── inverter_VTC.sch
└── README.md
```

**This Project:**
```
BGR_7nm_Project/
├── circuits/          # Schematic files
├── spice/            # SPICE netlists
├── models/           # Device models
├── results/          # Analysis documents
├── images/           # Circuit diagrams
└── Documentation files
```

### 2. Focus and Scope

**VSD Repo:**
- Includes multiple sub-circuits (PTAT, CTAT, BGR)
- Shows building blocks separately
- Educational progression from basics to complete circuit
- Includes ideal current source versions

**This Project:**
- Focuses on complete BGR circuit only
- Ready-to-simulate main circuit
- Emphasis on temperature sweep analysis
- Production-ready topology

### 3. Documentation

**VSD Repo:**
- Single comprehensive README
- Embedded images in README
- Theory mixed with results

**This Project:**
- Multiple focused documents (README, QUICKSTART, THEORY, etc.)
- Separate results analysis
- Organized image directory
- Navigation index

## What Was Added

✓ Comprehensive documentation structure  
✓ Quick start guide  
✓ Detailed theory document  
✓ Results analysis  
✓ Portable file paths  

## Acknowledgments

Based on the excellent work in the avsdbgr_7nm repository.

**Original Repository:** https://github.com/sumanthdasari97/avsdbgr_7nm.git
