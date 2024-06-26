# Project Discription

In this project the aim is to develop regression machine learning (ML) models to predict the solvation free energy of small drug molecules. The ML models are trained on a data set obtained from high level DFT calculations.  

**Step 1: Data Collection**

2586 small neutral drug molecules with one aromatic ring and molecular weight less than 150 are taken from the ChEMBL database. The "molecules_ChEMBL.sdf" file contains all these molecules.

**Step 2: Data Preparation**

Using the [RDKit package](https://www.rdkit.org/) and "structure_preparation_RDKit.ipynb" script, the structures are prepared for the DFT calculations. The structures are first converted to SMILES (smiles.smi file), then those molecules containing only H, C, N, and O atoms are collected and finally converted to XYZ coordinates.

**Step 3: Solvation Free Energy Calculations**

The DFT solvation free energy calculations are performed at STP condition (i.e. T = 298.15 K and P = 1 atm) using the [ORCA](https://orcaforum.kofo.mpg.de) quantum chemistry program package at an accurate level of theory: ωB97X-V functional with D4 London dispersion correction and def2-TZVP basis set. The structures are first optimized and then the frequency calculations are performed in the gas phase and aqueous solution using conductor-like polarizable continuum model (CPCM).  

**Step 4: ML Model Training**

ML models are trained on the reference dataset (solv_free_energy_dataset_HCNO.csv) using [DeepChem package](https://deepchem.io/) and the "MLModelsTrianing_DeepChem.ipynb" script. The data is spilit into training (90%) and test (10%) sets.

**Results:**

1) Model: Directed Message Passing Neural Network Model

   Pearson R2 Score: Train = 0.99; Test = 0.85

2) Model: Graph Convolutional Neural Network Model

   Pearson R2 Score: Train = 0.99; Test = 0.86
   
3) Model: SKlearn Linear Regression Model

   Pearson R2 Score: Train = 0.99; Test = 0.83
    
4) Model: Multitask Regression Model

   Pearson R2 Score: Train = 0.65; Test = 0.66
