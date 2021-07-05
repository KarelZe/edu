# Selbst-Testfragen

Nachfolgende Fragen eigenen sich zur Prüfungsvorbereitung mittels **Active Recall** gedacht und eine Ergänzung zu [Karteikarten](00_anki.md).

## TODOs

- Explain algorithm xy → Alle Algorithmen herausarbeiten
- Give applications for algorithm xy...
- Compare algorithm xy with uw....
- What are the advantages of xy over uw...


## Big Data

- What are the characteristics of big data? (*)
- Explain three characteristics of big data? (*)
- What is the difference between veracity and variety? (E)

## ML vs. Statistics vs. Econometrics
- Compare ML to Statistics. What are the most significant differences? (E)
- Compare ML to Econometrics. In which way do both differ? (E)


## Structure of data / CRISPDM / Taxonomy

- What are characteristics of unstructured data? Explain them. (*)
- What is unsupervised learning? (*)
- Give two examples for unsupervised learning techniques. (E)
- Give examples for structured / unstructured data. (E)
- Give a brief explanation of categorical, binary, ordinal and numeric variables. (E)
- Explain common techniques for data gathering. (E)
- Why is it desirable to work on normalized data? (E)
- Explain common techniques to analyse the relationship between variables. (E)
- How can missing data be replaced? Explain. (E)
- Explain 3 patterns in which missing data can occur. (E)


## Multiple Linear Regression

- What is the purpose $\beta$ in a *Multiple Linear Regression Model*? (E)
- Explain how an optimal estimate for $\beta$ can be derived.
- Compare Multiple Linear Regression to LASSO. Why is it desirable to penalize a Linear Regression model? (E)
- Compare Multiple Linear Regression to Ridge Regression. Why is it desirable to penalize a Linear Regression model? (E)
- Name two measure to test the goodness of fit of a Linear Regression model. (-&rightarrow; Total Sum of Squares / R^2) (E)
- Explain scenarios, where Ridge Regression would be preferred over LASSO. (E)
- Write the definitions R^2, Adj. R^2, MAE, RMSE. (E)
- Compare R^2, Adj. R^2 to MAE, RMSE. Name advantages and drawbacks. (E) 
- Compare R^2, Adj. R^2 to MAE, RMSE. Which of these is normed. (E)
- Explain the 3 steps in fitting a regression model. (E)
- What is the advantage of using R^2 over SST? (E)
- In which way does adjusted R^2 improve the standard R^2? (E)
- Explain the purpose of conducting an ANOVA test? (E)
- Is the F-static normalized? What values can the F static take? (E)
- How can the significance of a model be tested? (E)
- Why does the improvement when adding new explanatory variables follow a chi-squared distribution with one degree of freedom? (E)
- What is problematic about Multicollinearity? (E)
- How can Multicollinearity be resolved? (E)
- How does correlations and multicollinearity relate? (E)
- Give the definition of the Variance Inflation Factor. (E)
- Explain how the Variance Inflation Factor can be calculated. (E)
- Name implications when residuals of a general linear regression model are not normally distributed. (E)
- Why do errors of a linear regression model have to be normally distributed? (E)
- Why does variance of regression errors in a linear regression model has to be constant? (E)
- Explain the concept of heteroscedasticity for regression errors. (E)
- Define the coefficient of partial determination. (E)
- How do the coefficient of partial determination and F-test relate? (E)
- Why is it not desirable to use Linear Regression for default prediction? (E)


## Logistic Regression
- In which day does logistic regression and linear regression differ?
- Explain what logistic regression is. (E)
- How is the maximum likelihood estimated in a logistic regression setting? (E)
- What are the advantages of logistic regression over SVMs? (E)
- What is the effect on the coefficients of logistic regression if two predictors are highly correlated? (Interview questions GitHub?)
- Calculate the probabilities of ... using logistic regression model. (E)
- How can logistic regression enhanced to a multiple logistic regression case? (E)

