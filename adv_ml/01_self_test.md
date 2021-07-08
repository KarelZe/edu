# Selbst-Testfragen

Nachfolgende Fragen eigenen sich zur Prüfungsvorbereitung mittels **Active Recall** gedacht und eine Ergänzung zu [Karteikarten](00_anki.md).

Zur Herkunft der Fragen:
- Fragen aus Altklausuren sind mit einem Stern (⭐) markiert. 
- Ein weiterer Teil der Fragen stammt aus der Vorlesung Maschinelles Lernen (Grundverfahren). Diese Fragen sind mit einem Gehirn (🧠) gekennzeichnet.
- Fragen der University of Toronto sind mit einem Camp (🏕️) markiert.
- Fragen der University of Berkley mit einem Feuerwehrmann (🧑‍🚒)
- Die übrigen Fragen sind eigene Fragen oder es handelt sich um Interviewfragen.

## Überblick
![Überblick über Algorithmen der Vorlesung](./../.gitbook/assets/adv_ml_map_of_algorithms.png)

## Big Data

<details>
<summary>F: What are the characteristics of big data? ⭐</summary>
<ul>
  <li>volume</li>
  <li>variety</li>
  <li>velocity</li>
  <li>veracity</li>
  <li>value</li>
</ul>
</details> 
 
- F: *Explain three characteristics of big data?* ⭐
- F: *What is the difference between veracity and variety?* 

## ML vs. Statistics vs. Econometrics
- F: *Compare ML to Statistics. What are the most significant differences?* 
- F: *Compare ML to Econometrics. In which way do both differ?* 


## Structure of data / CRISPDM / Taxonomy

- F: *What are characteristics of unstructured data?* Explain them. ⭐
- F: *What is unsupervised learning?* ⭐
- F: *Give two examples for unsupervised learning techniques.* 
- F: *Give examples for structured / unstructured data.* 
- F: *Give a brief explanation of categorical, binary, ordinal and numeric variables.* 
- F: *Explain common techniques for data gathering.* 
- F: *Why is it desirable to work on normalized data?* 
- F: *Explain common techniques to analyse the relationship between variables.* 
- F: *How can missing data be replaced? Explain.* 
- F: *Explain 3 patterns in which missing data can occur.* 
- F: *What is a training, test and validation set for?*
- F: *What is the risk with tuning hyperparameters using a test dataset?* 🧑‍🚒

## Multiple Linear Regression

- F: *Explain how linear regression works.*
- F: *What is the purpose $$\beta$$ in a *Multiple Linear Regression Model*?* 
- F: *Explain how an optimal estimate for $$\beta$$ can be derived.*
- F: *Compare Multiple Linear Regression to LASSO. Why is it desirable to penalize a Linear Regression model?* 
- F: *Compare Multiple Linear Regression to Ridge Regression. Why is it desirable to penalize a Linear Regression model?* 
- F: *Name two measure to test the goodness of fit of a Linear Regression model. (&rightarrow; Total Sum of Squares / $$R^2$$) 
- F: *Explain scenarios, where Ridge Regression would be preferred over LASSO.* 
- F: *Write the definitions R^2, Adj. $$R^2$$, MAE, RMSE.* 
- F: *Compare $$R^2$$, Adj. $$R^2$$ to MAE, RMSE. Name advantages and drawbacks.*  
- F: *Compare $$R^2$$, Adj. $$R^2$$ to MAE, RMSE. Which of these is normed.* 
- F: *Explain the 3 steps in fitting a regression model.* 
- F: *What is the advantage of using $$R^2$$ over SST?* 
- F: *In which way does adjusted $$R^2$$ improve the standard $$R^2$$?* 
- F: *Explain the purpose of conducting an ANOVA test?* 
- F: *Is the F-static normalized?* What values can the F static take?* 
- F: *How can the significance of a model be tested?* 
- F: *Why does the improvement when adding new explanatory variables follow a chi-squared distribution with one degree of freedom?* 
- F: *What is problematic about Multicollinearity?* 
- F: *How can Multicollinearity be resolved?* 
- F: *How does correlations and multicollinearity relate?* 
- F: *Give the definition of the Variance Inflation Factor.* 
- F: *Explain how the Variance Inflation Factor can be calculated.* 
- F: *Name implications when residuals of a general linear regression model are not normally distributed.* 
- F: *Why do errors of a linear regression model have to be normally distributed?* 
- F: *Why does variance of regression errors in a linear regression model has to be constant?* 
- F: *Explain the concept of heteroscedasticity for regression errors.* 
- F: *Define the coefficient of partial determination.* 
- F: *How do the coefficient of partial determination and F-test relate?* 
- F: *Why is it not desirable to use Linear Regression for default prediction?* 


