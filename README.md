# ET-NWChem
Computing electron transfer matrix element (H_ab) using Generalized Mulliken−Hush (GMH) NWChem.

Herein, tddft module has been being modified to compute electron transfer matrix element using GMH method based on following formula.

```
                (Ej - Ei) * muij
GMH = ------------------------------------
         _______________________________
       \/ (muii - mujj)**2 + 4*(muij**2)
```

Original source code of tddft module (all tddft_\*.F) of NWChem was written by So Hirata.

NWChem 6.8 is released as open-source under the ECL 2.0 license.

# Recompile NWChem without full compilation

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
