- **Bit vector** 
	**quantizing** the input for a chosen bit amount for example $2^{10}$ bits
	
	**Representation operations:**
		**Works on 2 individuals, combines information of both**
	-  **Crossover:**
		*This is a one split crossover, we can also have a masked crossover 
		(using a mask for example 10000001)*
		A: ==1000101001==
		B: 0101011100
		-->
		C1: ==100==1011100
		C2: 010==0101001==
	
	- **Mutation:**
		*Any bit has a chance to mutate and change*
		**If the chance is too high it becomes like a random search the same as if we have high radiation in nature.**
		A: 10==0==0101001
		-->
		B: 10==1==0101001

- **Numeric vectors**
	Instead of bits we have a vector of **real values**
	A: (7.25, 2.12, 0.07, 5.32)
	*In reality we use discrete representations more as they work better with the operations*
	
	**Representation operations:**
	- **Crossover**
		*We could do it the same way as with bits but with that the initial numbers never change and we are stuck with them*
		Instead we use ==Linear crossover==:
		**$C=a*A + (1-a)B,$    $0 < a < 1$**
	
	- **Mutation**
		*To avoid converging to the average we need to use stronger mutation*

- **Trees**
	With trees we can represent functions
	$y=3*cos(x+0.2)-x^2*7+0.5$
	Into something like:
	![[Pasted image 20251006133557.png]]
	
	**Representation operations:**
	- **Crossover**
		We choose a branch to *cut of* and then recombine
	
	- **Mutation**
		Randomly select a node or a tree and if:
		***operator** -> choose another random **operator**
		**number** -> choose another random **number***
		
		We also must take into account how many arguments the functions have

- **Permutations**
	**Travelling salesman problem**
	*We can represent the problem using a permutation of the nodes we visit*
	
	For example:
	A: (1,4,3,7,6,3,2)
	B: (6,1,5,7,4,3,2)
	
	**Representation operations:**
	- **Crossover**
		We cant just make a cut and take bit from both as then we lose the hamiltonian cycle property
		*So we do a ordered crossover:*
		
		We choose a part of the permutation lets say (1,4,3,==7,6==,3,2)
		We then start with that and fill in the rest from the other counterpart.
		(?, ?, ?, 7, 6, ==3, 2==) -> we already have 6 so 1(==1, 5==, ?, 7, 6, 3, 2)
		We are then left with 4 so we add it where we can (1, 5, 4, 7, 6, 3, 2)
	
	- **Mutation**
		We simply swap 2