## Logistic Regression
- F: *In which day does logistic regression and linear regression differ?*
- F: *Explain what logistic regression is.* 
- F: *How is the maximum likelihood estimated in a logistic regression setting?* 
- F: *What are the advantages of logistic regression over SVMs?* 

- F: *What is the effect on the coefficients of logistic regression if two predictors are highly correlated?*
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *Calculate the probabilities of ... using logistic regression model.* 
- F: *How can logistic regression enhanced to a multiple logistic regression case?* 

## Classification Evaluation
- F: *What is an imbalanced dataset in classification?* ⭐

- F: *How do you deal with imbalanced data in classification?*
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *Why is it a bad idea to evaluate your algorithm on the training set?* 🧠
- F: *What is the advantage/disadvantage of $$k$$-fold CV vs. Hold-out method?*
- F: *Give an example for True Positive Rates etc.?* 
- F: *Explain what precision and recall are. How do they relate to the ROC-Curve?*
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *Is it better to have many false positives, or too many false negatives?*
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *Draw a ROC Curve for given metrics.* 
- F: *Interpret a ROC Curve.* 
- F: *How is the AUC be calculated?* 
- F: *Accuracy should not be the only criteria when comparing classifiers. Name 4 others.* 
- F: *Is Kappa static sensitive to imbalanced data?* 
- F: *How can Kappa static be interpreted?* 
- F: *How is Kappa static defined?* 
- F: *In which way does the F-measure improve over simpler measure like precision?* 
- F: *How is the F measure defined?* 
- F: *What values can a F measure take?* 
- F: *Define precision / recall / sensitivity / False Positive Rate.* 
- F: *Give an intuition for precision / recall / sensitivity...* 
- F: *Derive a confusion matrix from given TP, FP...* 
- F: *When classifying why is it not just sufficient to look at the accuracy?* 
- F: *Draw a confusion matrix. Include the metrics, that are inside the cells.* 
- F: *How can a standard 2x2 confusion matrix be enhanced for a multi-classification case?* 
- F: *Are ROC curves / is AUC sensitive to imbalanced data?* If yes, how can it be resolved?* 
- F: *What kinds of datasets are difficult for a linear classifier to correctly classify?


## Cross-Validation

- F: *What is the motivation to use resampling methods such as cross validation?* 
- F: *What are drawbacks of resampling approaches?* 
- F: *How should we tune parameters for machine learning models?* ⭐
- F: *Explain purged $$k$$-fold cross-validation.* ⭐
- F: *How should we divide data into training and testing for a time series dataset?* ⭐

- F: *What are bias and variance, and what are their relation to modelling data?*
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *Name at least techniques for cross validation.* 
- F: *Explain $$k$$-fold cross-validation.* 
- F: *Explain the validation set approach?* 
- F: *Explain the Leave-One-Out Cross-Validation.* 
- F: *What is the motivation to perform purged $$k$$-Fold Cross Validation.* 
- F: *Why is bootstrapping used? Why is bootstrapping desirable?* 
- F: *Explain what bootstrap is.* 


## Shrinkage Methods
- F: *Explain how forward stepwise selection works in 3 steps.* 
- F: *Explain how backward stepwise selection works in 3 steps.* 
- F: *Compare the subset selection methods forward and backward stepwise selection.* 
- F: *When is it desirable to use backward stepwise selection and when is it desirable to use forward stepwise selection?* 
- F: *What is an alternative to subset selection methods?* 
- F: *What are the reasons why shrinkage methods such as LASSO are preferred over subset selection methods such as forward stepwise selection?*
- F: *Compare the stepwise inclusion regression method to stepwise exclusion regression method and standard stepwise regression method.* 
- F: *Explain how the stepwise inclusion regression method / ... /... works.* 
- F: *In which way do stepwise inclusion method and stepwise exclusion method differ?* 

