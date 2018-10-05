# Generalized Mulliken-Hush Analysis of Electron Transfer Calculation in NWChem

Computing electron transfer matrix element (H_ab) or electron transfer integral using a Generalized Mulliken−Hush (GMH) in NWChem program.

Herein, tddft module has been being modified to compute electron transfer matrix element using GMH method based on following formula.

```
                (Ej - Ei) * muij
GMH = ------------------------------------
         _______________________________
       \/ (muii - mujj)**2 + 4*(muij**2)
```

where Ei and Ej are energy for each pair of ground state and excited state, muii, mujj, and muij are transition dipole moment for different species.

### Useful link
 - [Doxygen for NWChem documenting](http://www.doxygen.nl/)
 - [Generalization of the Mulliken-Hush treatment for the calculation of electron transfer matrix elements Author links open overlay panel by Robert J.Cave et al.](https://www.sciencedirect.com/science/article/abs/pii/0009261495013105)
 - [Computational Methods For Electronic Couplings by Chao-Ping Hsu, Academia Sinica](http://www.q-chem.com/tutorial/Cherri_Hsu_Electronic_Coupling.pdf)

### Disclaimers

A GMH approach I implemented and modified is based on original source code of Time-Dependent Density Functional Theory (all tddft_\*.F) of NWChem software was written by Prof. So Hirata. I am not responsible for any damage caused through use of all products here.

The latest version of writing this document is NWChem 6.8.1, which is released as open-source under the ECL 2.0 license.

# Recompile NWChem without full compilation

I strongly suggest you to compile NWChem wihtout using my experimentally modified source code of GMH first, if original NWChem is compile successfully (testing results are acceptable), then you can go further with my work.

Step 1. Go to folder where source code is modified.

```
cd $NWCHEM_TOP/src/nwdft/lr_tddft
```

Step 2. Export env var as first time NWChem was compile.

```
export USE_64TO32=y
cd $NWCHEM_TOP/src/nwdft/lr_tddft
make -j4
cd $NWCHEM_TOP/src
make link -j4
echo "Done"
```

ref: [recompile-nwchem.sh](recompile-nwchem.sh)

# Acknowledgements
I thank Prof. Chao-Ping Hsu, Academia Sinica, Taipei, Taiwan for sugggesting GMH approach. I also thank Edoardo Apra, NWChem developer at PNNL, USA for useful comments on NWChem code modification.


