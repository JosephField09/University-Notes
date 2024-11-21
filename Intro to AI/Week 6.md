Data cleaning:
- Involves identifying and addressing issues in the raw data to ensure it is suitable for training machine learning models
- Common tasks
	- Missing data handling
	- Outlier detection and treatment
	- Data scaling and normalisation
	- Handling scaling and normalisation
	- Handling categorica data


Decision Trees:
- A supervised machine learning algorithm that uses a set of rules to make decisions, similarly to how humans make decisions
- ![[Pasted image 20241031152155.png]]
- Terminal node (leaf) indicates the class assignment
- Tree partitions samples into mutually exclusive groups
- One group for each terminal node
- All paths:
	- Start at root node
	- End at a leaf
- Each path represents a decision rule:
	- joining AND of all the tests along that path
	- seperate paths that result in the same class are disjunctions
- All paths - mutually exclusive:
	- for any one case - only one path will be followed
	- false decisions on the left branch 
	- true decisions on the right branch

Algorithm:
1. Pick the best attribute/feature. The best attribute is one which best splits or separates the data.
2. Ask the relevant question
3. Follow the answer path
4. Go to step 1 until you arrive to the answer

- The goal is to have the resulting decision tree as small as possible (Occam's Razor)
	- Main decision in the algorithm is the selection of the next attribute to condition on
- We want attributes that split the examples to sets that are relatively pure in one label; this way we are closer to a leaf node




Clustering:
- The process of grouping similar objects together such that the similarity of members within the same group is maximised, and among those that belong to different groups is minimised.
- Similarity is defined using distance measure (e.g., Euclidean distance)

- Reduces the complexity of the data by deriving a reduced representation of it (summary)
- Helps for looking for new insights into the structure of the data (discovery)