- F: *Explain what regularization is and why it is useful*
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *Explain the ridge regression.* ⭐
- F: *Explain LASSO.*
- F: *Explain the difference between LASSO and ridge regression?* ⭐
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *In practice, explain what is the main difference between ridge regression and LASSO.* ⭐
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *Explain what is the difference between LSSO and linear regression?* ⭐
- F: *What are the main applications of LASSO?*⭐
- F: *Compare LASSO and the stability selection technique.*⭐
- F: *How do we apply the kernel trick to ridge regression?* 🧠
- F: *Why does it make sense to penalize the norm of the weight vector?* 🧠
- F: *Which norms can we use and what are the different effects?* 🧠
- F: *Give the formula for ridge regression and explain its components.*
- F: *Give the formula for LASSO and explain its components.*

- F: *Name one major advantage of LASSO over ridge regression.*
- A: Lasso yields sparse models, that is, models that only involve a subset of other variables.

- F: *How should $$\lambda$$ be selected for ridge regression / LASSO?*
- F: *Explain how selecting tuning parameters works for ridge regression.*

## Dimensionality Reduction

- F: *What are the advantages of sparse PCA over PCA?*⭐
- F: *What does dimensionality reduction mean?* 🧠
- F: *What is PCA?* 🧠
- F: *What are three things, that PCA does?* 🧠
- F: *What are the roles of the Eigenvectors and Eigenvalues in PCA?* 🧠
- F: *Can you describe applications of PCA?* 🧠
- F: *Give the definition for PCA*
- F: *Explain the ordinary PCA.*
- F: *Explain the sparse PCA.*
- F: *Explain the nonlinear PCA.*
- F: *Explain the kernel PCA.*
- F: *Explain the major difference of sparse PCA over ordinary PCA.*
- F: *Explain the major difference of non-linear PCA over ordinary PCA.*
- F: *Explain the major difference of kernel PCA over ordinary PCA.*
- F: *Give applications for PCA.*

## Decision Trees

- F: *Mention three characteristics of impurity measures?* ⭐
- F: *What are advantages of decision trees over random forests?* ⭐
- F: *How can continuous attributes be handled in Decision Trees?* ⭐
- F: *Explain what a decision tree is.*
- F: *What are useful splitting criterions?* 🧠
- F: *How can we influence the model complexity of the tree?* 🧠
- F: *Name 3 impurity measures.*
- F: *Compare the Gini-Coefficient to Entropy and the resubstitution error.*
- F: *Name 3 conditions an impurity measure has to fulfil.*
- F: *When should the Gini-Coefficient be used? When is it desirable to use the Entropy?*
- F: *Explain how categorical features can be split?*
- F: *Explain how numerical features can be split?*
- F: *What is the motivation to prune a decision tree?*
- F: *Explain how growing a decision tree works?*
- F: *How can decision trees be applied to a regression case?*
- F: *Name several advantages / disadvantages of decision trees*

## Bagging, Boosting and RF

- F: *What are tuning parameters for Boosting?* ⭐
- F: *How does Boosting work for regression?* ⭐
- F: *Explain what Boosting is*
- F: *Explain what Bagging is.*
- F: *What ensemble techniques can be applied?*
- F: *How does Boosting work for classification?*
- F: *How does Bagging differ from Boosting? Explain the differences?*
- F: *How does Bagging work for regression?*
- F: *How does Bagging work for classification?*
- F: *What is the main advantage and disadvantage of a random forest over a decision tree?* ⭐
  
- F: *Describe how Gradient Boosting works.
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *Compare Boosting trees to Random Forests. What are the differences?*
- F: *Explain how a Random Forest improves ordinary decision trees.*
- F: *Explain what a Random Forest is?*
- F: *When can it be advantageous to use Random Forests over Decision Trees?*
- F: *What are tuning parameters for Decision Trees?*
- F: *What are tuning parameters for Random Forests?*
- A: No. Trees + No. of predictors used to build each tree.
- F: *What is an ensemble algorithm? Give on example from the class of an ensemble model that gave improved performance over a base model.*

- F: *Compare supervised learning to unsupervised learning. How do they differ?* 
- F: *What are advantages / disadvantages of unsupervised learning techniques?*

