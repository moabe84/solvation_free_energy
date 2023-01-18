**Project Discription**

In this project the aim is to develop machine (ML) learning models to predict the solvation free energy of small drug molecules. The ML models are trained on a data set obtained from high level DFT calculations.  

**Step 1:**

2586 small neutral drug molecules with 1 aromatic ring and molecular weight less than 150 are taken from ChEMBL database. The "molecules_ChEMBL.sdf" file contains all these molecules.

**Step 2:**

Using the [RDKit package](https://www.rdkit.org/) and "structure_preparation_RDKit.ipynb" script, the structures are prepared for the DFT calculations. The molecules are first converted to SMILES (smiles.smi file) and then to XYZ coordinates.

**Step 3:**

The DFT solvation free energy calculations are performed at STP condition (T = 298.15 K and P = 1 atm) using the [ORCA package](https://orcaforum.kofo.mpg.de) at a very accurate level of theory: wB97X-D4 functional and def2-TZVP basis set.

**Step 4:**

The data is collected in a CSV file (solv_free_energy_dataset.csv) constituted SMILESs and the corresponding calculated solvation free energy.

**Step 5:**

A Graph Convolutional Network model is trained on the reference dataset using the [DeepChem package] (https://deepchem.io/) and "GraphConvolutionalModel_DeepChem.ipynb" script.  
