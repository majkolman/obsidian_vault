In classification we can find the optimal classification for an instance $(x_0,y_0)$ by selecting the class j which maximizes the probability
$P(Y=j|X=x_0)$

This is called the Bayes optimal classifier.

![[Pasted image 20251020132457.png]]
$arg max_j P(Y=y_j|X=x_0)$
Means we get the argument j of the max value

## Bayes classifier approximations
- Two models can be viewed as directly approximating the Bayes classifier
- Naive Bayesian classifier
![[Pasted image 20251020132431.png]]
- **Nearest neighbor classifier**
	directly estimates the conditional probability using instances near to $x_0$
	- **K-Nearest neighbor classifier**
		We take the K nearest instances and using select the classifier of the majority
