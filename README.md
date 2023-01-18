**Project Discription**

In this project the aim is to develop machine (ML) learning models to predict the solvation free energy of small drug molecules. The ML models are trained on a data set obtained from high level DFT calculations.  

**Step 1: Data Collection**

2586 small neutral drug molecules with one aromatic ring and molecular weight less than 150 are taken from ChEMBL database. The "molecules_ChEMBL.sdf" file contains all these molecules.

**Step 2: Data Preparation**

Using the [RDKit package](https://www.rdkit.org/) and "structure_preparation_RDKit.ipynb" script, the structures are prepared for the DFT calculations. The molecules are first converted to SMILES (smiles.smi file) and then to XYZ coordinates.

**Step 3: Solvation Free Energy Calculation**

The DFT solvation free energy calculations are performed at STP condition (T = 298.15 K and P = 1 atm) using the [ORCA](https://orcaforum.kofo.mpg.de) quantum chemistry program package at a very accurate level of theory: wB97X-D4 functional and def2-TZVP basis set.

**Step 4: ML Model Training**

A Graph Convolutional Network model is trained on the reference dataset (solv_free_energy_dataset.csv) using the "GraphConvolutionalModel_DeepChem.ipynb" script and [DeepChem package](https://deepchem.io/). 
