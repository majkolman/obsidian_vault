##### Wrapper approach
*high computational load but effective for a given learning model; attention to data overfitting*
```
Start with an empty set of features S = {} //forward selection
repeat
	add all unused features one by one to S
	train a prediction model with each set S
	evaluate each prediction model
	keep the best added feature in S
until all features are added to S
return the best set of features encountered
```
