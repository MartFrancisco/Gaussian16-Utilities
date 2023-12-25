# Gaussian16-Utilities

Hey everyone,

Lately, I found myself in a situation where I needed to perform scans with multiple files. I was looking at two reaction coordinates simultaneously – the dihedral and bond angle. While I know that G16 can handle this automatically, I ran into some issues along the way, mainly due to calculation crashes. It seems the scan range was causing the problem.

To work around this, I ended up creating numerous files where I kept one coordinate frozen while scanning the other. For example, I'd freeze the bond angle at 120 degrees and scan the dihedral, then freeze it at 130 degrees and scan the dihedral again. You can imagine the pile of files I had to deal with in the end.

That's when I thought it would be awesome to automate the task of extracting energies from each of these files and organizing them neatly into a table. Plus, it also calculates the relative energy for your dataset.

That's the simple idea behind this piece of code. My plan is to refine this code further in the coming days to enable the generation of potential energy surfaces.
[You can access here the code for taking energies from G16 .out files](https://github.com/MartFrancisco/Gaussian16-Utilities/blob/getting-scan-energies/Extract%20energy%20from%20scan%20calculation.ipynb).


# Smiles to Gaussian input .com files

[Here](https://github.com/MartFrancisco/Gaussian16-Utilities/tree/Smiles-to-gaussian-.com-input) you can access a python script that takes a list of molecules in SMILES format and covert into Gaussian input, .com, files.
How to use:


1) Paste the convert_smiles_xyz.py script in your bin folder and make it an executable file. 


2) Go to your work directory and create a txt file, [click here to check one example](https://github.com/MartFrancisco/Gaussian16-Utilities/blob/Smiles-to-gaussian-.com-input/smiles.txt), with the name of your molecule followed by one space and the SMILE string. Each line in your txt file should represent one molecule.


3) To execute the .py file just type "python ~/bin/convert_smiles_xyz.py smiles.txt" in your work directory. It will create all input files from smiles using default 32GB of memory, 32 processors, opt freq calculation in the wb97xd/def2svp level of theory, charge = 0, and multiplicity of 1.

You can also change these settings using the arguments --mem, --proc, --level, --charge, and --mult. For example: "python convert_smiles_xyz.py smiles.txt --mem 4 --proc 4 --level 'opt wb97xd/def2svp' --charge 1 --mult 3"

Ps. You need the OpenBabel software to run this code since it was built using it to convert SMILE string into XYZ coordinates.
