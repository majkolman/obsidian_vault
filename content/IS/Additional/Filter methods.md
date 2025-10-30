##### Heuristic measures for attribute evaluation
• Impurity based 
• information theory based (information gain, gain ratio, distance measure, J-measure) 
• probability based: Gini index, DKM, classification error on the training set 
• MDL 
• statistics G, $N^2$ 
• mean squared and mean absolute error (MSE, MAE) 
• assume conditional independence (upon label) between the attributes 
• Context sensitive measures: 
• Relief, Contextual Merit, 
• random forests or boosting based attribute evaluation, 
• affinity graph based

##### Information gain
![[Pasted image 20251027123746.png]]

##### Relief algorithms
*Criterion: evaluate attribute according to its power of separation between near instances*
![[Pasted image 20251027124243.png]]
Here the color and size is rewarded for its distinction

*Input: set of instances <$x_i, t_i$>*
*Output: the vector W of attributes' evaluations*

```
set all weights W[A] := 0.0;
for i := 1 to m do begin
	randomly select an instance R;
	find nearest hit H and nearest miss M;
	for A:=1 to #all_attributes do
		W[A] := W[A] - diff(A,R,H)/m + diff(A,R,M)/m;
	end;

```

**To make this more robust we could take several nearest hits and misses**