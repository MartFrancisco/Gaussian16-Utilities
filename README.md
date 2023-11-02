# Gaussian16-Utilities

Hey everyone,

Lately, I found myself in a situation where I needed to perform scans with multiple files. I was looking at two reaction coordinates simultaneously – the dihedral and bond angle. While I know that G16 can handle this automatically, I ran into some issues along the way, mainly due to calculation crashes. It seems the scan range was causing the problem.

To work around this, I ended up creating numerous files where I kept one coordinate frozen while scanning the other. For example, I'd freeze the bond angle at 120 degrees and scan the dihedral, then freeze it at 130 degrees and scan the dihedral again. You can imagine the pile of files I had to deal with in the end.

That's when I thought it would be awesome to automate the task of extracting energies from each of these files and organizing them neatly into a table. Plus, it also calculates the relative energy for your dataset.

That's the simple idea behind this piece of code. My plan is to refine this code further in the coming days to enable the generation of potential energy surfaces.
[You can access here](https://github.com/MartFrancisco/Gaussian16-Utilities/blob/getting-scan-energies/Extract%20energy%20from%20scan%20calculation.ipynb).

