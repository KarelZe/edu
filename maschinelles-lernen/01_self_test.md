# Selbsttestfragen

Nachfolgende Fragen eigenen sich zur Prüfungsvorbereitung mittels **Active Recall** gedacht und eine Ergänzung zu Karteikarten.

Offizielle Fragen sind mit 🧠 markiert. Probeklausurfragen mit einem 🦧. Fragen der University of Berkley mit 🧑‍🚒. Eigene Fragen haben keine Markierung.

## Linear Regression

* Under which assumptions is the least squares objective from linear regression equivalent to a maximum likelihood objective?🦧
* Give the formula for ridge regression and explain its components.
* Give the formula for LASSO and explain its components.
* Compare Multiple Linear Regression to LASSO. Why is it desirable to penalize a Linear Regression model?
* Why do errors of a linear regression model have to be normally distributed?

## Linear Classification

* Write down the objective of linear binary logistic regression. The samples are given by $$x_{i}$$ and the labels by $$c_{i} \in\{0,1\}$$. How is $$p\left(c_{i} \mid \boldsymbol{x}_{i}\right)$$ assumed to be distributed in binary logistic regression?🦧

## Model Selection

* Why is it a bad idea to evaluate your algorithm on the training set? 🧠
* What is the difference between true and empirical risk? 🧠
* The true risk can be decomposed in which parts?🧠
* How is the bias and the variance of a learning algorithm defined and how do they contribute to the true risk?🧠
* What is the advantage/disadvantage of k-fold CV vs. the Hold-out method?🧠
* Why does it make sense to penalize the norm of the weight vector?🧠
* Which norm can we use and what are the different effects?
* What is the effect of early stopping?🧠

## Nearest Neighbour Algorithms, Trees, and Forests

* What we mean with non-parametric / instance-based machine learning algorithms?🧠
* How $$k$$-Nearest neighbour works?🧠
* Why is it hard to use for high-dimensional data?🧠
* How to search for nearest neighbours efficiently?🧠
* What is a binary regression / decision tree?🧠
* What are useful splitting criterions?🧠
* How can we influence the model complexity of a tree?🧠
* Why is it useful to use multiple trees and randomization?🧠
* Name at least two advantages and two disadvantages of decision trees. 🦧
* Which data structure is usually used to efficiently implement k-Nearest Neighbours? Name the main steps in building that data structure.🦧

## Clustering

* _How is the clustering problem defined?🧠_
  * Clustering tries to find a natural grouping within the data.
  * One tries to maximize the intra-cluster similarity and minimize the inter-cluster similarity.
* _Why is it called 'unsupervised'?🧠_
  * It's called unsupervised, as the data is unlabeled. There is no supervisor, that tells us in advance to which cluster a training data point belongs. Hence, unsupervised. The structure is actually learned from the data. 
* _How do hierarchical clustering methods work?_ 🧠
  * **Init-phase:** Each of the $$n$$samples becomes a cluster itself
  * **Iterate-phase:** 
    1. Find closest clusters and merge them
    2. Proceed until we have a single cluster
* _What is the rule of the cluster-2-cluster distance and which distances can we use?_🧠
  * So called cluster linkage types define the distance between two clusters. Commonly used are
    * Single linkage
    * Complete linkage
    * Average linkage
    * Centroid linkage
* _How does the_ $$k$$_-mean algorithm work? What are the two main steps?_🧠
  * The two main steps are the **assigment** and **adjustment step**.
  * **Assignment step:** 
    * Assign each sample to its closest centroid $$z_{n}=\arg \min_{k}\left\|\boldsymbol{c}_{k}-\boldsymbol{x}_{n}\right\|^{2}$$ 
  * **Adjustment Step:**
    * Adjust the centroids to be the means of the samples assigned to them: $$c_{k}=\frac{1}{\left|X_{k}\right|} \sum_{\boldsymbol{x}_{i} \in X_{k}} \boldsymbol{x}_{i}, \quad X_{k}=\left\{\boldsymbol{x}_{n} \mid z_{n}=k\right\}$$ 
* _Why does the algorithm converge? What is it minimizing?_🧠
  * $$k$$-means minimizes the Sum of Squared Distances \(SSD\). By checking, if a cluster centeroids exists, that is closer to a point than its current cluster centroid the SSD is reduced. If no closer custer centre exists and the SSD remains constant.
  * SSD is defined as $$\operatorname{SSD}(C ; \mathcal{D})=\sum_{i=1}^{n} d\left(\boldsymbol{x}_{i}, c\left(\boldsymbol{x}_{i}\right)\right)^{2} $$ 
* _Does_ $$k$$_-means find a global minimum of the objective?🧠_
  * No, generally it doesn't. Finding a global minimum is a NP-hard problem. One would have to check all assignments to find the global best solution.
  * More over, the result of $$k$$-means is heavily dependent on the initialisation.

## Dimensionality Reduction

* What does dimensionality reduction mean?🧠
* What is PCA? 🧠
* What are three things that it does?🧠
* What are the roles of the Eigenvectors and Eigenvalues in PCA?🧠
* Can you describe applications of PCA?🧠
* Why should each dimension have a unit variance / be normalized?

## Density Estimation and Expectation Maximization

* What are parametric methods and how to obtain their parameters?🧠
* How many parameters have non-parametric methods?🧠
* What are mixture models?🧠
* Should gradient methods be used for training mixture models?🧠
* How does the EM algorithm work?🧠
* What is the biggest problem of mixture models?🧠
* How does EM decomposes the marginal likelihood?🧠
* Why does EM always improve the lower bound?🧠
* Why does EM always improve the marginal likelihood?🧠
* Why can we optimize each mixture component independently with EM?🧠
* Why do we need sampling for continuous latent variables?🧠

