##### Regularization for feature selection
- feature selection as part of learning
- loss function is composed of two components: prediction error and number/weight of included features
	$L(X,Y,f) = \sum{I(y_i != f(x_i)) + \lambda \sum{I(A_j \in X)}}$
- in regression we get similar expressions for ridge regression and lasso
##### Ridge regression
**y = $\beta_0 + \beta_1 X1 + \beta_2 X2 + ...$**
Ordinary Least Squares (OLS) estimates $\beta$s by minimizing
![[Pasted image 20251027125847.png]]
Ridge regression minimizes a slightly different equation
![[Pasted image 20251027125914.png]]
##### Ridge regression adds a penalty on $\beta$s
![[Pasted image 20251027131919.png]]
##### Why can shrinking towards zero be a good thing?
• It turns out that the OLS estimates generally have low bias but can be highly variable. In particular when n and p are of similar size or when n < p, then the OLS estimates will be extremely variable. 
• The penalty term makes the ridge regression estimates biased but can also substantially reduce variance 
• Thus, there is a bias/variance trade-off
##### Computational advantages of ridge regression
- If the number of features p is large, then using the best subset selection approach requires searching through enormous numbers of possible models
- With ridge regression, for any given λ, we only need to fit one model and the computations turn out to be very simple 
- Ridge regression can even be used when p > n, a situation where OLS fails completely!
##### The LASSO method
Ridge regression isn't perfect
It works in a similar way compared to ridge regression but it takes the absolute value of $\beta$s
![[Pasted image 20251027132330.png]]
