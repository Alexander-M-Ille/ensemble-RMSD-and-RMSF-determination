README

The Python scripts presented here are custom versions of the RMSD and RMSF determination scripts originally from the CHARMM-GUI lecture series, available online at www.charmm-gui.org/?doc=lecture&module=scientific&lesson=11 and www.charmm-gui.org/?doc=lecture&module=scientific&lesson=12

Example input files/folders based on PDB ID 1SRB are available in the “Input Examples using PDB ID 1SRB” folder.

---------------------------------------------------------------
Structured Region RMSD Script
---------------------------------------------------------------

The structured region RMSD script determines the average C-alpha RMSD between two conformational ensembles for a user-specified region, i.e. range of amino acid residues. Each structure in one ensemble is aligned and compared with each structure in the other ensemble. The script takes an Excel file as input which in the first column (column A) lists the PDB ID, in the second column (column B) lists the specified structured region range for one ensemble, and in the third column (column C) lists the specified structured region range for the other ensemble. The specified structured regions may differ in terms of residue numbering, but must be of equal length. The format of the Excel file should be as outlined in the example below. Additionally, the script takes two folders as input, one folder for each of the two conformational ensembles to be compared, with each folder containing individual PDB files for each structural conformer of that ensemble. The script relies on the PDB ID provided in the input Excel file, so individual PDB file names must begin with the designated PDB ID but may also contain additional text. The script will output an Excel file listing the RMSD values for all of the compared structures as well as an average RMSD value. Folder/file paths must be designated in the code. An example input Excel file and two example conformational ensemble input folders are available in the “Input Examples using PDB ID 1SRB” folder.

Example for input Excel file format:
Column A, Row 1: “PDB_ID”
Column A, Row 2: “1SRB”
Column B, Row 1: “Folder 1 Range”
Column B, Row 2: “1-17”
Column C, Row 1: “Folder 2 Range”
Column C, Row 2: “1-17”

* Note that column titles (Row 1) in the input Excel file must be written exactly as in the example above (without quotation marks). Row 2 contents may be modified as desired by the user.

---------------------------------------------------------------
Per-residue RMSF and Global Delta RMSF Scripts
---------------------------------------------------------------

The per-residue RMSF script determines the C-alpha RMSF between all structures within one conformational ensemble. As input, the script takes a folder containing individual PDB files for each structural conformer of the ensemble. For RMSF calculation, the first PDB file in the input folder is used as the reference structure for alignment of all other structures within the folder. The script will output an Excel file listing each residue compared and the calculated RMSF value. Note that this script is for one ensemble, and its output is intended to be used as input for the global delta RMSF determination script, which compares the RMSF of two ensembles. Folder/file paths must be designated in the code. Two example conformational ensemble input folders are available in the “Input Examples using PDB ID 1SRB” folder.

The global delta RMSF script determines the average of the per-residue RMSF differences between two conformational ensembles. As input, the script takes two Excel files, one Excel file for each of the two conformational ensembles to be compared, as output by the per-residue RMSF script. For global delta RMSF calculation, the absolute difference of the RMSF value of each corresponding residue is summed and divided by the total number of residues.  The script will output an Excel file listing RMSF difference (delta RMSF) values and a single global delta RMSF value. File paths must be designated in the code.
