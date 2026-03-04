3.11.2025

---
## Slides:
![[IS 05 Feature engineering.pdf]]

---
## Content
### Model Selection
#### Semi-supervised feature selection
We have some labeled data and a lot of unlabeled data (this can happen if you pay someone to label the data manually)
> The question is if the unlabeled data can help
#### Stability of feature selection
**Ensemble approach**
- Split the data
- Run the data with a weaker model
- Average the results
![[Pasted image 20251103113059.png]]
### Dimensionality reduction
#### PCA - Principle components analysis
- We iteratively find the orthogonal axes of the largest variance (where the points are most spread out)
- We use that as our first dimension and repeat for the next dimensions where the next ones are orthogonal to the last
![[Pasted image 20251103113804.png]]
With this we center the data at the origin and it alligns the axis
#### Linear and local embedding
• PCA tries to find a global structure 
	• Low dimensional subspace 
	• Can lead to local inconsistencies 
	• Far away point can become nearest neighbors 
• t-SNE is an alternative dimensionality reduction algorithm. 
• t-SNE tries to preserve local structure 
	• Low dimensional neighborhood should be the same as the original neighborhood. 
	• Unlike PCA almost only used for visualization 
	• No easy way to embed new points
#### SNE - Stochastic Neighbor Embedding
- Encode high-dimensional neighborhood information as a distribution
- Random walk between data points
	- High probability of jumping to a close point

With this we find low dimensional points such that their neighborhood distribution is similar
We measure the distance between distributions using **KL divergence**
#### KL divergence - Kullback-Leiber divergence
It measures the distance between two distributions, P and Q
![[Pasted image 20251103115648.png]]
The function is not symmetric
#### Crowding Problem
In high dimensions points can have a lot of neighbors and we dont have room to fit them all

---
# Neural networks
## Slides:
![[IS 06 Neural networks.pdf]]
## Content
### Backpropagation algorithm
>TODO
### GD - Gradient descent
Its an efficient local optimization in $R^n$
![[Pasted image 20251103125547.png]]
The GD optimization moves in the direction of -$\Delta f(x)$ (okrog obrn delta)
### Error backpropagation
We will do GD on the whole network
The error gets fixed from the last to the first
![[Pasted image 20251103125903.png]]