## Classification Evaluation
- What is an imbalanced dataset in classification? (*)
- How do you deal with imbalanced data in classification? (GitHub Interview Questions)
-  Why is it a bad idea to evaluate your algorithm on the training set? (ML)
- What is the advantage/disadvantage of k-fold CV vs. Hold-out method?
- Give an example for True Positive Rates etc.? (E)
- Explain what precision and recall are. How do they relate to the ROC-Curve?  (GitHub Interview Questions)
- Is it better to have many false positives, or too many false negatives? (GitHub Interview Questions)
- Draw a ROC Curve for given metrics. (E)
- Interpret a ROC Curve. (E)
- How is the AUC be calculated? (E)
- Accuracy should not be the only criteria when comparing classifiers. Name 4 others. (E)
- Is Kappa static sensitive to imbalanced data? (E)
- How can Kappa static be interpreted? (E)
- How is Kapp static defined? (E)
- In which way does the F-measure improve over simpler measure like precision? (E)
- How is the F measure defined? (E)
- What values can a F measure take? (E)
- Define precision / recall / sensitivity / False Positive Rate. (E)
- Give an intuition for precision / recall / sensitivity... (E)
- Derive a confusion matrix from given TP, FP... (E)
- When classifying why is it not just sufficient to look at the accuracy? (E)
- Draw a confusion matrix. Include the metrics, that are inside the cells. (E)
- How can a standard 2x2 confusion matrix be enhanced for a multi-classification case? (E)
- Are ROC curves / is AUC sensitive to imbalanced data? If yes, how can it be resolved? (E)



## Cross-Validation

- What is the motivation to use resampling methods such as cross validation? (E)
- What are drawbacks of resampling approaches? (E)
- How should we tune parameters for machine learning models? (*)
- Explain purged $k$-fold cross-validation (*)
- How should we divide data into training and testing for a time series dataset? (*)
- What are bias and variance, and what are their relation to modelling data? (GitHub Interview questions)
- Name at least techniques for cross validation (E)
- Explain $k$-fold cross-validation (E)
- Explain the validation set approach? (E)
- Explain the Leave-One-Out Cross-Validation. (E)
- What is the motivation to perform purged $k$-Fold Cross Validation. (E)
- Why is bootstrapping used? Why is bootstrapping desirable? (E)
- Explain what bootstrap is. (E)


## Shrinkage Methods
-  Explain how forward stepwise selection works in 3 steps. (E)
-  Explain how backward stepwise selection works in 3 steps. (E)
-  Compare the subset selection methods forward and backward stepwise selection. (E)
-  When is it desirable to use backward stepwise selection and when is it desirable to use forward stepwise selection? (E)
-  What is an alternative to subset selection methods? (E)
-  What are the reasons why shrinkage methods such as LASSO are preferred over subset selection methods such as forward stepwise selection?
- Compare the stepwise inclusion regression method to stepwise exclusion regression method and standard stepwise regression method. (E)
- Explain how the stepwise inclusion regression method / ... /... works. (E)
- In which way do stepwise inclusion method and stepwise exclusion method differ? (E)
- Explain what regularization is and why it is useful (GitHub Interview Questions)
- Explain the ridge regression (*)
- Explain the difference between LASSO and ridge regression? (*) (→ Für Antwort siehe GitHub Interview Questions)
- In practice, explain what is the main difference between ridge regression and LASSO. (*) (→ Für Antwort siehe GitHub Interview questions)
- Explain what is the difference between LSSO and linear regression? (*)
- What are the main applications of LASSO? (*)
- Compare LASSO and the stability selection technique. (*)
- How do we apply the kernel trick to ridge regression? (ML)
- Why does it make sense to penalize the norm of the weight vector? (ML)
- Which norms can we use and what are the different effects? (ML)
- Give the formula for ridge regression and explain its components. (E)
- Give the formula for LASSO and explain its components. (E)
- Name one major advantage of LASSO over ridge regression. (E) &rightarrow; Lasso yields sparse models, that is, models that only involve a subset of other variables.
- How should $\lambda$ be selected for ridge regression / LASSO? (E)
- Explain how selecting tuning parameters works for ridge regression. (E)

## Dimensionality Reduction

