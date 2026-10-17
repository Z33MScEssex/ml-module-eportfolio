# Unit 7: perceptron activities

**Learning outcomes:** LO2, LO3

| Notebook | What I did | Headline |
|---|---|---|
| [ex1_simple_perceptron.ipynb](ex1_simple_perceptron.ipynb) | a grid of inputs and weights, plotted the decision line | A perceptron is a weighted sum and a hard cut-off, and it can only ever draw one straight line. |
| [ex2_perceptron_AND_operator.ipynb](ex2_perceptron_AND_operator.ipynb) | trained AND, OR, XOR and NAND, changed the learning rate | XOR can't be learned by one perceptron. NAND only learns once a bias is added. The module's update rule only ever increases weights. At learning rate 1.0 even AND never learns. |
| [ex3_multi_layer_perceptron.ipynb](ex3_multi_layer_perceptron.ipynb) | fixed two problems, varied learning rate, hidden neurons and random starts | With 2 hidden neurons only 4 of 20 random starts solve XOR, and training 10 times longer doesn't help: they're stuck. With 3 hidden neurons all 20 solve. |

**Fixes I made to the supplied code:** a misnamed variable (`weights1` vs `weights_1`) that only worked for
the author because of something left in memory, and an unseeded random start. Both are marked in the notebook.
