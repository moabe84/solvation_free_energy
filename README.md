# Project Discription

In this project the aim is to develop machine learning (ML) models to predict the solvation free energy of small drug molecules. The ML models are trained on a data set obtained from high level DFT calculations.  

**Step 1: Data Collection**

2586 small neutral drug molecules containing H, C, N, O, F, P, S, Cl, and Br atoms with one aromatic ring and molecular weight less than 150 are taken from the ChEMBL database. The "molecules_ChEMBL.sdf" file contains all these molecules.

**Step 2: Data Preparation**

Using the [RDKit package](https://www.rdkit.org/) and "structure_preparation_RDKit.ipynb" script, the structures are prepared for the DFT calculations. The molecules are first converted to SMILES (smiles.smi file) and then to XYZ coordinates.

**Step 3: Solvation Free Energy Calculations**

The DFT solvation free energy calculations are performed at STP condition (i.e. T = 298.15 K and P = 1 atm) using the [ORCA](https://orcaforum.kofo.mpg.de) quantum chemistry program package at a very accurate level of theory: ωB97X-V functional with D4 London dispersion correction and def2-TZVP basis set.

**Step 4: ML Model Training**

ML models are trained on the reference dataset (solv_free_energy_dataset.csv) using [DeepChem package](https://deepchem.io/) and the "MLModelsTrianing_DeepChem.ipynb" script:

**Results:**

1) Model: Graph Convolutional Network

   Pearson R2 Score: Train = 0.99; Test = 0.82; Validation = 0.83
   
2) Model: Multitask Regression Model

   Pearson R2 Score: Train = 0.99; Test = 0.71; Validation = 0.72
   
3) Model: Pytorch Linear Regression Model

   Pearson R2 Score: Train = 0.70; Test = 0.70; Validation = 0.67
   
4) Model: SKlearn Linear Regression Model

   Pearson R2 Score: Train = 0.65; Test = 0.62; Validation = 0.65