- F: *What is PCA commonly used for?*
- F: *How can the proportion of variance explained by $$m$$ variables be calculated?*
- F: *Calculate the PCA for the first 2 components?*
- F: *Sketch the algorithm for calculating the first two PCA components.*


## k-means Clustering

- F: *Explain the $$k$$-means clustering algorithm* ⭐
- F: *How is the clustering problem defined?* 🧠
- F: *Why is clustering called unsupervised?* 🧠
- F: *How do clustering methods work? What is the rule of the cluster-2-cluster distance and which distances can we use?*  🧠
- F: *How does the $$k$$-mean algorithm work?* 🧠
- F: *What are the 2 main steps of $$k$$-means?* 🧠
- F: *Why does $$k$$-means converge? What is it minimizing.* 🧠
- F: *Does $$k$$-means find a global minimum of the objective?* 🧠
- F: *Name similarity measures. Name an advantage and disadvantage for each of them.*
- F: *Compare similarity measures for low and high-dimensional spaces.*
- F: *In unsupervised learning, if a ground truth about a dataset is unknown, how can we determine the most useful number of clusters to be?*
- A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)

- F: *What is the main idea of clustering?*
- F: *When is a clustering optimal?*
- F: *What properties does a set has to fulfil when $$k$$-means clustering should be applied.*
- F: *How does minimizing the WCV relate to solving the clustering problem?*
- F: *What are alternatives to $$k$$-means clustering?
- F: *How can $$k$$-means clustering be phrased as an optimization problem?*
- F: *What are advantages / drawbacks of using the $$k$-means algorithm?*
- F: *Name distance measures, that can be used with in conjunction with $$k$$ means. When should they be used.*
- F: *Draw a dendrogram from a given clustering.*
- F: *Explain how the algorithm for hierarchical clustering works.*
- F: *Explain different linkage types, that can be used for clustering.*
- F: *Draw different linkage types visually.*
- F: *What is the impact of using different linkage types?*
- F: *Name practical issues that arise with hierarchical or $$k$$-means clustering.*
- F: *Give applications for clustering.*

## SVMs

- F: *Explain what a SVM is.*
- F: *Required scaling for SVMs?* ⭐
- A: Features should be scaled to the interval $[0,1]$.
- F: *Name advantages of SVMs over logistic regression.* ⭐
- F: *Recommendations to improve results of a SVM.* ⭐
- F: *Why is it good to use a maximum margin objective for classification?* 🧠
- F: *How can we define the margins as optimization problem?* 🧠
- F: *What are slack variables and how can they be used to get a "soft" margin?* 🧠
- F: *How is hinge loss defined?* 🧠
- F: *What is the relation between the slack variables and the hinge loss?* 🧠
- F: *What are the advantages and disadvantages in comparison to logistic regression?* 🧠
- F: *What is the difference between gradients and subgradients?* 🧠
- F: *What is the definition of a kernel and its relation to an underlying feature space?* 🧠
- F: *Why are kernels more powerful than traditional feature-based methods?* 🧠
- F: *What do we mean by the kernel trick?* 🧠
- F: *What is the central idea of SVMs?*
- A: We try to find a plane that separates the classes in the feature space. If that's not possible, we get creative in two ways:
    - We soften what we mean by separates through the introduction of support vectors.
    - We enrich and enlarge the feature space so that separation is possible. This means the feature space get's transformed.
