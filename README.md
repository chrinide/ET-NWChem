# ET-NWChem
Computing electron transfer matrix element (H_ab) using Generalized Mulliken−Hush (GMH) NWChem.

Herein, tddft module has been being modified to compute electron transfer matrix element using GMH method based on following formula.

```
                (Ej - Ei) * muij
GMH = ----------------------------------
         ------------------------------
       \/ (muii - mujj)**2 + 4*(muij**2)
```

Original source code of tddft module (all tddft_\*.F) of NWChem was written by So Hirata.

NWChem 6.8 is released as open-source under the ECL 2.0 license.
