# Selbst-Testfragen

Nachfolgende Fragen eigenen sich zur Prüfungsvorbereitung mittels **Active Recall** und sind sinnvoll als Ergänzung zu Karteikarten.

Einarbeiten

- Explain algorithm xy → Alle Algorithmen rausarbeiten
- Give applications for algorithm xy...
- Compare algorithm xy with uw....
- What are the advantages of xy over uw...

## Big Data

- What are the characteristics of big data? (*)
- Explain three characteristics of big data? (*)
- What is the difference between varacity and variety? (Eigene)

## ML vs. Statistic vs. Econometrics

## Structure of data / CRISPDM / Taxonomy

- What are characteristics of unstructured data? Explain them. (*)
- What is unsupervised learning? (*)

## Multiple Linear Regression

- Explain what regularization is and why it is useful (Github Interview Questions)
- Explain the ridge regression (*)
- Explain the difference between LASSO and ridge regression? (*) (→ Für Antwort siehe Github Interview Questions)
- In practice, explain what is the main difference between ridge regression and LASSO. (*) (→ Für Atnworth siehe Github Interview questions)
- Explain what is the difference between LSSO and linear regression? (*)
- What are the main applications of LASSO? (*)
- Compare LASSO and the stability selection technique. (*)
- How do we apply the kernel trick to ridge regression? (ML)
- Why does it make sense to penalize the norm of the weight vector? (ML)
- Which norms can we use and what are the different effects? (ML)

## Logistic Regression

- Explain what logistic regression is.
- What are the advantages of logistic regression over SVMs?
- What is the effect on the coefficients of logistic regression if two predictors are highly correlated? (Interview questions GitHub?)

## Classification Evaluation

- What is an imbalanced dataset in classification? (*)
- How do you deal with imbalanced data in classification? (Github Interview Questions)

![self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled.png](self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled.png)

- Why is it a bad idea to evaluate your algorithm on the training set? (ML)
- What is the advantage/disadvantage of k-fold CV vs. Hold-out method?
- Give an example for True Positive Rates etc.? (E)
- Explain what precision and recall are. How do they relate to the ROC-Curve?  (Github Interview Questions)
- Is it better to have many false positives, or too many false negatives? (Github Interview Questions)

## Cross-Validation

- How should we tune parameters for machine learning models? (*)
- Explain purged $k$-fold cross-validaton (*)
- How should we divide data into training and testing for a time series dataset? (*)

## Shrinkage Methods

## Dimensionality Reduction

- What are the advantages of sparse PCA over PCA? (*)
- What does dimensionality reduction mean? (ML)
- What is PCA? (ML)
- What are three things, that PCA does? (ML)
- What are the roles of the Eigenvectors and Eigenvalues in PCA? (ML)
- Can you describe applications of PCA? (ML)

## Decision Trees

![self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%201.png](self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%201.png)

![self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%202.png](self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%202.png)

![self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%203.png](self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%203.png)

![self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%204.png](self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%204.png)

- Mention three characteristics of impurity measures? (*)
- What are the advantages of decision trees over random forests? (*)
- How can continous attributes be handled in Decision Trees? (*)
- What are useful splitting criterions? (ML)
- How can we influence the model complexity of the tree? (ML)

![self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%205.png](self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%205.png)

- 

![self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%206.png](self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%206.png)

## Bagging, Boosting and RF

- What are tuning parameters for Boosting? (*)
- How does Boosting work for regression? (*)
- What is the main advantage and disadavantage of a random forest over a decision tree? (*)
- Describe how Gradient Boosting works (Interview Questions Github)

## $k$-means Clustering

- Explain the k-means clustering algorithm (*)
- How is the clustering problem defined? (ML)
- Why is clustering called unsupervised? (ML)
- How do clustering Methods work? Waht is the rule of the cluster-2-cluster distance and which distances can we use?  (ML)
- How does the k-mean algorithm work? (ML)
- What are the 2 main steps of k-means? (ML)
- Why does k-means converge? What is it minimizing (ML)
- Does k-means find a global minimum of the objective? (ML)
- Name similarity measures. Name an advantage and disadvantage for each of them. (Eigene)
- Compare similarity measures for low and high-dimensional spaces. (Eigene)
- In unsupervised learning, if a ground truth about a dataset is unknown, how acan we determine the most useful number of clusters to be? (Github Interview questions)
- 

![self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%207.png](self%20test%20questions%20255cf1aed9eb4c40bb951332b4c9413a/Untitled%207.png)

## SVMs

- Required scaling for SVMs? (*)
- Advantages of SVMs over logistic Regression (*)
- Recommendations to improve results of a SVM. (*)
- Why is it good to use a maximum margin objective for classification? (ML)
- How can we define the margins as optimization problem? (ML)
- What are slack variables and how can they be used to get a "soft" margin? (ML)
- How is hinge loss defined? (ML)
- Waht is the relation between the slack variables and the hinge loss? (ML)
- What are the advantages and disadvantages in comparsion to logistic regression? (ML)
- What is the difference between gradients and subgradidents? (ML)
- What is the definition of a kernel and its relation to an underlying feature space? (ML)
- Why are kernels more powerful than traditional feature-based methods? (ML)
- What do we mean by the kernel trick? (ML)

## Neural Net

- How does logistic regression relate to neural networks? (ML)
- What kind of functions can single layer NN learn? (ML)
- Why do we need non-linear activation functions? (ML)
- What activation functions can we use and what are advantages / disadvantages of those? (ML)
- What output layer and loss function use given the task (regression / classification)? (ML)
- Why not use a sigmoid activation function? (ML)
- Why neural networks can overfit and what are the options to prevent it? (ML)
- Early stopping, cross-validation and network pruning are techniques to prevent overfitting of Neural Nets. Explain them. (E)

## RNN

- Explain Recurrent Neural Networks (RNN) (*)

## LSTM

- LSTMs are suitable for which type of analysis? (*)
- How can we use LSTMs for time series dataset? (*)
- Explain LSTMs. (*)

## Methods in NLP

## RNNs / GRUs / Bidirectional LSTMs

- Explain Differences between RNNs and GRUs (E)

### Misc

- Techniques that can be used for default predicition. (*)