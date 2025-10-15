13.10.2025

Continuing the template of a evolutionary program - Slide 20 onward
### Slides
![[IS 02 Nature inspired computation.pdf]]

![[Gaussian mutation]]

### Gray coding of binary numbers
*Keeping similarity
Similar object have a similar genome*

This is helpful for **Ordered representations** (integers, real numbers, ...)

We change how **encoding** is done
![[Pasted image 20251013112622.png]]

### Adaptive crossover
*Using crossover templates* (masks)

We change the template every 5 generations or so.
![[Pasted image 20251013113137.png]]


### Options for choosing mutation
- Single point / multisearch
- Random search
- [[Lamarckism]] (searching for locally best mutation)

### Evolutionary model
- Keep the good
- Prevent premature convergence
- Assure heterogenity of population (that all agents are different)

![[Selection]]

![[Replacement]]

### Single tournament selection
We apply only a single tournament to the population
With this we keep the best agents
Depending on the number of agents we keep the computational speed can be rather slow

### Population size
Shouldn't be too small to have a wide variety of genes and shouldn't be to big for computation speed

### Niche specialization
*This is very present in nature but we don't want this in our agents*

We want to avoid this by **punishing too similar agents** by modifying fitness
$f'_i = f_i / q(i)$
where
q(i) = 1 if sim(i) <=4
     else sim(i) / 4

#### Checkboard example
![[Pasted image 20251013122332.png]]

### Why do genetic algorithms work?
*It may seem that they wouldn't as we do random choices*

### Parameters of GA
- Encoding
	Usual settings of Parameters
	- Population size: form 20-50 to a few thousand
	- Crossover probability: high (around 0.9)
	- Mutation probability: low(below 0.1 )

### Applications
- Optimization
- Scheduling
- Bioinformatics
- Machine learning
- Planning
- Multicriteria optimization (for example cheap and enviromentaly friendly products)

### Where to use
- Many local extremes
- Just fitness, without derivations
- No specialized methods
- Multi-objective optimization
	**Pareto optimal solution** - a solution where increasing one criteria decreases the other
- Robustness
- Combined with other approaches

### Strengths and weaknesses
- **Robust, adaptable, general**
- **Requires weak knowledge** of the problem
- several alternative solutions
- hybridization and paralelization
- **faster and less memory** than exhaustive or random search
- little effort to try

- suboptimal solutions
- possibly many parameters
- may be computationally expensive

#### No-free-lunch theorem
It says that there is no method which would be suitible for all possible problems.

### Neuroevolution: evolving neural networks
*We will return to this later in our year*

## Statistical Predictive Modeling

Slides:
![[IS 03 Predictive modeling.pdf]]

*Our basic task is to predict the outcome of a new input by using example inputs to create a model*
We can also figure out which parameters are useful for predicting and which aren't

### Basic notation
Our output is usually notated as Y
The input is a matrix of vector X
The variables are call attributes, features, inputs or predictors; we name them $x_{.,j}$ - a column
One observation is $x_{i,.}$ - a row

The model is written as $Y = f(X) + \epsilon$

### Goals of learning
#### 1. Prediction
*If we can produce a good estimate for f we can make accurate predictions*
**We care more about the prediction**
#### 2. Inference
*We are interested in the type of relationship between Y and all the $X_{.,j}$*
- Which features are important
- Is the relationship linear or more complicated
- Which predictors actually affect the prediction

### How do we estimate f
*We will assume we have a set of **Training data***
-> We must then use the training data and a  statistical method to estimate f

**Statistical learning methods:**
1. ![[Parametric methods]]
2.  ![[Non-parametric methods]]
There is a trade-off between ==interpretability of the model and the prediction accuracy==
	Here overfitting also appears when using a really complicated model

