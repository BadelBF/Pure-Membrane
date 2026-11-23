## Building a Pure-Membrane system for MD simulations

### introduction
This tutorial shows how to build a pure bilayer membrane (100 % POPC) system using AmberTools26, as well as how to convert AMBER topology files (`.prmtop & .inpcrd`) into GROMACS input files (`.top & .gro`)

Step 1: Set up a conda environment for AmberTools26 through the link `https://anaconda.org/channels/conda-forge/packages/ambertools/overview`

Step 2: Run the command below to create a complete membrane bilayer system containing all molecules (membrane, water, and Ions), as well as the individual PDB files of these molecules.

```python3
packmol-memgen --lipids POPC --ratio 1 --dims 40 40 60 --dist_wat 15 \
--salt --salt_c Na+ --salt_a Cl- --saltcon 0.15`
```
