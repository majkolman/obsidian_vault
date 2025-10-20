20.10.2025

Previous lecture: [[IS/Predavanja/2/Predavanje 2|Predavanje 2]]
## Predictive modeling
### Slides
![[IS 03 Predictive modeling.pdf]]

### Types of learning
- **Classification**
	Discrete y
- **Regression**
	*function learning*
	Numerical y

#### Supervised learning
This is where both the predictors, $X_i$, and the response. $Y_i$, are observed
- Linear regression
#### Unsupervised learning
This is where only the $X_i$'s are observed.
We need to use the $X_i$'s to guess what Y would have been and build a model from there.
- Clustering
#### Semi-supervised learning
Only a small sample of labelled instances are observed but a large set of unlabeled instances. 
An initial supervised model is used to label unlabeled instances
#### Self-supervised learning
A mixture of supervised and unsupervised learning
The labels of data are obtained from the properties of the data itself (usually structure)
#### Weakly-supervised data
Noisy, limited, or imprecise sources are used to provide supervision signal for labeling large amounts of training data to do supervised learning
In reality we are doing supervised learning.
### Data mining
>How do we get our data and what types of data are there
- **Database-oriented data sets and applications**
	We get our data from a database that is relational, a warehouse or transactional.

- **Advanced data sets and advanced applications**
	• Data streams and sensor data 
	• Time-series data, temporal data, sequence data (incl. bio-sequences) 
	• Structure data, graphs, social networks and multi-linked data 
	• Object-relational databases 
	• Heterogeneous databases and legacy databases 
	• Spatial data and spatiotemporal data 
	• Multimedia database 
	• Text databases 
	• The World-Wide Web
### Association and correlation analysis
*Analyzing data and its associations.*
We can use this to do classification, clustering, ...
**Support - The probability that the conditional part of the rule happens**
**Confidence - The probability that if the conditional part happens, the consequential part also happens**

### Outlier analysis
An outlier is a data object, that doesn't comply with the general behavior of the data
- Is it noise or an exception
	*The outlier could be really important* (maybe a machine broke down or some fraud was done)
### Relational learning
![[Pasted image 20251020120103.png]]
### Criteria of success for ML
The most popular measure of success for **regression** is MSE, while the best for **classification** is CA
- Mean squared error
	$MSE = \frac{1}{n}\sum{(y_i - f'(x_i))^2}$

- Classification accuracy
	$CA = \frac{1}{n}\sum{I(y_i = y'_i)}$
	
	$I(x) = 1$, if event happened
	$I(x) = 0$, otherwise
### NFL - No free lunch Theorem
The theorem says that there isn't a algorithm that can solve any problem in the best way.
## Bias of machine learning models

### Slides
![[IS 04 Bias, variance and predictive models.pdf]]

### The problem of generalization
The problem of generalizing a model to work for more than one test data set.

One approach is to use a reserved portion of the training data we call a evaluation dataset. We use this dataset during training to detect the **sweetspot** of when to stop training the model and avoid overfitting.

**But even with this we can overfit for the evaluation dataset.**
### Bias and variance
**Bias** is how much we are missing the average by
$Bias = E[Y]-f(x)$
*Its how much our results are scattered around the true center*

**Variance** is how much our model would change if we had a different dataset.
$Var = E[(Y-E[Y])^2]$
*Its how much our results are scattered around our own center*

![[Pasted image 20251020124636.png]]

> Here we discover a Trade-off between Bias and variance

$ExpectedTestMSE = Bias^2 + Var + \sigma^2$
Where $\sigma$ is an irreducible error.

This means when the bias decreases variance will increase and the other way around.
==For some models there may be no bias variance trade-off==

![[Bayes classifier]]

