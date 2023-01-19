# Project Discription

In this project the aim is to develop machine learning (ML) models to predict the solvation free energy of small drug molecules. The ML models are trained on a data set obtained from high level DFT calculations.  

**Step 1: Data Collection**

2586 small neutral drug molecules with one aromatic ring and molecular weight less than 150 are taken from ChEMBL database. The "molecules_ChEMBL.sdf" file contains all these molecules.

**Step 2: Data Preparation**

Using the [RDKit package](https://www.rdkit.org/) and "structure_preparation_RDKit.ipynb" script, the structures are prepared for the DFT calculations. The molecules are first converted to SMILES (smiles.smi file) and then to XYZ coordinates.

**Step 3: Solvation Free Energy Calculations**

The DFT solvation free energy calculations are performed at STP condition (T = 298.15 K and P = 1 atm) using the [ORCA](https://orcaforum.kofo.mpg.de) quantum chemistry program package at a very accurate level of theory: ωB97X-V functional with D4 London dispersion correction and def2-TZVP basis set.

**Step 4: ML Model Training**

In this step, ML models are trained on the reference dataset (solv_free_energy_dataset.csv) using [DeepChem package](https://deepchem.io/):

1) Model: Graph Convolutional Network (Feature(s): SMILES and Label(s): Solvation Free Energy)

   Script: "GraphConvolutionalModel_DeepChem.ipynb"  
   
   Pearson R2 Score: Train = 0.99; Test = 0.80; Validation = 0.80
