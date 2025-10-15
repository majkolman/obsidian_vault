6.10.2025

---
## Slides:
![[IS 01 Introduction.pdf]]

---

## Syllabus and obligations; overview of artificial intelligence

>We will be learning about [[Strojno učenje]] and additionally [[Reinforcement learning]] as the main categories. Along with that we will aquire practical use about the theoretical knowledge.

---
### Grading

**Both theoretical and practical. The main goals of the class are:**
![[Pasted image 20251006114234.png]]
#### Projects
2 of them, they give 50%
#### Written exam
The other 50%
#### Quizzes
5 quizzes, you need >= 50%


---
### Literature:
- An introduction to Statistical Learning: With applications in python
- Deep learning with Python
- Speech and Language Processing
- Reinforcement Learning, An Introduction
- Probabilistic Machine Learning: An introduction
- Probabilistic Machine Learning: Advanced Topics
- The elements of statistical learning

---
## Nature inspired computing
#### Slides:
![[IS 02 Nature inspired computation.pdf]]

![[Agent]]

Evolution of novelty - can we learn to predict a field that is new / novel
### Template of evolutionary program

```
generate a population of agents
do {
	compute fitness
	select candidates for reproduction
	create new agents by combining candidates #crossing of genes
	replace old agents with new ones
} while (not satisfied)
```

We can combine in many ways one of those being the crossing of genes.
We stop or are satisfied once:
- We reach our computational goal
- Prespecified goal
- The top score of agents is good enough for us
- ...

![[Pasted image 20251006123506.png]]

**With this we can only reach the local maximum and not the global maximum.**

![[Nature inspired computing]]

![[Genetic algorithms]]

![[Genome representation]]

[A demo Eaters](https://math.hws.edu/eck/jsdemo/jsGeneticAlgorithm.html)
