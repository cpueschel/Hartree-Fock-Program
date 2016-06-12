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
  You must have [PSI4](http://www.psicode.org/downloads.php) (an open-source quantum chemistry package)
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
The resulting iterations that are preformed for CH4 are;

> 1. `dE = -750801.898817 Energy: 2503.83715085`
> 1. `dE = -2512.80776199 Energy: -8.97061113479`
> 1. `dE = -42.4011296156 Energy: -51.3717407504`
> 1. `dE = 14.2161344845 Energy: -37.1556062659`
> 1. `dE = 2.80444327045 Energy: -34.3511629955`
> 1. `dE = -5.42481013625 Energy: -39.7759731317`
> 1. `dE = -1.13160054872 Energy: -40.9075736804`
> 1. `dE = 0.978093560493 Energy: -39.9294801199`
> 1. `dE = 0.140052117369 Energy: -39.7894280026`
> 1. `dE = -0.144211248161 Energy: -39.9336392507`
> 1. `dE = -0.0224585216738 Energy: -39.9560977724`
> 1. `dE = 0.0223416929177 Energy: -39.9337560795`
> 1. `dE = 0.00285421264459 Energy: -39.9309018668`
> 1. `dE = -0.00285875740182 Energy: -39.9337606242`
> 1. `dE = -0.000498737300397 Energy: -39.9342593615`
> 1. `dE = 0.00049846068562 Energy: -39.9337609009`
> 1. `dE = 4.76044741831e-05 Energy: -39.9337132964`
> 1. `dE = -4.76271408516e-05 Energy: -39.9337609235`
> 1. `dE = -1.36289804615e-05 Energy: -39.9337745525`
> 1. `dE = 1.36268460622e-05 Energy: -39.9337609257`
> 1. `dE = -6.81766181287e-08 Energy: -39.9337609938`
> 1. `dE = 6.7961309469e-08 Energy: -39.9337609259`
> 1. `dE = -6.08808804259e-07 Energy: -39.9337615347`
> 1. `dE = 6.08786145051e-07 Energy: -39.9337609259`
> 1. `dE = -1.05954981677e-07 Energy: -39.9337610318`
> 1. `dE = 1.05952544516e-07 Energy: -39.9337609259`
> 1. `dE = -4.60915501321e-08 Energy: -39.933760972`
> 1. `dE = 4.60913227585e-08 Energy: -39.9337609259`
> 1. `dE = -1.30536292886e-08 Energy: -39.9337609389`
> 1. `dE = 1.3053586656e-08 Energy: -39.9337609259`
> 1. `dE = -4.49462334018e-09 Energy: -39.9337609304`
> 1. `dE = 4.49458070761e-09 Energy: -39.9337609259`
> 1. `dE = -1.43231915217e-09 Energy: -39.9337609273`
> 1. `dE = 1.43231915217e-09 Energy: -39.9337609259`
> 1. `dE = -4.76347850054e-10 Energy: -39.9337609264`

>###RHF Final Energy:   -39.72686367948620  @ 9 iterations