## Kernel methods

* What is the definition of a kernel and its relation to an underlying feature space?🧠
* Why are kernels more powerful than traditional feature-based methods?🧠
* What do we mean by the kernel trick?🧠
* How do we apply the kernel trick to ridge regression?🧠
* Study the kernel properties, where is symmetry relevant? Where and why is positive definiteness of matrix important?
* What is the impact of changing $$\sigma$$ in a RBF kernel?
* What is the actual gain from using polynomial kernels?

## SVMs

* Why is it good to use a maximum margin objective for classification?🧠
* How can we define the margin as an optimization problem?
* What are slack variables and how can they be used to get a 'soft' margin?🧠
* How is the hinge loss defined?🧠
* What is the relation between the slack variables and the hinge loss?🧠
* What are advantages and disadvantages in comparison to logistic regression?🧠
* What is the difference between gradients and sub-gradients?🧠
* First, explain the intuition behind slack-variables in support vector machine training. Second, for a single data-point $$\left(\boldsymbol{x}_{i}, c_{i}\right)$$ the margin condition with slack variable $$\xi_{i}$$ is given as

  $$
  c_{i}\left(\boldsymbol{w}^{T} \boldsymbol{x}_{i}+b\right) \geq 1-\xi_{i}
  $$

  * Assuming $$0 \leq \xi_{i} \leq 1$$, is $$\boldsymbol{x}_{i}$$ classified correctly?
  * Assuming $$\xi_{i}>1$$, is $$x_{i}$$ classified correctly?🦧

## Bayesian Learning

* What are the two basic steps behind Bayesian Learning?🧠
* Why is Bayesian Learning more robust against overfitting?🧠
* What happens with the posterior if we add more data to the training set?🧠
* What is completing the square and how does it work?🧠
* For which 2 cases can Bayesian Learning be solved in closed form?🧠
* Which approximations can we use if no closed form is available?
* How can we derive Bayesian Linear regression?🧠
* What is the advantage of Bayesian Linear Regression over Ridge regression? What is the conceptual difference?🧠
* What is the major advantage of Gaussian processes over kernel ridge regression?🧠
* Why are GPs a Bayesian approach?🧠
* What principle allowed deriving GPs from a Bayesian regression point of view?🧠
* Gaussian Processes\(GP\) are also referred to as a "Bayesian Kernel Regression" approach. Why? 🦧

## Neural Nets

* How does logistic regression relate to neural networks?🧠
* What kind of functions can single-layer neural networks learn?🧠
* Why do we need non-linear activation functions?🧠
* What activation functions can we use and what are the advantages/disadvantages of those?🧠
* What output layer and loss function to use given the task \(regression, classification\)?🧠
* Why not use a sigmoid activation function?🧠
* Derive the equations for forward and backpropagation for a simple network.🧠
* What is mini-batch gradient descent? Why use it instead of stochastic gradient descent or full gradient descent?🧠
* Why neural networks can overfit and what are the options to prevent it?🧠
* Why is the initialization of the network important?🧠
* What can you read from the loss-curves during training \(validation and training loss\)?🧠
* How can we accelerate gradient descent?🧠
* How does Adam work?🧠
* What is the key idea behind second-order optimization methods? What are their benefits? Why are second-order optimization methods usually not applicable for Deep Neural Networks? 🦧
* _Explain why sigmoid activation results tend to be almost_ $$0$$ _or_ $$1$$?
* Adding more hidden layers will solve the vanishing gradient problem for a two-layer neural network. 🧑‍🚒
* xxx suffer\(s\) from the vanishing gradient problem. Circle all that apply and JUSTIFY YOUR ANSWER. 🧑‍🚒
* Adding L2-regularization will help with vanishing gradients 🧑‍🚒
* Early stopping, cross-validation, and network pruning are techniques to prevent overfitting of Neural Nets. Explain them. 
* For a fully-connected deep network with one hidden layer, increasing the number of hidden units should have what effect on bias and variance? 🧑‍🚒
* What is the problem of Neural nets with many parameters?
* Explain what network pruning is.
* Explain how early stopping works with Neural Nets.

## CNNs

* Why are fully connected networks for images a bad idea and why do we need images?🧠
* What are the key components of a CNN?🧠
* What hyper-parameters can we set for a convolutional layer and what is their meaning?🧠
* What hyper-parameters can we set for a pooling layer and what is their meaning?🧠
* How can we compute dimensionality of the output of a convolutional layer?🧠
* Describe basic properties of 'AlexNet' and 'VCG'.🧠
* What is the main idea of 'ResNet' to make it very deep?🧠
* Why is it not feasible to use a fully connected layer for images? How do convolutional neural networks solve this problem and which property of an image do they exploit?🦧
* How do LSTMs actually avoid the vanishing gradient problem?

## General

* What is the difference between AI and ML?
* What are the hyperparameters for choosing the model complexity for each of the following algorithms. Name at least one hyperparameter for every algorithm.
  * Neural Networks
  * Support Vector Machines
  * Gaussian Processes
  * Decision Trees? 🦧
* You are given the following optimization problem:

  $$
  \begin{aligned}
  &\underset{a}{\operatorname{argmax}} a^{2} h \\
  &\qquad \text { s.t. } S_{\max } \geq 2 a^{2}+4 a h
  \end{aligned}
  $$

  Write down the Lagrangian. Derive the optimal value for $$a$$ depending on your lagrangian multiplier. 🦧