- F: *What does a Maximal Margin Classifier maximize for?*
- F: *How do a Maximal Margin Classifier, SVMs and Logistic Regression relate?*
- F: *What is the purpose of the support vectors $$\epsilon$$? 
- F: *Explain what is referred to as *feature expansion*?
- F: *Name and define kernels that can be used with SVMs.*
- F: *Compare SVMs to logistic regression*
- A:
  - When classes are not linearly separable, SVM does better than logistic regression. ([See here](https://stats.stackexchange.com/a/95348))
  - Otherwise, the performance of logistic regression (with ridge penalty) and SVM are very similar. 
  - To estimate probabilities, the choice should be logistic regression.
  - If interpretability and speed is a major concern, logistic regression should be used.
- F: *Explain how Least-Squares Support Vector Regression improves ordinary SVMs for bond recovery rate prediction.*
- F: *Explain how semiparametric Least-squares Support Vector Regression improves ordinary SVMs for bond recovery rate prediction.*
- F: *Name proper alternatives to standard SVMs for default prediction.*

## Neural Net

- F: *Explain what a Neural Network is.*
- F: *How does logistic regression relate to neural networks?* 🧠
- F: *What kind of functions can single layer NN learn?* 🧠
- F: *Why do we need non-linear activation functions?* 🧠
- F: *What activation functions can we use and what are advantages / disadvantages of those?* 🧠
- F: *What output layer and loss function use given the task (regression / classification)?* 🧠
- F: *Why not use a sigmoid activation function?* 🧠
- F: *Why neural networks can overfit and what are the options to prevent it?* 🧠
- F: *Early stopping, cross-validation and network pruning are techniques to prevent overfitting of Neural Nets. Explain them.* 
- F: *What makes an Ordinary Least Square Regression different from a neural net?*
- F: *Explain what Principal Component Regression is.*
- F: *Explain how Principal Component Regression works.*
- F: *Explain the purpose of activation functions.*
- F: *Define different activation functions and sketch them.*
- F: *Sketch a neural network with 3 input units, 4 hidden units and 2 output units. Make sure to label its components.*
- F: *How is a recurrent neural net different from an ordinary neural network?*
- F: *Explain how back-propagation works in neural network.*
- F: *What is necessary to apply Neural Nets to classification tasks?
- F: For a fully-connected deep network with one hidden layer, increasing the number of hidden units should have what effect on bias and variance? 🧑‍🚒
- F: *What is the problem of Neural nets with many parameters?* 
- F: *What is the impact of a higher number of layers and hidden units in a neural net?*
- A:
  - the more layers and more hidden units in a model, the more capacity it has.
  - There might not be enough data. A high capacity model easily overfits training data and results in a bad performance during testing.
- F: *Explain what network pruning is.*
- F: *Explain how early stopping works with Neural Nets.*
- F: *Consider the following two multilayer perceptrons, where all of the layers use linear activation functions. Give an advantage of Network A over Network B.* 🏕️
![Network architectures](./../.gitbook/assets/network_architecture.jpg)


## RNN

- F: *Explain Recurrent Neural Networks (RNN)* ⭐
- F: *What types of RNN were discussed in class?*
- F: *Give applications of RNNs.*
- F: *What are key components of RNNs?*

## LSTM

- F: *Explain LSTMs.* ⭐
- F: *LSTMs are suitable for which type of analysis?* ⭐
- F: *How can we use LSTMs for time series dataset?* ⭐
- F: *Explain how LSTMs update their memory.*
- F: *Give applications of LSTMS.*

## Methods in NLP
- F: *How does the concept of Word2Vec work?*
- F: *How can the notion of similarity be embedded in a vector-to-word conversion?*
- F: *Sketch and explain the process of applying Continous Bag of Words to text prediction.*
- F: *Why is Softmax used in a CBOW model?*
- F: *How does the Skip-Gram Model work*?
- F: *Compare the Skip-Gram Model to CBOW. In which way are they different?*
- F: *Explain different types of NLP applications including examples.*
- F: *Explain what is commonly referred to as 'Named Entity Recognition'*
- F: *Name different approaches for 'Named Entity Recognition'. How do they relate.*
- F: *Explain what a Sentiment Analysis is.*
- F: *Name different Deep Learning Models used in NLP.*


## RNNs / GRUs / Bidirectional LSTMs
- F: *Explain RNNs.*
- F: *Explain GRUs.*
- F: *Explain Bidirectional LSTMs.*
- F: *Explain Differences between RNNs and GRUs.*
- F: *Explain 'Bidirectional Long Short Term Memory Network'.*
- F: *What problem of RNN's do LSTMs solve?*
- F: *Explain what is called the 'vanishing gradient problem'.*
- F: *Why is it desirable to use RNNs instead of standard networks for NLP?*
- F: *Explain why sigmoid activation results tend to be almost $$0$$ or $$1$$?
- F: *Adding more hidden layers will solve the vanishing gradient problem for a 2 layer neural network.* 🧑‍🚒
- F: *xxx suffer(s) from the vanishing gradient problem. Circle all that apply and JUSTIFY YOUR ANSWER.* 🧑‍🚒
- F: *Adding L2-regularization will help with vanishing gradients* 🧑‍🚒

## Misc

- F: *Techniques that can be used for default prediction.* ⭐