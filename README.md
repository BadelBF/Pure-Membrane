## Building a Pure-Membrane system for MD simulations

### introduction
This tutorial shows how to build a pure bilayer membrane (100 % POPC) system using AmberTools26, as well as how to convert AMBER topology files (`.prmtop & .inpcrd`) into GROMACS input files (`.top & .gro`)

Step 1: Set up a conda environment for AmberTools26 through the link `https://anaconda.org/channels/conda-forge/packages/ambertools/overview`

Step 2: Run the command below to create a complete membrane bilayer system containing all molecules (membrane, water, and Ions), as well as the individual PDB files of these molecules.

```python3
packmol-memgen --lipids POPC --ratio 1 --dims 80 80 80 --dist_wat 15 --salt --salt_c Na+ --salt_a Cl- --saltcon 0.15
```

where:

`packmol-memgen`: Invokes the automated membrane-building workflow script. \
`--lipids POPC`: Sets the lipid composition to 100% POPC (1-palmitoyl-2-oleoyl-sn-glycero-3-phosphocholine), a standard model phospholipid for eukaryotic membranes. \
`--ratio 1`: Defines the molar ratio of the specified lipids. Since only one lipid (POPC) is listed, 1 represents a single-component membrane (100% POPC). \
`--dims 40 40 60`: Sets the target dimensions of the simulation box in Angstroms (Å) along the X, Y, and Z axes (80 Å X 80 Å X 80 Å). \
`--dist_wat 15`: Adds a water layer (solvation padding) of at least 15 Å above and below the lipid bilayer along the Z-axis. \
`--salt`: Adds neutralizing counterions and bulk salt ions to the water phase. \
`--salt_c Na+`: Specifies sodium (Na+)) as the positively charged cation. \
`--salt_a Cl-`: Specifies chloride (Cl-) as the negatively charged anion. \
`--saltcon 0.15`: Sets the bulk salt concentration to 0.15 M (150 mM), mimicking physiological saline conditions.


