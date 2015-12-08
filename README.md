# Hartree-Fock-Program
Closed-shell restricted Hartree-Fock computation when given nuclear repulsion energy and one- and two-electron integrals.

Uses PSI4's python front-end to obtain data for the nuclear repulsion energy and one- and two-electron integrals.

Programs Steps
  1. Obtains nuclear repulsion energy
  2. Uses PSI4 to calculate one-electron integrals
  3. Constructs ortogonalizing matrix
  4. Constructs an intial density matrix
  5. Performs the SCF iterations
  6. Calculates the electronic energy
  7. Transforms and diagonalizes fock matrix, constrcuts the new SCF eigenvector matrix
  8. Forms new density matrix and tests for convergence.

  
## Required Dependencies:
  You must have [PSI4](http://www.psicode.org/downloads.php) (an open-source quantum chemsitry package)
##Example Case:
An example case was provided for CH4 where, the result is shown below:
***
>   *** tstart() called on Winterfell
>   *** at Wed Apr 22 12:53:55 2015

>     There are an even number of electrons - assuming singlet.
>     Specify the multiplicity with the MULTP option in the
>     input if this is incorrect


>            ---------------------------------------------------------
>                                      SCF
>               by Justin Turney, Rob Parrish, and Andy Simmonett
>                                 RHF Reference
>                           1 Threads,    256 MiB Core
>            ---------------------------------------------------------

>     ==> Geometry <==

>       Molecular point group: cs
>       Full point group: C3v

>       Geometry (in Angstrom), charge = 0, multiplicity = 1:

>          Center              X                  Y                   Z       
>       ------------   -----------------  -----------------  -----------------
>              C          0.000000000000    -0.000000741551     0.000000000000
>              H          0.000000000000     1.082999258449     0.000000000000
>              H         -0.510531791082    -0.360996809644     0.884267001033
>              H         -0.510531791082    -0.360996809644    -0.884267001033
>              H          1.021063582164    -0.360996809644     0.000000000000

>     Running in cs symmetry.

>     Nuclear repulsion =   13.522229199451864

>     Charge       = 0
>     Multiplicity = 1
>     Electrons    = 10
>     Nalpha       = 5
>     Nbeta        = 5

>     ==> Algorithm <==

>     SCF Algorithm Type is DIRECT.
>     DIIS enabled.
>     MOM disabled.
>     Fractional occupation disabled.
>     Guess Type is CORE.
>     Energy threshold   = 1.00e-06
>     Density threshold  = 1.00e-06
>     Integral threshold = 0.00e+00

>     ==> Primary Basis <==

>     Basis Set: STO-3G
>       Number of shells: 7
>       Number of basis function: 9
>       Number of Cartesian functions: 9
>       Spherical Harmonics?: true
>       Max angular momentum: 1

>     ==> Pre-Iterations <==

>      -------------------------------------------------------
>       Irrep   Nso     Nmo     Nalpha   Nbeta   Ndocc  Nsocc
>      -------------------------------------------------------
>        A'         7       7       0       0       0       0
>        A"         2       2       0       0       0       0
>      -------------------------------------------------------
>       Total       9       9       5       5       5       0
>      -------------------------------------------------------

>     Starting with a DF guess...

>    OEINTS: Wrapper to libmints.
>      by Justin Turney

>      Calculation information:
>         Number of atoms:                   5
>         Number of AO shells:               7
>         Number of SO shells:               6
>         Number of primitives:             21
>         Number of atomic orbitals:         9
>         Number of basis functions:         9

>         Number of irreps:                  2
>         Number of functions per irrep: [   7    2 ]

>         Overlap, kinetic, potential, dipole, and quadrupole integrals
>           stored in file 35.

>     ==> Integral Setup <==

>     ==> DFJK: Density-Fitted J/K Matrices <==

>       J tasked:                  Yes
>       K tasked:                  Yes
>       wK tasked:                  No
>       OpenMP threads:              1
>       Integrals threads:           1
>       Memory (MB):               183
>       Algorithm:                Core
>       Integral Cache:           NONE
>       Schwarz Cutoff:          1E-12
>       Fitting Condition:       1E-12

>      => Auxiliary Basis Set <=

>     Basis Set: CC-PVDZ-JKFIT
>       Number of shells: 60
>       Number of basis function: 162
>       Number of Cartesian functions: 181
>       Spherical Harmonics?: true
>       Max angular momentum: 3

>     Minimum eigenvalue in the overlap matrix is 2.1678619199E-01.
>     Using Symmetric Orthogonalization.
>     SCF Guess: Core (One-Electron) Hamiltonian.

>     ==> Iterations <==

>                              Total Energy        Delta E     RMS |[F,P]|

>      @DF-RHF iter   1:   -36.08518615759890   -3.60852e+01   2.09010e-01 
>      @DF-RHF iter   2:   -39.56743834835473   -3.48225e+00   7.15783e-02 DIIS
>      @DF-RHF iter   3:   -39.72575186426305   -1.58314e-01   6.26872e-03 DIIS
>      @DF-RHF iter   4:   -39.72685853473570   -1.10667e-03   6.52619e-04 DIIS
>      @DF-RHF iter   5:   -39.72686966510145   -1.11304e-05   9.70520e-05 DIIS
>      @DF-RHF iter   6:   -39.72686996291508   -2.97814e-07   1.11113e-06 DIIS
>      @DF-RHF iter   7:   -39.72686996294974   -3.46603e-11   1.43699e-08 DIIS

>     DF guess converged.

>     ==> Integral Setup <==

>     ==> DirectJK: Integral-Direct J/K Matrices <==

>       J tasked:                  Yes
>       K tasked:                  Yes
>       wK tasked:                  No
>       Integrals threads:           1
>       Schwarz Cutoff:          1E-12

>      @RHF iter   8:   -39.72686367940492    6.28354e-06   1.50240e-06 DIIS
>      @RHF iter   9:   -39.72686367948620   -8.12790e-11   3.17323e-07 DIIS

>     ==> Post-Iterations <==

>     Orbital Energies (a.u.)
>     -----------------------

>     Doubly Occupied:                                                      

>        1A'   -11.029686     2A'    -0.912100     1A"    -0.520500  
>        3A'    -0.520500     4A'    -0.520498  

>     Virtual:                                                              

>        5A'     0.719230     2A"     0.719232     6A'     0.719232  
>        7A'     0.761074  

>     Final Occupation by Irrep:
>              A'    A" 
>     DOCC [     4,    1 ]

>     Energy converged.

>     @RHF Final Energy:   -39.72686367948620

>      => Energetics <=

>       Nuclear Repulsion Energy =             13.5222291994518642
>       One-Electron Energy =                 -79.4916242532468118
>       Two-Electron Energy =                  26.2425313743087543
>       DFT Exchange-Correlation Energy =       0.0000000000000000
>       Empirical Dispersion Energy =           0.0000000000000000
>       Total Energy =                        -39.7268636794862005



>   Properties will be evaluated at   0.000000,   0.000000,   0.000000 Bohr
>     ==> Properties <==


>   Properties computed using the SCF density density matrix
>     Nuclear Dipole Moment: (a.u.)
>        X:    -0.0000      Y:     0.0000      Z:     0.0000

>     Electronic Dipole Moment: (a.u.)
>        X:    -0.0000      Y:    -0.0000      Z:     0.0000

>     Dipole Moment: (a.u.)
>        X:    -0.0000      Y:     0.0000      Z:     0.0000     Total:     0.0000

>     Dipole Moment: (Debye)
>        X:    -0.0000      Y:     0.0000      Z:     0.0000     Total:     0.0000


>     Saving occupied orbitals to File 180.

>   *** tstop() called on Winterfell at Wed Apr 22 12:53:55 2015
>   Module time:
>     user time   =       0.50 seconds =       0.01 minutes
>     system time =       0.01 seconds =       0.00 minutes
>     total time  =          0 seconds =       0.00 minutes
>   Total time:
>     user time   =       0.50 seconds =       0.01 minutes
>     system time =       0.01 seconds =       0.00 minutes
>     total time  =          0 seconds =       0.00 minutes

>   *** PSI4 exiting successfully. Buy a developer a beer!

***
