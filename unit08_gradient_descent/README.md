# Unit 8: gradient descent and the cost function

**Learning outcomes:** LO2, LO3

**Task.** Change the number of iterations and the learning rate, and watch the cost fall:
[gradient_descent_cost_function.ipynb](gradient_descent_cost_function.ipynb).

**What I found**
- A bigger learning rate gets there faster: 13,527 iterations at 0.001, 167 at 0.08.
- Too big and it explodes. At 0.09 the cost goes up every step until the maths breaks.
- The module's default of 0.08 sits right next to the edge. For this data the largest safe rate works out at
  0.0845. A 10% change is the difference between converging and blowing up.
- That limit comes from the data's scale, which is why features are scaled before training.
