- **Proportional**
	The probability of being selected is proportional to their **fitness** so $p = \frac{f_i}{\sum{f}}$

- **Rank-Based**
	We use the rank of the fitnes (so lowest is 1, highest is n), so $p = \frac{r_i}{\sum{r}}$

- **Tournament**
	There are several versions of this selection but the simplest one is
	**Deterministic**
		Population: **n**
		**k** Tournaments
		Select **p** in tournaments
		->
		$k*p$ Selected elements
		Random selection of participants, in each tournament we select the best agents
		
		
| t1    | t2    | t3    |
| ----- | ----- | ----- |
| a1    | a2    | a6    |
| a2    | a5    | a2    |
| a3    | a1    | a3    |
| a1,a2 | a5,a1 | a2,a3 |
		Our pool is then (a1,a2)(a5,a1)(a2,a3)
	**Probabilistic**
		We select the best one with the probability p
		*This can be better as we have a safe guard against an early convergence*

*We simulate the rotation of the wheel with a random number generator*
![[Pasted image 20251013113918.png]]