# Stanford RNA-3D-Folding
Overview If you sat down to complete a puzzle without knowing what it should look like, you’d have to rely on patterns and logic to piece it together. In the same way, predicting Ribonucleic acid (RNA)’s 3D structure involves using only its sequence to figure out how it folds into the structures that define its function.
Develop machine learning models to predict an RNA molecule’s 3D structure from its sequence. The goal is to improve our understanding of biological processes and drive new advancements in medicine and biotechnology.
Description:
RNA is vital to life’s most essential processes, but despite its significance, predicting its 3D structure is still difficult. Deep learning breakthroughs like AlphaFold have transformed protein structure prediction, but progress with RNA has been much slower due to limited data and evaluation methods.

Data Descriptions:
Files

[train/validation/test]_sequences.csv - the target sequences of the RNA molecules.

target_id - (string) An arbitrary identifier. In train_sequences.csv, this is formatted as pdb_id_chain_id, where pdb_id is the id of the entry in the Protein Data Bank and chain_id is the chain id of the monomer in the pdb file.
sequence - (string) The RNA sequence. For test_sequences.csv, this is guaranteed to be a string of A, C, G, and U. For some train_sequences.csv, other characters may appear.
temporal_cutoff - (string) The date in yyyy-mm-dd format that the sequence was published. See Additional Notes.
description - (string) Details of the origins of the sequence. For a few targets, additional information on small molecule ligands bound to the RNA is included. You don't need to make predictions for these ligand coordinates.
all_sequences - (string) FASTA-formatted sequences of all molecular chains present in the experimentally solved structure. In a few cases this may include multiple copies of the target RNA (look for the word "Chains" in the header) and/or partners like other RNAs or proteins or DNA. You don't need to make predictions for all these molecules; if you do, just submit predictions for sequence. Some entries are blank.
[train/validation]_labels.csv - experimental structures.

ID - (string) that identifies the target_id and residue number, separated by _. Note: residue numbers use one-based indexing.
resname - (character) The RNA nucleotide ( A, C, G, or U) for the residue.
resid - (integer) residue number.
x_1,y_1,z_1,x_2,y_2,z_2,… - (float) Coordinates (in Angstroms) of the C1' atom for each experimental RNA structure. There is typically one structure for the RNA sequence, and train_labels.csv curates one structure for each training sequence. However, in some targets the experimental method has captured more than one conformation, and each will be used as a potential reference for scoring your predictions. validation_labels.csv has examples of targets with multiple reference structures (x_2,y_2,z_2, etc.).
sample_submission.csv

Same format as train_labels.csv but with five sets of coordinates for each of your five predicted structures (x_1,y_1,z_1,x_2,y_2,z_2,…x_5,y_5,z_5).
Source Data:
kaggle competitions download -c stanford-rna-3d-folding
Kaggale

Citation: 
Shujun He, CASP16 organizers, CASP16 RNA experimentalists, RNA-Puzzles consortium, VFOLD team, Rachael Kretsch, Alissa Hummer, Andrew Favor, Walter Reade, Maggie Demkin, Rhiju Das, et al. Stanford RNA 3D Folding. https://kaggle.com/competitions/stanford-rna-3d-folding, 2025. Kaggle.

