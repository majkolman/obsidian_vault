27.10.2025
Previous lecture: [[IS/Predavanja/3/Predavanje 3|Predavanje 3]]

---
## Data Preprocessing: feature engineering
### Slides

![[IS 05 Feature engineering.pdf]]

---
### First steps in ML

Raw Data -> Data Engineering -> Prepared Data -> Feature Engineering -> Engineered features
-> Machine Learning

---
### Data Preprocessing
#### Data cleansing
Removing or correcting records that have corrupted or invalid values from raw data, and removing records that are missing a large number of columns.
#### Instance selection and partitioning
Selecting data points from the input dataset to create training, evaluation, and test sets. This process includes techniques for repeatable random sampling, minority class oversampling, and stratified partitioning.
#### Feature tuning
Improving the quality of a feature for ML, which includes scaling and normalizing numeric values, imputing missing values, clipping outliers, and adjusting values that have skewed distributions
#### Feature transformation
Converting a numeric feature to a categorical feature, or converting categorical features to a numeric representation. Some models work only with numeric or categorical features, while others can handle mixed-type features. Even when models handle both types, they can benefit from different representations.

Color(blue, green, yellow, none)
**1-hot encoding:**

| blue | green | yellow | none |
| ---- | ----- | ------ | ---- |
| 1    | 0     | 0      | 0    |
| 0    | 1     | 0      | 0    |
| 0    | 0     | 1      | 0    |
| 0    | 0     | 0      | 1    |
#### Feature extraction
Reducing the number of features by creating lower-dimension, more powerful data representations using techniques such as PCA, embedding extraction and hashing.
#### Feature selection
Selecting a subset of the input features for training the model, and ignoring the irrelevant or redundant ones, using filter or wrapper methods. Feature selection can also involve simply dropping features if the features are missing a large number of value
#### Feature construction
Creating new features by using different operators, such as logical, arithmetical, trigonometrical, etc. Features can also be constructed by using domain knowledge, e.g., business logic from the domain of the ML use case.

 ---
### Feature subset selection
Choose a small subset of the relevant features from the original features by removing irrelevant, redundant and/or noisy features

*The aim: better learning performance, i.e. higher learning accuracy, lower computational cost, or better model interpretability*

**Huge number of features**
- **Text classification, around 100,000** words in a dictionary
- **Bioinformatics, around 10,000** measurements of gene expression levels
- **Computer vision, around 1,000,000** pixels

==Selection -> ranking -> evaluation==
#### **Evaluation of attributes**:
The success of the evaluation procedure depends on the role it plays in learning:
- feature subset selection
- building of the tree-based models
- constructive induction
- discretization
- ...

#### **Feature evaluation**:
*In order to select attributes, we have to evaluate (rank) them*
The success of feature evaluation is measured through the success of downstream tasks, i.e. learning
**Example: feature evaluation in decision tree building**
- in each interior node of the tree an attribute is selected which determines split of the instances
- the attributes are evaluated to ensure useful split
![[Pasted image 20251027123032.png]]
#### Types of feature selection
- ![[Filter methods]]
- ![[Wrapper methods]]
- ![[Embedded methods]]
---
### Model evaluation
**Metrics**:
- Evaluation metrics
- Regression: MSE, MAE
- Classification: accuracy, sensitivity, specificity, AUC, precision, recall
- Comparing classifiers:
	- Mean and confidence intervals
	- Cost-benefit analysis and ROC Curves
	- Rank-based tests
	- Bayesian tests

#### Classifier evaluation metrics
![[Pasted image 20251027133909.png]]

**Classification accuracy, Error rate**:
![[Pasted image 20251027134138.png]]

**Sensitivity and specificity**:
![[Pasted image 20251027134223.png]] 

**Precision, recall and F-measures**:
![[Pasted image 20251027134303.png]]
#### Multiclass evaluation
- no problems for classification accuracy 
- most other measures assume binary class, e.g., precision, recall, F1 
- multiclass extensions simulate binary case 
- macro average: 
	- compute several one-versus-all scores and average 
	- assumes balanced class distribution, gives equal weight to each class 
- micro average 
	- computes TP, FP, TN, FN for each class separately and then computes the measure 
	- assumes all instances are of the same importance; in case of imbalanced classes this might be problematic
#### ROC curve
![[Pasted image 20251027135549.png]]

---
### Model Selection
**Accuracy**:
	- Classification
	- Regression
**Speed**:
	- time to construct the model
	- time to use the model
**Robustness**
Scalability
Interprability