# Unit 2 seminar: exploratory data analysis on Auto-mpg

**Learning outcomes:** LO2 (datasets and their challenges), LO3 (applying and appraising techniques)

**Task.** Follow the module's EDA tutorial, then do the same on the Auto-mpg dataset: missing values, skewness
and kurtosis, a correlation heat map, scatter plots, and turning categories into numbers.

**What I did.** The tutorial uses functions that have since been removed from NumPy and seaborn, so I applied
its methods to Auto-mpg in current syntax: [auto_mpg_eda.ipynb](auto_mpg_eda.ipynb).

**What I found**
- The missing values were hiding. `isna()` reported none, but six cars had `?` for horsepower. The clue was the
  column loading as text.
- Fuel economy falls with weight, engine size, horsepower and cylinders (all around −0.8), and those four
  overlap heavily with each other.
- Storing origin as 1, 2, 3 only worked by luck: the numbering happens to match fuel economy order.
- My own first cross-validation gave a negative R², because the file is sorted by year. Shuffling the folds
  fixed it. Row order can quietly wreck an evaluation.

**Data:** Auto MPG (Quinlan, 1993), supplied by the module as `auto-mpg.csv`.
