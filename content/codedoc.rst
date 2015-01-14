Code Documentation
------------------
This is the code documentation of the generate_pes code. Here you will find all the possible input keywords and documentation of the functions.

Keywords
--------
MOLINfo : specify molecular parameters [#atoms #modes] (NOT OPTIONAL)

GRIDIn : specify grid parameters [xmin #steps stepsize] (NOT OPTIONAL)

GEOMEtry : specify input geometry in cartesian coordinates on the form:
``[a1 a2 a3]
[a1x a1y a1z]
[a2z a2y a2z]
[a3x a3y a3z]``

DISPLacement : specify the displacement vectors in cartesian form: 
``a1x [mode1 mode2 mode3]
a1y [mode1 mode2 mode3]
a1z [mode1 mode2 mode3]
a2x [mode1 mode2 mode3]
a2y [mode1 mode2 mode3]
a2z [mode1 mode2 mode3]
a3x [mode1 mode2 mode3]
a3y [mode1 mode2 mode3]
a3z [mode1 mode2 mode3]``

