Introduction
------------

This project is the examination of the 5 hp Scientific software development toolbox (http://toolbox.readthedocs.org/en/latest/index.html). The aim of the project is to put to use the tools that were introduced during the course week on a project related to our own research.

As I am presently not involved in a software development project I decided to apply my new knowledge to the type of programs I often use in my day to day work, namely data pre- and post processing scripts. As my field of research is quantum chemistry these scrips most commonly involve reading energies and other chemical properties from computational program output, alternatively generation of molecular geometries for preparation of input files.

For this project I chose to work with a script that generates molecular geometries from displacement vectors obtained by normal mode analysis. The geometries are then used as input for quantum chemistry calculations of the potential energy surface along the vibrational mode of the vibrational coordinates of the molecule.

My plan was to first modularise the existing code so that it would easier to use and modify. More specifically I had in mind a code that could compute new geometries in different coordinate systems (in this case cartesian and Z-matrix form) and that could also create input to a kind of two dimensional potential energy surface obtained by combining the effect of displacement vectors of two vibrational modes.

After all this geometry generation and quantum chemistry calculation I actually use the potential energy surfaces(!) to calculate the resonant inelastic x-ray scattering by wave packet propagation. In this way we manage to include the decay of the intermediary state and study the vibrational excitation of the final state. 

