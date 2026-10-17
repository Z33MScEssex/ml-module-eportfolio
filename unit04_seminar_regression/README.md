# Unit 4 seminar: linear regression with scikit-learn

**Learning outcomes:** LO2, LO3, LO4 (the seminar asked us to compare solutions as a team)

**Part 1. The module's demo:** [demo_fuel_consumption_fixed.ipynb](demo_fuel_consumption_fixed.ipynb)

The demo's own saved output shows an average error of 9,933 g/km and R² of −18.82, and nobody had flagged it.
The prediction line used the CO2 column (`test_y`) as if it were engine size. The R² arguments were also the
wrong way round. Fixed, the model is about 24 g/km out with R² 0.79. I marked every fix in the notebook.

**Part 2. Tasks A and B:** [population_vs_gdp_per_capita.ipynb](population_vs_gdp_per_capita.ipynb)

- The data needed more fixing than the task said. The "GDP" file is total GDP, not per capita, so I
  calculated per capita myself. It stops at 2020. Aruba appears twice. 49 rows are groups like "World", not
  countries.
- **Task A:** Pearson r = −0.067 (p = 0.34). There is no straight-line link between how many people a country
  has and how rich each person is. On a log scale there is a weak tendency (r = −0.30) for smaller countries
  to be richer per head, driven by micro-states like Monaco and Liechtenstein.
- **Task B:** R² = 0.004. Population explains less than half a percent of the differences in wealth, and on
  unseen countries the model does worse than guessing the average.

**Data:** World Bank (2021) population and GDP series, supplied by the module.
