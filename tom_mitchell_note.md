
## Chapter 3
##### 3.3 Appropriate problems for decision tree learning
* Instances are represented by attribute-value pair
* The target function has discrete output value
* Disjunctive descriptions may be required
* The training data may contain error
* The training data may contain missing attribute values

##### 3.4  The basic decision tree learning algorithm
1. which attribute is the best classifier?  
1) Use entropy to measure information gain.  
2) Entropy(S) = Sum(-pi*log2Pi)
3) The entropy can be as large as log2C

##### 3.5 Hypothesis space search in decision tree
* Decision tree (ID3) searches a complete hypothesis space.
* ID3 maintains only a single current hypothesis.
* ID3 is susceptible to the risks of converging to local optimal solutions.
* ID3 uses all training examples at each step in the search to make statistically based decisions, thus can tolerate errors in training examples.

##### 3.6 Inductive bias in decision tree
* selects in favor of shorter trees over longer ones.
* select trees that place the attributes with highest importation gain closest to the root.

##### 3.7 Issues in decision tree learning
###### 1. Avoid overfitting
1.1 Why overfitting occurs     
a) One source of overfitting is derived from the error/noise in the training sample.  
b) Overfitting is also possible when the training data is error-free, especially when the training sample is small. Some attributes may partition the examples very well despite being unrelated to the actual target function.

1.2 How to avoid overfitting
* approach-1: reduced error pruning. This approach use training data to train the model; use the validation data to prune the tree; and use testing data to provide an un-biased estimation of accuracy.  
* approach-2:rule post-pruning

###### 2. Incorporating continuous-valued attributes
pick a threshold, c, that produces the greatest information gain by split the continuous values into two groups.

###### 3. Alternative measures for selecting attributes  
There is a natural bias in the information gain measure that favors attributes with many values.
Solution: a) Use GainRatio(S,A); b) distance-based measure.

###### 4. Handling training examples with missing attribute values  
* assign the value that is most common among training examples at node n.  
* assign a probability to each of the possible values.

###### 5 Handling attributes with differing costs
* divide Gain by the cost of the attribute.
