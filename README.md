# icolos_pmx_paper_2022

Input files, workflow configuration files and free energy values calculated in the paper:

## Automated relative binding free energy calculations: from SMILES to binding affinities

Investigated proteins:
  - tnks2
  - syk
  - ptp1b
  - p38

Docking approaches probed:
  - glide_naive: standard docking with Glide
  - glide_core_const: Glide docking with constraints on the core atoms
  - glide_mcs: Glide docking with mcs based constraints
  - vina_naive: standard docking with Vina
  - vina_filtered: docking with Vina followed by a filtering step to select the pose with the lowest RMSD to a reference ligand

Folders:
  - docking: results of docking for every protein system. sdf files contain the poses, pdb file contains protein structure. Edge mapping for further free energy calculations is in the log file. The log file also provides map for ligand naming used further for simulations.
  - simulation_data: for every system and docking protocol, the folder 'ligands' contains subfolders for each ligand with the topology and structure files. The folder 'protein' contains protein structure and topology files.
  - results: for every system and docking protocol, file resultsAll.csv provides all the calculated free energies. For each edge 3 independent replicas were performed. An edge consists of two legs: ligand transformation in water and ligand bound to protein. The first part of the resultsAll.csv lists values for each replica and separately. The second part of the file provides average over the replicas for every edge. 
  - mdp: Gromacs simulation parameter files
