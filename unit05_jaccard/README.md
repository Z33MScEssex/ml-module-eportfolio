# Unit 5: Jaccard coefficient calculations

**Learning outcomes:** LO1 (ethical issues), LO2

**Task.** Calculate the Jaccard distance between three patients from their test results.

**Notebook:** [jaccard_calculations.ipynb](jaccard_calculations.ipynb). I show the hand working first, then
check it two ways in code.

| Pair | Distance |
|---|---|
| Jack, Mary | 0.33 |
| Jack, Jim | 0.67 |
| Jim, Mary | 0.75 |

All three match the published answers.

**The interesting bit** was getting it wrong on purpose. Leaving Gender in turns Jack's clear match with Mary
(0.33 vs 0.67) into a dead tie (0.50 each). One column that has nothing to do with the illness changes who
counts as "similar". On real patient data, that's how a careless choice of columns ends up grouping people by
a protected characteristic.