- What are the advantages of sparse PCA over PCA? (*)
- What does dimensionality reduction mean? (ML)
- What is PCA? (ML)
- What are three things, that PCA does? (ML)
- What are the roles of the Eigenvectors and Eigenvalues in PCA? (ML)
- Can you describe applications of PCA? (ML)
- Give the definition for PCA (E)
- Explain the sparse PCA. (E)
- Explain the nonlinear PCA. (E)
- Explain the kernel PCA. (E)
- Explain the major difference of sparse PCA over ordinary PCA (E)
- Explain the major difference of sparse PCA over ordinary PCA (E)



## Decision Trees

- Mention three characteristics of impurity measures? (*)
- What are advantages of decision trees over random forests? (*)
- How can continuous attributes be handled in Decision Trees? (*)
- What are useful splitting criterions? (ML)
- How can we influence the model complexity of the tree? (ML)
- Name 3 impurity measures. (E)
- Compare the Gini-Coefficient to Entropy and the resubstitution error. (E)
- Name 3 conditions an impurity measure has to fulfil. (E)
- When should the Gini-Coefficient be used? When is it desirable to use the Entropy? (E)
- Explain how categorical features can be split? (E)
- Explain how numerical features can be split? (E)
- What is the motivation to prune a decision tree? (E)
- Explain how growing a decision tree works? (E)
- How can decision trees be applied to a regression case? (E)
- Name several advantages / disadvantages of decision trees (E)

## Bagging, Boosting and RF

- What are tuning parameters for Boosting? (*)
- How does Boosting work for regression? (*)
- How does Boosting work for classification? (E)
- How does Bagging differ from Boosting? Explain the differences? (E)
- How does Bagging work for regression? (E)
- How does Bagging work for classification? (E)
- What is the main advantage and disadvantage of a random forest over a decision tree? (*)
- Describe how Gradient Boosting works. (Interview Questions GitHub)
- Compare Boosting trees to Random Forests. What are the differences? (E)
- Explain how a Random Forest improves ordinary decision trees. (E)
- Explain what a Random Forest is? (E)
- When can it be advantageous to use Random Forests over Decision Trees? (E)
- What are tuning parameters for Decision Trees? (E)
- What are tuning parameters for Random Forests? (E) &rightarrow; No. Trees + No. of predictors used to build each tree.

## Vorlesung 8

- Compare supervised learning to unsupervised learning. How do they differ? (E)
- What are advantages / disadvantages of unsupervised learning techniques?

- What is PCA commonly used for? (E)
- How can the proportion of variance explained by $m$ variables be calculated? (E)
- Calculate the PCA for the first 2 components? (E)
- Sketch the algorithm for calculating the first two PCA components. (E)

## $k$-means Clustering

- Explain the k-means clustering algorithm (*)
- How is the clustering problem defined? (ML)
- Why is clustering called unsupervised? (ML)
- How do clustering Methods work? What is the rule of the cluster-2-cluster distance and which distances can we use?  (ML)
- How does the k-mean algorithm work? (ML)
- What are the 2 main steps of k-means? (ML)
- Why does k-means converge? What is it minimizing (ML)
- Does k-means find a global minimum of the objective? (ML)
- Name similarity measures. Name an advantage and disadvantage for each of them. (Eigene)
- Compare similarity measures for low and high-dimensional spaces. (Eigene)
- In unsupervised learning, if a ground truth about a dataset is unknown, how can we determine the most useful number of clusters to be? (GitHub Interview questions)
- What is the main idea of clustering(E)
- When is a clustering optimal?

## Vorlesung 9

## SVMs

- Required scaling for SVMs? (*)
- Advantages of SVMs over logistic Regression (*)
- Recommendations to improve results of a SVM. (*)
- Why is it good to use a maximum margin objective for classification? (ML)
- How can we define the margins as optimization problem? (ML)
- What are slack variables and how can they be used to get a "soft" margin? (ML)
- How is hinge loss defined? (ML)
- What is the relation between the slack variables and the hinge loss? (ML)
- What are the advantages and disadvantages in comparison to logistic regression? (ML)
- What is the difference between gradients and subgradients? (ML)
- What is the definition of a kernel and its relation to an underlying feature space? (ML)
- Why are kernels more powerful than traditional feature-based methods? (ML)
- What do we mean by the kernel trick? (ML)

## Vorlesung 10

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

## Misc

- Techniques that can be used for default prediction. (*)