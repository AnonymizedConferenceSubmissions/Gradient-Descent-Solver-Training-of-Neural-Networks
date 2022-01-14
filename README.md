# Gradient Descent + Solver Training of Neural Networks

We present a novel hybrid algorithm for training Deep Neural Networks that combines the state-of-the-art Gradient Descent (GD) method with a Mixed Integer Linear Programming (MILP) solver, outperforming GD and variants in terms of accuracy, resource and data efficiency for regression as well as classification tasks. 
Our GD+Solver hybrid algorithm, called GDSolver, works as follows:given a DNN D as input, GDSolver invokes GD to partially train D until it gets stuck in a local minima, at which point GDSolver invokes an MILP
solver to exhaustively search a region of the loss landscape around the weight assignments of D’s final layer parameters, with the goal of tunnelling through and escaping the local minima. 
The process is repeated until desired accuracy is achieved.
We report on an extensive evaluation of GDSolver against Stochastic Gradient Descent (SGD), Mo-
mentum Based Algorithms (Adam) and common heuristics (e.g., Learning Rate Scheduling LRS) on
a suite of regression and classification tasks. 
In our experiments, we find that GDSolver not only scales well to additional data and very large model sizes, but also outperforms all other competing methods in terms of rates of convergence and data efficiency. For regression tasks, GDSolver produced models with, on average, 31.5% lower MSE in 48% less time, and for classification tasks on MNIST and CIFAR10, GDSolver was able to achieve the highest accuracy over all competing methods, using only 50% of the training data that GD baselines required.
By judiciously leveraging an MILP solver to finetune the final layer and thus tunnelling through local minima, we avoid the scalability issues associated with previous solver-based training methods,while at the same time avoiding the propensity of GD methods getting stuck in local minima.
