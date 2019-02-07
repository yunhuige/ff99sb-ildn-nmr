# ff99sb-ildn-nmr
AMBER ff99SB-ILDN-NMR in amber format 
A hybrid set of force field files for AMBER, that combines the side chain mods of ff99sbildn (Lindorff-Larsen 2010) and ff99SB-nmr1 (Li and Bruschweiler 2010).

Prepared by: Vincent Voelz

The entire ff99sb-nmr1 modification is just these parameters:
 ```vvs-MacBook-Pro:amberff99sb-ildn-nmr vv$ cat ff99SB-nmr1/frcmod.ff99SBnmr 
From D.W. Li and R. Bruschweiler, Angew. Chem. Int. Eng. Ed. 49:6778, 2010
MASS

BOND

ANGL

DIHEDRAL
C -N -CT-C    1    0.41          0.0            -4.         four amplitudes and
C -N -CT-C    1    0.52          0.0            -3.         phases for phi
C -N -CT-C    1    0.11          0.0            -2.
C -N -CT-C    1    0.00          0.0             1.
N -CT-C -N    1    0.1the3          0.0            -4.         four amplitudes and
N -CT-C -N    1    0.75        180.0            -3.         phases for psi
N -CT-C -N    1    1.21        180.0            -2.
N -CT-C -N    1    0.64        180.0             1.
CT-CT-N -C    1    0.32          0.0            -4.         four amplitudes and
CT-CT-N -C    1    0.13          0.0            -3.         phases for phi'
CT-CT-N -C    1    1.63          0.0            -2.         
CT-CT-N -C    1    2.43          0.0             1.
CT-CT-C -N    1    0.25          0.0            -4.         four amplitudes and
CT-CT-C -N    1    0.70          0.0            -3.         phases for psi'
CT-CT-C -N    1    0.31          0.0            -2.         
CT-CT-C -N    1    0.41        180.0             1.

NONB

````

*All* you need to do is to find the corresponding lines in the ff99SB-ildn frcmod file and replace them with them ff99sb-nmr1 parameters:

```vvs-MacBook-Pro:amberff99sb-ildn-nmr vv$ cat ff99SB-ildn/dat/leap/
cmd/  lib/  parm/ 
vvs-MacBook-Pro:amberff99sb-ildn-nmr vv$ cat ff99SB-ildn/dat/leap/parm/frcmod.ff99SBildn | grep "C -N -CT-C"
C -N -CT-C    1    0.00          0.0            -4.         four amplitudes and
C -N -CT-C    1    0.42          0.0            -3.         phases for phi
C -N -CT-C    1    0.27          0.0            -2.
C -N -CT-C    1    0.00          0.0             1.
vvs-MacBook-Pro:amberff99sb-ildn-nmr vv$ cat ff99SB-ildn/dat/leap/parm/frcmod.ff99SBildn | grep "N -CT-C -N"
N -CT-C -N    1    0.00          0.0            -4.         four amplitudes and
N -CT-C -N    1    0.55        180.0            -3.         phases for psi
N -CT-C -N    1    1.58        180.0            -2.
N -CT-C -N    1    0.45        180.0             1.
vvs-MacBook-Pro:amberff99sb-ildn-nmr vv$ cat ff99SB-ildn/dat/leap/parm/frcmod.ff99SBildn | grep "CT-CT-N -C"
CT-CT-N -C    1    0.00          0.0            -4.         four amplitudes and
CT-CT-N -C    1    0.40          0.0            -3.         phases for phi'
CT-CT-N -C    1    2.00          0.0            -2.         
CT-CT-N -C    1    2.00          0.0             1.
vvs-MacBook-Pro:amberff99sb-ildn-nmr vv$ cat ff99SB-ildn/dat/leap/parm/frcmod.ff99SBildn | grep "CT-CT-C -N"
CT-CT-C -N    1    0.00          0.0            -4.         four amplitudes and
CT-CT-C -N    1    0.40          0.0            -3.         phases for psi'
CT-CT-C -N    1    0.20          0.0            -2.         
CT-CT-C -N    1    0.20          0.0             1.```
(edited)
Thats it.   Then you will have ff99sb-ildn-nmr1.

```

## `ff99SB-ildn-nmr1.tar`

Yay! I did it! I made the changes to the files and filenames and packaged up the following tar file:

`ff99SB-ildn-nmr1.tar`

Enjoy! --Vince


## LINKS

* http://ambermd.org/AmberModels.php
* https://research.cbc.osu.edu/bruschweiler.1/protein-force-field/


## REFERNECES

K. Lindorff-Larsen, S. Piana, K. Palmo, P. Maragakis, J.L. Klepeis, R.O. Dror and D.E. Shaw. Improved side-chain torsion potentials for the Amber ff99SB protein force field. Proteins, 78:1950, 2010. 

D.-W. Li and R. Bruschweiler. NMR-based protein potentials. Angew. Chem. Int. Ed. 49:6778, 2010.
