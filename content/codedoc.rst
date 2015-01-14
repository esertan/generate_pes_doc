Code Documentation
------------------
This is the code documentation of the generate_pes code. Here you will find all the possible input keywords and documentation of the functions.

Keywords
********
``MOLINfo`` : specify molecular parameters ``[#atoms #modes]`` (NOT OPTIONAL)

``GRIDIn`` : specify grid parameters ``[xmin #steps stepsize]`` (REQUIRED)

``GEOMEtry`` : specify input geometry in cartesian coordinates on the form (REQUIRED) ::
 
    [a1 a2 a3]
    [a1x a1y a1z]
    [a2z a2y a2z]
    [a3x a3y a3z]

``DISPLacement`` : specify the displacement vectors in cartesian form (REQUIRED)::
 
    [mode1 mode2 mode3] a1x
    [mode1 mode2 mode3] a1y
    [mode1 mode2 mode3] a1z
    [mode1 mode2 mode3] a2x
    [mode1 mode2 mode3] a2y
    [mode1 mode2 mode3] a2z
    [mode1 mode2 mode3] a3x
    [mode1 mode2 mode3] a3y
    [mode1 mode2 mode3] a3z

``INTERnal`` : specify the displacement vectors in internal (Z-matrix) form (OPTIONAL) ::

    [r1 r2 theta] mode1
    [r1 r2 theta] mode2
    [r1 r2 theta] mode3

``2DIMEnsional`` : specify generation of 2 dimensional geometry by combination of two vibrational modes (OPTIONAL, ``INTERnal`` REQUIRED)::

    [mode1 mode2]
    [xmin #steps stepsize]

``END OF INPUT`` : EOF marker (REQUIRED)

Function doc
************
    ::

        function integer function read_key(checkkey)

In module ``pes_init`` :
Function reads keyword from input and compares in to character input. Returns 1 if keyword matches character else 0.

    ::

        subroutine get_molinfo(maxatoms, maxmodes)

In module ``pes_init`` :
Subroutine reads number of atoms and number of modes from input and stores them in the variables maxatom and maxmodes.

    ::

        subroutine get_gridinfo(xmin, step, ssize)

In module ``pes_init`` :
Subroutine reads grid parameters from input and stores them in variables xmin, steps and ssize.
    
    ::
    
        subroutine allocate_arrays(...)

In module ``pes_init`` :
Subroutine allocates arrays for atom positions and displacements.

    ::

        subroutine allocate_2d_arrays(...)

In module ``pes_init`` :
Subroutine allocates arrays for atom positions and displacements (if Keyword ``2DIMEnsional`` is active).

    ::

        subroutine deallocate_arrays(...)

In module ``pes_init`` :
Subroutine deallocates arrays.

    ::

        subroutine deallocate_2d_arrays(...)
      
In module ``pes_init`` :
Subroutine deallocates arrays (if keyword ``2DIMEnsional`` is active).

    ::

        subroutine init_geo(xyz0, maxatoms, aname)

In module ``pes_init`` :
Subroutine reads in atom names and initial geometry from input in cartesian coordinates (Angstrom).

    ::

        subroutine init_internal_geo(xyz0, r01, r02, a0)

In module ``pes_init`` :
Subroutine converts the initial geometry to internal coordinates.

    ::

        subroutine read_cartd(dxyz, maxatoms, maxmodes)

In module ``pes_init`` :
Subroutine reads in displacement vectors from input in atomic units.

    ::

        subroutine read_interd(drtheta, maxmodes)

In module ``pes_init`` :
Subroutine reads in displacement in internal coordinates (atomic units).

    ::

        subroutine read_2d(mode1, mode2, xmin2d, step2d, ssize2d)

In module ``pes_init`` :
Subroutine reads which modes that will be combined to make (2d) displacement.

    ::

        subroutine make_internal(...)

In module ``pes_calc`` :
Subroutine makes the displacement in internal coordinates.

    ::

        subroutine make_cartesian(...)

In module ``pes_calc`` :
Subroutine makes the displacement in cartesian coordinates.

    ::

        subroutine make_2d_internal(...)

In module ``pes_calc`` :
Subroutine makes displacement in internal coordinates using two the displacement vectors of normal modes (~2d)

    ::

        subroutine make_2d_cartesian(...)

In module ``pes_calc`` :
Subroutine makes displacement in cartesian coordinates using two the displacement vectors of normal modes (~2d).

    ::

         subroutine write_grid(step, ssize, xmin)

In module ``pes_write`` :
Subroutine writes the distortion grid to output file in atomic units.

    ::

        subroutine write_2d_grid(step2d, ssize2d, xmin2d)

In module ``pes_write`` :
Subroutine writes the 2d distortion grid to output files in atomic units.

    ::

        subroutine write_cartesian(xyz, maxatoms, step, aname)

In module ``pes_write`` :
Subroutine writes displaced cartesian coordinates to specified output file. Maximum number of output geometries are 999.

    ::

        subroutine write_internal(r1, r2, a, maxatoms, step, aname)

In module ``pes_write`` :
Subroutine writes displaced internal coordinates to file. Output in cartesian format.

    ::

        subroutine write_2d_internal(...)

In module ``pes_write`` :
Subroutine writes displaced 2d internal coordinates to file. Output in cartesian format.

    ::

        subroutine write_2d_cartesian(...)

In module ``pes_write`` :
Subroutine writes displaced 2d cartesian coordinates to file.
       
