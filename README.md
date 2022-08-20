# Predicting the Potency by Analysizing QASR activity of "Replicase polyprotein-1ab"


## Aim for this research
This study aims to identify compounds for in silico drug screenings of Replicase polyprotein 1ab, the principal protein in Severe acute respiratory syndrome caused by the Coronavirus. Molecular docking will be performed on the compounds with the highest potency while adhering to the Lipinski Rule of 5, which includes absorption, distribution, metabolism, and excretion.


## About the Protein
Replicase polyprotein-1a is a Multifunctional protein involved in the transcription and replication of viral RNAs. Contains the proteinases responsible for the cleavages of the polyprotein ( https://pubchem.ncbi.nlm.nih.gov/protein/P0C6X7 ). 

## Methadology

###Step1 
Import ChembllAPI and protein responsible for CoronaVirus

###Step2 
Filter the standard type as IC50

IC50 is half maximal inhibitory concentration is a measure of potency of a compound in inhibitting a special biological/biochemical function. It is needed to measure how much of a particular inhibitory substance is needed to inhibit a given biological component by 50%

### Step 3 - Handle Missing Values

Delete missing values and duplicates of cannoical smiles. Cannonical smile are the chemical properties descriptors of the protein termed as Assay descriptors.

### Step 3 - Labelling Compounds as active, inactive or intermediate. 

Thus corresponding to IC50, is their value as standard value. The values less than 1000Mn for that particular compound will be considered as active for that disease, and those more than 10,000Mn are considered inactive. And the value between 1000Mn to 10000Mn are considered as intermediate. 

Thus we shortlist the Molecule Id, Cannonical smile based on their standard value. 


### Step 3 - Compute Lipinski descriptors for compounds that have been compiled.

Install rdkit which has a library to compute Lipinski Descriptiors

Lipinski Descritprs is used to evaluate the likeness of the drug compound. 

The rule of describes molecular properties important for a drugs pharmacokinetics in the human body including their abosbtion, distribution, metabolism and excretion. 


Rules are:
1. No more than 5 hydrogen acceptors. 
2. No more than 10 hydrogen donors. 
3. A molecular mass less than 500 daltons
4. An Octanol-water partition coefficient that doesn't exceed 5

It's called rule of 5 because all of them are multiples of 5.

### Clean the data

1. Cap values of standard values and convert them into lograrithmic for easy gradient divergence. 
2. Remove intermediate and inavtive class. 
3. Create a scatter plot of molecular weight vs Logp   ----    molecular weight vs solubility
4. Perform Statistical Test : manhitneyu for all lipinski desciptors 


### Padel Descriptors

Padel Descriptors are used to convert the molecular descriptors into Pubchem descriptors. Converting Hydrogen, Nitrogen, Oxygen chemical bonds into categorical variables. 

Remove Salth and other impurities. 

### Train the model

Train the model with 30+ algorithms to recognize the potency with only it's compound and compare it with other models. 



















#####Refrences

PubChem. Replicase polyprotein 1ab (Severe acute respiratory syndrome-related coronavirus). Replicase polyprotein 1ab (Severe acute respiratory syndrome-related coronavirus) | Protein Target - PubChem.
