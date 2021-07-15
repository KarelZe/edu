# Selbsttestfragen

Nachfolgende Fragen eigenen sich zur Prüfungsvorbereitung mittels **Active Recall** gedacht und eine Ergänzung zu [Karteikarten](https://github.com/KarelZe/edu/tree/55e29762b35fb16586fce118e8feaee3aa720fea/adv_ml/00_anki.md).

Zur Herkunft der Fragen:

* Fragen aus Altklausuren sind mit einem Stern \(⭐\) markiert. 
* Ein weiterer Teil der Fragen stammt aus der Vorlesung Maschinelles Lernen \(Grundverfahren\). Diese Fragen sind mit einem Gehirn \(🧠\) gekennzeichnet.
* Fragen der University of Toronto sind mit einem Camp \(🏕️\) markiert.
* Fragen der University of Berkley mit einem Feuerwehrmann \(🧑‍🚒\)
* Die übrigen Fragen sind eigene Fragen oder es handelt sich um Interviewfragen.

## Überblick

![&#xDC;berblick &#xFC;ber Algorithmen der Vorlesung](../.gitbook/assets/adv_ml_map_of_algorithms.png)

## Big Data

* F: _What are the characteristics of big data?_ ⭐
  * volume
  * variety
  * velocity
  * veracity
  * value
* F: _Explain three characteristics of big data?_ ⭐
  * Volume refers to the sheer amount of data that is generated.
  * Variety refers to diversity of types of data. Data can come in structured, semi-structured or even unstructured types.
  * Velocity refers to the sheer speed at which data is generated \(and processed\).
  * Veracity refers to the quality of data or accuracy of the collected data. To resolve data quality issues one has to apply sophisticated pre-processing.
* F: _What is the difference between veracity and variety?_

  Veracity refers to the quality of data \(e. g. noise in data\). While variety refers to types of data \(e. g. unstructured data\) in which data can come. As data is often collected from different sources both their types and their quality can differ.

## ML vs. Statistics vs. Econometrics

* F: _Compare ML to Statistics. What are the most significant differences?_

  Statistics is:

  * based on hypothesis, then collection of data and analysis
  * model-oriented with an emphasize on parametric models
  * focus on understanding on hypothesis testing

  Whereas in Machine Learning:

  * there is seldomly a priori hypothesis
  * data is collected in advance
  * analysis is data-driven not hypothesis-driven
  * analysis is algorithm-oriented rather than model-oriented
  * focus lies on prediction

* F: _Compare ML to Econometrics. In which way do both differ?_

  Econometrics is:

  * concerned about casual interference and counterfactuals
  * mostly centred around linear regressions and complex structural models
  * standard errors are often reported after one run

  Machine Learning is:

  * concerned about prediction
  * using all sorts of data-driven models e. g. Trees, NN etc.  

## Structure of data / CRISP-DM / Taxonomy

* F: _What are characteristics of unstructured data? Explain them._ ⭐

  Unstructured data is:

  * **Nonnumeric:** No predefined numeric representation for the constructs of interests. Must be defined.
  * **Multifaceted:** Each aspect of data provides unique information for studying and different types of research goals. E. g. voice data present information about the speaker such as pitch, speech rate. Data can be used both in psychology and communication. 
  * **Concurrent representation:** Represents different phenomena at the same time. One can study different research questions with one single unstructured data. TODO: Paper nachlesen

* F: What is referred to as 'structured data'?
  * Structured data is data that adheres to a pre-defined data model and is therefore straightforward to analyse.
  * Structured data conforms to a tabular format with a relationship between the different rows and columns.
* F: _What is unsupervised learning?_ ⭐
  * Observe data and construct a low complexity description of the data. 
  * That means in unsupervised learning the dataset that a data set transforms into is _not previously known_ or understood. Data is not labelled. \(Grooking p. 13\) 
  * We observe only the features $$X_1, X_2,\ldots, X_P$$. We are not interested in prediction, because we do not have an associated response variable $$Y$$.
* F: _What is supervised learning?_ ⭐
  * We observe both a set of features $$X_1,X_2,\ldots,X_P$$ for each object, as well as a response or outcome variable $$Y$$. The goal is then to predict $$Y$$ using $$X_1, X_2,\ldots,X_P$$
* Examples include clustering and PCA.
* F: _Give two examples for unsupervised learning techniques._ 
  * Clustering algorithms such as $$k$$-means
  * Dimensionality reduction techniques such as PCA
* F: _Give examples for structured / unstructured data._

  **Unstructured:** \(low degree of organization\)

  * Video Data, as video comes in different formats, compression ratios, sizes, where the video has to be transformed first to extract information from every single frame
  * Image Data, just like videos.

  **Structured:** \(high degree of organization\)

  * Numeric secondary data e. g. sales figures, as they come in a standardized format and easy to process format e. g. float with $$x$$ decimal places 
  * Categorial data e. g. gender, as there are predefined formats

* F: _Give a brief explanation of categorical, binary, ordinal and numeric variables._
  * **categorical / nominal:** Names of things or symbols.
  * **binary:** A nominal variable with two categories or states: 0 or 1.
  * **ordinal:** Ordinal variables have a meaningful order or ranking among them, but the magnitude between successive values is not known.
  * **numeric:** A quantitative variable. Numeric variables could be interval-scaled or ratio-scaled.
* F: _Which steps are part of the CRISP-DM model? Explain them in-depth._
  1. Business understanding i. e. developing an understanding of business objects and requirements of the data mining
  2. Data understanding i. e. identify and collect the data set needed to fulfil the business goals
  3. Data preparation i. e. prepare data for modelling
  4. Modelling i. e. build several models and assess them on a technical level.
  5. Evaluation i. e. Evaluate whether models are able to help achieve the business goals. Plan on the next steps.
  6. Deployment i. e. Deploy model to production. Make it accessible to customers.
* F: _Explain common techniques for data gathering._
  * **Bulk downloads:** Downloading large amounts of data. Often done using sophisticated software.
  * **APIs:** Accessing data through machine readable interfaces. Examples include Google Maps API.
  * **Web Scraping:** Extraction of data from websites. Often done using bots and web crawlers or manually.
* F: _Why is it desirable to work on normalized data?_
  * Some algorithms require normalized data, such as $$k$$-means clustering, which is 'isotropic' in all directions of space and therefore tens to produce more or less round  shapes. Not standardizing data would give more relative on variables with a smaller variance. \([See here.](https://stats.stackexchange.com/a/21226)\) 
* F: _Explain common techniques to analyse the relationship between variables._ 
  * A scatter plot \(or scatter diagram\) is used to show the relationship between variables
  * Bar plot for high dimensional data
  * Mean graph for categorial data
  * Correlation analysis
* F: _How can missing data be replaced? Explain._
  * **mean based imputation:** i. e. mean is calculated from all observations
  * **median based imputation:** Same as above but with median.
  * **stratified imputation:** i. e. categories / structure of data is considered for replacements. E. g. missing height is different for gender male and female.
  * **regressed imputation:** i. e. replacing missing values by predictions of a regression model
* F: _Explain 3 patterns in which missing data can occur._
  * **Completely random / MCAR:** Missing values have no pattern. Can not be predicted.
  * **Missing at random / MaR:** Missing values can be predicted using other data available for observation. Assign a categorial value.
  * **Latent, yet unknown variable:** Missing value depends on latent and highly correlated variable.
* F: _What is a training, test and validation set for?_
  * **Training set** is used to fit all potential models
  * **Validation set** is used to select hyperparameters of a model
  * **Test set** is used to estimate the predictive power of a model on unseen data
* F: _What is the risk with tuning hyperparameters using a test dataset?_ 🧑‍🚒
  * Tuning model hyperparameters to a test set means that the hyperparameters may overfit to that test set. If the same test set is used to estimate performance, it will produce an overestimate. Using a separate validation set for tuning and test set for measuring performance provides unbiased, realistic measurement of performance. \(Berkley p. 14\)

## Multiple Linear Regression

* F: _Explain how linear regression works._
* F: _What is the purpose_ $$\beta$$ _in a Multiple Linear Regression Model?_
  * $$\beta$$ is a $$(p+1)$$-dimensional vector, where $$\beta_0$$ is the intercept and $$\beta_1,\cdots,\beta_k$$ are the regression coefficients of $$k$$ independent variables.
* F: _Explain how an optimal estimate for_ $$\beta$$ _can be derived._

  * A linear regression model has the best fit when the error term $$\epsilon$$ is minimal. To achieve this, the regression coefficients $$\beta$$ have to be estimated such that the error term is minimized. It's common to use squared error terms for $$\| \varepsilon \|_{2}^{2}$$ minimization. 
  * This leads to the following equation:

    $$
    \min _{\boldsymbol{\beta}} \sum_{i=1}^{N}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} x_{i j} \beta_{j}\right)^{2}=\min _{\boldsymbol{\beta}}\|\mathbf{y}-\mathbf{X} \beta\|^{2}
    $$

  TODO: Formel für Linear Regression TODO: Minimierung SSE?

* Which can be reformulated to:

  $$
  \beta=\left(X^{\intercal} X\right)^{-1} X^{\intercal} y
  $$

  $$
  \epsilon=y-X^{\intercal} \beta
  $$

* F: Why do we optimize for the SSE for?
  * It is fully differentiable 
  * Easy to optimize
  * It also makes sense as:

    $$
    f^{*}(x)=\operatorname{argmin}_{f(x)} \mathrm{SSE} \Rightarrow f^{*}(x)=\mathbb{E}[y \mid x]
    $$
* F: _Name two measure to test the goodness of fit of a Linear Regression model._
  * Total Sum of Squares \(SST\)
  * $$R^2$$ 
* F: _Write the definitions_ $$R^2$$_, Adj._ $$R^2$$_, MAE, RMSE._ 
  * $$R^{2}=1-\frac{S S E}{S S T}$$ 
  * $$\text { Adjusted } R^{2}=1-\left(1-R^{2}\right)\left(\frac{n-1}{n-k-1}\right)$$ 
  * $$\text{RMSE}=\sqrt{\frac{1}{n} \sum_{i=1}^{n}\left(y_{i}-\hat{y}_{i}\right)^{2}}$$ 
  * $$\text{MAE}=\frac{1}{n} \sum_{i=1}^{n}\left|y_{i}-\hat{y}_{i}\right|$$ 
  * TODO: n, k einführen....
* F: _Give an intution for_ $$R^2$$ _, MAE and RMSE._
  * $$R^2$$ / adj. $$R^2$$**:** How well can my model explain the variance?
  * **MAE:** How does the model perform on average?
  * **RMSE:** How many large prediction derivations does the model have? \(lecture BDA p. 43\)
* F: _Compare_ $$R^2$$_, Adj._ $$R^2$$ _to MSE, MAE and RMSE. Name advantages and drawbacks._  
  * **MSE:**
    * MSE is differentiable which is important for finding optima. \(+\)
  * **MAE:** 
    * The scale of MAE, RMSE depends on the scale of the dependent variable. \(-\)
    * MAE is not differentiable. \(-\)
    * MAE is more robust to outliers. \(+\)
  * $$R^2$$ **:** 
    * Measure always increases by adding new independent variables which can lead to the addition of redundant variables in the model. \(-\)
* F: _Compare MAE to RMSE._
  * **RMSE** penalizes large errors more than MAE. This can be useful if being off by 10 is more than twice as bad as being of by 5. If however being of by 5 is just as bad as being of by 10, MAE should be preferred. \([See here](https://medium.com/human-in-a-machine-world/mae-and-rmse-which-metric-is-better-e60ac3bde13d).\)
* F: _Compare_ $$R^2$$_, Adj._ $$R^2$$ _to MAE, RMSE. Which of these is normed._ 
  * $$R^2$$ and Adj. $$R^2$$ between$$[0,1]$$. TODO: worse than 0 if prediction is worse than mean  / large SSE vs small SST.
  * MAE, RMSE between$$[0, \infty)$$. If RMSE is acceptable depends on the scale of the variables. [\(see here\)](https://stats.stackexchange.com/a/56332). RMSE and MAE are $$0$$ for models with a perfect fit.
* F: _In which way does adjusted_ $$R^2$$ _improve the standard_ $$R^2$$_?_ 
  * A model might have a good fit in-sample but poor fit on out-of-sample, if to many regressors are used.
  * Adj. $$R^2$$ is a $$R^2$$ which has been corrected by a penalty function and takes into account the number of $$k$$ regressors in the model.
* F: _Explain the 3 steps in fitting a regression model._ 
  * **Specification:** 
    * Determine dependent and explantory variables. 
    * Exclude explantory variables without predicitive power. 
    * Collect data for dependent and explanatory variables.
  * **Fitting / Estimating:**
    * Estimating regression coefficients.
  * **Diagnosis:**
    * Determine the quality of the regression model with e. g. $$R^2$$, adj.$$R^2$$ , MSE and MAE.
    * Determine the models significance and the significance of the regression coefficients.
    * Analyse standard deviation of regression erros.
* F: _Why is it not desirable to use Linear Regression for default prediction?_ 
  * In default prediction one searches for proability of default $$\operatorname{Pr}(\text { default }=\text { Yes } \mid \text { balance })$$ , which ranges between $$0$$ and $$1$$ .
  * Fitting a line between to a binary response variable \(1 = default / 0 = non-default\), could lead to estimates outside the $$[0,1]$$ interval, making them hard to interpret as probabilities i. e. if probabilities are negative.
  * Nevertheless, the predictions provide an ordering and can be interpreted as crude probability estimates.
* F: _Explain scenarios, where Ridge Regression would be preferred over LASSO._ 
  * Ridge only performs parameter shrinkage and no variable selection.
  * Ridge regression is preferred if one wants to insert some prior knowledge into approach. With ridge one has the ability to say that all features have at least some weight, even if it is very little [\(See here.\)](https://qr.ae/pG4QYT)
* F: _Explain scenarios, where LASSO would be preferred over Ridge Regression._ 
  * As with ridge regression, the LASSO shrinks the coefficient estimates towards zero.
  * However, in the case of LASSO some coefficient estimates are forced to be exactly equal to zero \(zeroed out\) when the tuning parameter $$\lambda$$ is sufficiently large. 
  * Therefore, LASSO does variable selection automatically and shrinkage of parameters.
* F: _Compare Multiple Linear Regression to LASSO. Why is it desirable to penalize a Linear Regression model?_ 
* F: _Compare Multiple Linear Regression to Ridge Regression. Why is it desirable to penalize a Linear Regression model?_ 
* F: _Explain the purpose of conducting an ANOVA test?_ 
* F: _Is the F-static normalized?_ _What values can the F static take_
* F: _How can the significance of a model be tested?_ 
* F: _Why does the improvement when adding new explanatory variables follow a chi-squared distribution with one degree of freedom?_ 
* F: _What is problematic about Multicollinearity?_ 
* F: _How can Multicollinearity be resolved?_ 
* F: _How does correlations and multicollinearity relate?_ 
* F: _Give the definition of the Variance Inflation Factor._ 
* F: _Explain how the Variance Inflation Factor can be calculated._ 
* F: _Name common assumptions about error terms._ 
  * 1. Regression Errors are normally distributed 
  * 2. The variance of regression errors is constant 
  * 3. The error terms from different points in time are independent 
  * 4. The residuals are uncorrelated with the independent variable.

    **But:** Linear Regression doesn't need the normal assumption, the estimator can be calculated without any need of such assumption. However, it is convenient from a user point of view to use errors are normally distributed to calculate confidence intervals etc. [\(see here.\)](https://stats.stackexchange.com/a/148812)
* F: _Name implications when residuals of a general linear regression model are not normally distributed._
* F: _Why do errors of a linear regression model have to be normally distributed?_ 
* F: _Why does variance of regression errors in a linear regression model has to be constant?_ 
* F: _Explain the concept of heteroscedasticity for regression errors._ 
* F: _Define the coefficient of partial determination._ 
* F: _How do the coefficient of partial determination and F-test relate?_ 

## Logistic Regression

* F: _In which way do logistic regression and linear regression differ?_
  * _Linear regression is applied to **regression problems**, whereas logistic regression is used for **classification**._
  * _The loss function in linear regression is calculated using SSE, whereas in logistic regression it's maximum likelihood estimation._
  * _The output of linear regression is continous. The output of logistic regression is discrete_
* F: _Explain what logistic regression is._ 
  * Logistic regression is a classification approach. 
  * It is a predictive analysis that describes data and explains the relationship between variables.
  * Logistic regression gives discrete outputs between 0 and 1 for an input variable $$X$$. To do so, a logistic function is utilized:$$p(X)=\frac{e^{\beta_{0}+\beta_{1} X}}{1+e^{\beta_{0}+\beta_{1} X}}$$, which produces a S-shaped like curve.
  * The regression coefficients $$(\beta_0, \beta_1X_1+\cdots+\beta_PX_P)$$ are estimated using the maximum likelihood method.
  * TODO: ecponential trick, why log?
* F: _How is the maximum likelihood estimated in a logistic regression setting?_
  * We try to maximize likelihood to estimate the parameters:

    $$\ell\left(\beta_{0}, \beta_{1}\right)=\prod_{i: y_{i}=1} p\left(x_{i}\right) \prod_{i: y_{i}=0}\left(1-p\left(x_{i}\right)\right)$$

  * The estimates $$\beta_0$$ and $$\beta_1$$ are chosen to maxize the likelihood of the observed data.
* F: _How can logistic regression enhanced to a multiple logistic regression case?_

  * We can generalize to the following form: 

  $$p(X)=\frac{e^{\beta_{0}+\beta_{1} X_{1}+\ldots+\beta_{p} X_{p}}}{1+e^{\beta_{0}+\beta_{1} X_{1}+\ldots+\beta_{p} X_{p}}}$$ , where $$X=\left(X_{1}, \ldots, X_{P}\right)$$ are $$p$$ is the number of predictors.

  * $$\log \left(\frac{p(X)}{1-p(X)}\right)=\beta_{0}+\beta_{1} X_{1}+\ldots+\beta_{P} X_{P}$$ 

* F: _What are the advantages of logistic regression over SVMs?_
  * _When classes are \(nearly\) separable, SVM does better than logistic regression._ \(-\)
  * _When not, logistic regression with \(ridge penalty\) and SVMs are very similar._\(+\)
  * If probability estimates are need, logistic regression is the best choice. \(+\)
  * logistic regression is fast and very easy to interpret. Good as baseline. \(+\)
  * Kernels in logistic regression are computionally expensive \(-\)
* F: _What is the effect on the coefficients of logistic regression if two predictors are highly correlated?_
  * A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* F: _Calculate the probabilities of the credit card example using logistic regression model._
  * _See script p. 18._

## Classification Evaluation

* F: _Draw a confusion matrix. Include the metrics, that are inside the cells._ 
  * ![](../.gitbook/assets/confusion_matrix.svg) 
* F: _Define precision / recall / sensitivity / False Positive Rate._ 
  * ![](../.gitbook/assets/grafik%20%283%29.png) 
* F: _Give an intuition for precision / recall / sensitivity..._ 
  * **Accuracy**: The share of instance that are correctly classified
  * **Precision**: Of examples recognized as cat, what % are actually cats? 95 % means: When classifier says 'cat', in 95 % it is a cat.
  * **Recall:**  Of all images that really are cats, what % were correctly recognized? Of all cats in the data, classifier pulled 90 % of them. \(BDA lecture, slide 43\)
* F: _Is it better to have many false positives, or too many false negatives?_
  * \([See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)\)
* F: _How can a standard_ $$2 \times 2$$ _confusion matrix be enhanced for a multi-classification case?_ 
* F: _What is an imbalanced dataset in classification?_ ⭐
  * A classification data set where class proportions are skrewed. A class is called majority class, if it makes up a large proportion of the data set. Classes that make up a small proportion are called minority classes. [\(see here.\)](https://developers.google.com/machine-learning/data-prep/construct/sampling-splitting/imbalanced-data)
* F: _How do you deal with imbalanced data in classification?_
  * _An effective way to treat imbalanced data is to downsample and upweight the majority class._ 
  * _Downsampling means training on a disproportionaly low subset of the majority class examples._
  * _Upweight means adding an example weight to the downsampled class equal to the factor by which you downsampled._ [\(see here.\)](https://developers.google.com/machine-learning/data-prep/construct/sampling-splitting/imbalanced-data)
  * Alternative: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* F: _When classifying why is it not just sufficient to look at the accuracy?_
  * Accuracy assigns equal costs to false positives and false negatives. 
  * If classes are highly imbalanced a high accuracy can easily achieved with low cost by predicting the majority class.
  * However, if different costs are assigned to every error e. g. low cost for false positives, but high costs for misses, accuracy can't take into account the different costs. [\(see here\)](https://stats.stackexchange.com/a/312783)
* F: _Give an example for True Positive Rates etc.?_ 
  * ![](../.gitbook/assets/matrix.jpg) 
  * [\(see here\)](https://www.answerminer.com/blog/confusion-matrix-explained)
* F: _Why is it a bad idea to evaluate your algorithm on the training set?_ 🧠
  * Training error \(error of learning method on seen data\) is quite different from test error rate, and in particular the former can be quite different from the test error rate, and in particular the former can underestimate the latter.
  * One reason to  use a seperate test set is to avoid overfitting.
* F: _Explain what precision and recall are. How do they relate to the ROC-Curve?_
  * \([see here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)\)
* F: Explain what a ROC curve is.
  * A ROC vurve is a diagnostic tool to investigate a classifier with different threshold values and the effect on the true positive rate and the false positive rate. It allows to select the best parameter combinations of the classification model.
* F: _Draw a ROC curve._
  * ![](../.gitbook/assets/roc-draft-xkcd-style.svg) 
* F: _How can a ROC curve be enhanced to multi-class model?_
  * We plot n number of ROC curves for n classifiers using a One vs. All methodolgy. So for example, ifyou have three classes named $$X$$ , $$Y$$ and Z, another ROC for y classified against X and Z, and the third one of Z classified against Y and X.
* F: _Derive a receiver opterating characteristic \(ROC\) Curve from classification results._
  * \(see exam St. Andrews\)
* F: _Interpret a ROC Curve._ 
  * A  line close to the diagonal indicates the result of a random guess.
  * A perfect classifier would yield a point in the upper left corner at \(0,1\). 
* F: What is AUC?
  * AUC stands for Area under the Curve and measures the entire two-dimensional area underneath the entire ROC curve from \(0,0\) to \(1,1\). \([see here.](https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc)\)
  * It can be seen as the probability that a model ranks a random positive example more highly than a random negative example.
* F: How can AUC be interpreted?
  * AUC ranges from 0 to 1. 
  * A model, that gets alle predictions wrong has an AUC of 0.
  * A value of 0.5 or less indicates that the classifier performs the same or worse than the random model, while an AUC value of 1 implies the perfect classifier. \(Script p. 27\)
  * For test [see here](https://developers.google.com/machine-learning/crash-course/classification/check-your-understanding-roc-and-auc).
* F: _How is the AUC be calculated?_ 
  * AUC is the integral of the ROC curve.
* F: Why is the AUC desirable?
  * AUC is **scale-invariant**. It measures how well predictions are ranked, rather than their absolute values.
  * AUC is **classification-threshold-invariant**. It measures the quality of the model's predictions irrespective of what classification threshold is chosen. \([see here.](https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc)\)
* F: What values can AUC take?
  * Between 0 and 1.
* F: _Are ROC curves / is AUC sensitive to imbalanced data? If yes, how can it be resolved?_
* F: _Accuracy should not be the only criteria when comparing classifiers. Name 4 others._ 
  * Precision
  * Recall
  * True positive rate
  * False positive rate
  * F-measure
  * Kappa Statistic
* F: _How is Kappa statstic defined?_  
  * $$\text { Kappa Statistic }=\frac{\left(P{a}-P{e}\right)}{\left(1-P_{e}\right)}$$ 
  * where TP, TN, FP, and FN are defined in previous questions,  $$P{a}=[(\mathrm{TP}+\mathrm{TN}) / \mathrm{N}]$$, and $$P{e}=[(\mathrm{TP}+\mathrm{FN}] / \mathrm{N}][(\mathrm{TP}+\mathrm{FN}) / \mathrm{N}]$$.
  * TODO: Formel nochmal nachschauen? Diagonale?
  * Fleiss' Kappa enhances Cohens Kappa to more than two raters.
* F: _How can Kappa statistic be interpreted?_ 
  * Kappa statistic is used to test **interrater reliability** between two raters.
  * Cohen's Kappa tells you how much better a classifier is performing over the performance of another classifier randomly guessing according to the frequency of the class.
  * Kappa value interpretation Landis & Koch \(1977\):
    * &lt;0 No agreement 
    * 0 — 0.20 Slight
    * 0.21 — 0.40 Fair 
    * 0.41 — 0.60 Moderate 
    * **0.61 — 0.80 Substantial**
    * 0.81 – 1.00 Perfect
* F: _What are disadvantages of_ $$\kappa$$_?_
  * It's maximal value is not always 1. \([see here](https://de.wikipedia.org/wiki/Cohens_Kappa).\)
* F: _Is Kappa statistic sensitive to imbalanced data?_
  * Cohen's kappa can handle imbalanced data well.
  * $$F_1$$ score
* F: _How is the_ $$F_1$$ _measure defined?_ 
  * $$F_{1}=\frac{2}{\frac{1}{\text { precision}}+\frac{1}{\text { recall }}}=2 * \frac{\text { precision } * \text { recall }}{\text { precision }+\text { recall }}$$ 
* F: _Give an intutition for the_ $$F_1$$ _-measure._
  * _Combined measure of precision and recall to take trade-off into account._
  * $$F_1$$ _is the harmonic mean between precision and recall._
* F: _What values can a_ $$F_1$$ _measure take?_ 
  * $$F_1$$ is at max 1, if precision and recall is perfect.
  * $$F_1$$ is 0, if either precision or recall is 0.
* F: _In which way does the_ $$F_1$$ _-measure improve over simpler measure like accuracy?_
  * $$F_1$$ measure is useful, if costs for false positives or false negatives are different e. g. prediction of illness
  * $$F_1$$ is useful, when data is imbalanced.
  * However, accuracy is easier to interpret. \([see here.](https://deepai.org/machine-learning-glossary-and-terms/f-score)\)
* F. _How to access model performance? Name 4 criteria._
  * Speed 
  * Interpretability
  * Robustness \(ability of the classifier to classify noisy data or data with missing values.\)
  * Scalability \(ability of the classifier to work with large amount of data.\)
* F: _What kinds of datasets are difficult for a linear classifier to correctly classify?_
  * _moon-shaped_
  * _circular or interwoven shapes_

## Cross-Validation

* F: What is commonly understood under resampling methods?
  * Resampling methods involve repeatedly drawing samples from a training set and refitting a model of interest on each sample in order to obtain additional information about the fitted model.
  * One example is Cross-Validation method.
* F: Name important resampling methods.
  * Cross-Validation
    * Validation Set approach / Hold-Out-method
    * K-Fold Cross Validation
    * Leave-One-Out Cross-Validation
    * Purged K-Fold Cross-Validation
  * Bootstrap Resampling.
* F: _Name at least techniques for cross validation._
  * Validation Set approach / Hold-Out-method
  * K-Fold Cross Validation
  * Leave-One-Out Cross Validation
  * Purged K-Fold Cross Validation
* F: _What is the motivation to use resampling methods such as cross validation?_  
  * Better estimates of variablity of fitting a model on different samples of the test data opposed to fitting a model only once on a original training example.
* F: _What are drawbacks of resampling approaches?_ 
  * Computional complexity, as they involve fitting the same statistical method multiple times using different subsets of the training data.
* F: _What is the difference between test and training error?_
  * _The test error is the average error that results from using a statistical learning method to predict the response on a new observation, one that was not used in training the method._
  * _The training error is the average error of a statistical learning method on seen data. It's used to get an unbiased estimate of how good the model does._
  * _Error of the final model on training data is biased, since the data is used to select the model._
  * ![](../.gitbook/assets/model_complexity_error_training_test.jpg) 
  * Model complexity decreases prediction erro until a point \(the bias trade-off\) where we are adding just noise. The train error goes down, but the test error is starting to go up. That's overfitting. One want's to find the model with smallest test error.
* F: What is the difference between variance and bias?
  * **Bias** is the amount that a model's prediction differs from the target due to simplifying assumptions a model makes to approximate a target function. Can be resolved using resampling methods.
  * **Variance** indicates how much the estimate of the target function differs from its expected value. Variance measures the inconsistency of different predictions if different training data is used.
  * If a model is too simple and has few parameters, then it it may have high bias and low variance. For models with many parameters, it has high variance and low bias. 
  * In ML we strike for a low bias and variance.
* F: _What are bias and variance, and what are their relation to modelling data?_
  * [\(See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)\)
* F: _Explain the validation set approach?_ 
  * In this method, the original data is randomly devided into a **train set** and a **validation** or **hold-out set**.
  * The model is fitted on the **training set**.
  * The fitted model is then used to predict the response for observations on the **validation set**.
  * Test error is estimated on the **test set**.
* F: _What is the advantage/disadvantage of  the hold-out method?_
  * _simple \(+\)_
  * Data is often scarce. So we can not afford to set aside test sets \([see here.](http://www.columbia.edu/~mh2078/MachineLearningORFE/ResamplingMethods.pdf)\).
  * Performance on the validation set is a  \(often highly variable\) random variable depending on the data-split into training and validation sets. \(-\)
  * In the validation approach, only a subset of the observations those that are included in the training set rather than in the validation set are used in fitting the model \(-\)
  * The error on the validation set tends to over-estimate the test-error rate on small data sets. \(-\)
  * TODO: letzten Punkt verstehen ist damit 70
* F: _Explain_ $$k$$_-fold cross-validation._ 
  * k-fold cross validation randomly devides data into $$K$$ equal-sized parts.
  * We leave out part $$k$$ , fit the model to the other $$K-1$$ parts \(combined\), and then obtain predictions for the left-out $$k$$ -th part.
  * This is done in turn for each part $$k = 1,2, \cdots, K$$, and then the results are combined.
* F: _Explain the Leave-One-Out Cross-Validation._ 
  * Leave -One-Out validation divides data into $$K$$ parts with $$K=N$$. That means every single observation used to test the the model.
  * We leave out part $$k$$ , fit the model to the other $$N-1$$ parts \(combined\), and then obtain predictions for the left-out $$k$$ -th part.
  * This is done in turn for each part $$k = 1,2, \cdots, N$$ , and then the results are combined.
* F: _What is the advantage/disadvantage of_ $$k$$_-fold CV?_
  * Very little bias, as model has been train on multiple data constellations. \(+\)
  * Computionally very expensive, as training of the model happens multiple times \(-\)
  * Can not prevent data leakage \(-\)
* F: _Explain purged_ $$k$$_-fold cross-validation._ ⭐
  * Purged K-Fold
* F: _What is the motivation to perform **purged**_ $$k$$_**-Fold Cross Validation.**_ 
  * Observations can e. g. in finance often not assumed to be drawn from an IID process. Leakage takes place when the training set contains information that also appears in the testing set. \(see e. g. stock quotes, where market information is priced in from the previous days\)
  * One way to reduce leakage is to purge from the trainig set all observations whose labels overlap in time with those labels included in the testing set. 
* F: How does purged $$k$$-Fold Cross validation work?
  * de Padro describes it[ here.](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3257420) Consider a label $$Y_{j}$$ that is a function of observations in the closed range $$t \in\left[t_{j, 0}, t_{j, 1}\right], Y_{j}=f\left[\left[t_{j, 0}, t_{j, 1}\right]\right]$$ .
  * For example, in the context of the triple barrier labeling method, it means that the label is the sign of the return spanning between price bars with indices $$t{j, 0}$$ and $t{j, i}$, that is $\operatorname{sgn}\left\[r{t{j, 0}, t{j, 1}}\right\]$. 
  * A label $Y{i}=f\left\[\left\[t{j, 0}, t{j, 1}\right\]\right\]$ overlaps with $Y\_{j}$ if any of the three sufficient conditions is met:

    $$
    t_{j, 0} \leq t_{i, 0} \leq t_{j, 1} ; t_{j, 0} \leq t_{i, 1} \leq t_{j, 1} ; t_{i, 0} \leq t_{j, 0} \leq t_{j, 1} \leq t_{i, 1}
    $$
* F: What is the motivation vor embargoed K-Fold CV?
  * Since financial features often include series that exhibit serial correlation \(like ARMA\) processes, we should eliminate from the training set observations that immediately follow an observation in the testing set. This process is called embargo. [\(see here.\)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3257420)
  * ![](../.gitbook/assets/purged_embargo_cv.png) 
* F: _How should we divide data into training and testing for a time series dataset?_ ⭐
  * When choosing models, it is common practice to separate the available data into two portions, training and test data, where the training data is used to estimate any parameters of the forecasting method and the test data is used to evalute its accuracy. The test set is typically about 20% of the total sample. \([see here.](https://otexts.com/fpp2/accuracy.html)\)
  * For time series a cross-validation using a rolling window approach is commly used. That means, a small subset of consecutive data serves for **training,** forecasting the **consecutive** data points, that are part in **the test set**. As the training set only includes observations prior to the observations in the test set, no future observations are used for forecasting. The same forecasted data points are then included as part of the next traing dataset and subsequent data points are forecasted. \([see here.](https://medium.com/@soumyachess1496/cross-validation-in-time-series-566ae4981ce4)\) \([see here.](https://otexts.com/fpp2/accuracy.html)\)
  * Sometimes a separate validation set to tune the hyperparameters of the model is used.
  * ![](../.gitbook/assets/grafik%20%2843%29.png) 
  * Blue Points are used for training red points are used for testing.
  * **Note:** Sketch in lecture looks different. However, it's not clear, what's the difference between the blue and green dots. Probably train and validation set.
* F: _Explain what bootstrap is._ 
  * Bootstrap is a flexible and powerful statistical tool can be used to quantify the uncertainty with a given estimator or statistical learning method. \([see here.](http://www.columbia.edu/~mh2078/MachineLearningORFE/ResamplingMethods.pdf)\)
  * Bootstrap relies on resampling the data many times to compute some measure of variability.  Sample data is repeatedly drawn with replacement from a data source to estimate a population parameter. \([see here.](https://datamites.com/blog/resampling-methods-in-machine-learning/)\)
  * The bootstrapped data sets are the same size as the original data set. That's why some observations appear more than once in a given boot strap data set or not at all. 
* F: _Why is bootstrapping used? Why is bootstrapping desirable?_ 
  * It's used, if analytic measures of variability are not available \(or not automatically output by statistical software\) 
  * Large scale resampling can be easily done on modern computers \(+\) \([see here.](http://www.columbia.edu/~mh2078/MachineLearningORFE/ResamplingMethods.pdf)\)
  * Bootstrapping doesn't assume a parametric distribution \(+\) \([see here.](https://stats.stackexchange.com/questions/280725/pros-and-cons-of-bootstrapping/280728)\)
  * A bootstrap sample can only tell about the original sample, but won't give any insights on the real population. \(-\) \([see here.](https://stats.stackexchange.com/questions/280725/pros-and-cons-of-bootstrapping/280728)\)
* F: _How should we tune parameters for machine learning models?_ ⭐
  * Hyper parameter tuning should happen using validation set which is solely used for tuning different mdoels / hyperparameters.
  * Testing should still happen on the testing set and training on the training set.
  * To find the best parameter combinations a systematic approach such as grid search should be used.
  * If grid search is not possible for computational reasons a randomized search might help.
* F: Compare the Hold out Validation, to Leave-One-Out Cross-Validation, $$k$$ -Fold Cross Validation and Bootsrap.
  * Adapted from [here](https://datamites.com/blog/resampling-methods-in-machine-learning/).

    | **Hold out Validation** | **Leave-One-Out Cross-Validation** | **k-Fold Cross-Validation** | **Bootstrap** |
    | :--- | :--- | :--- | :--- |
    | Use it when data have less features | Medium sized dataset | Large dataset with large features | Use it with any shape of data |
    | High chance of bias | Less bias | Good bias and variance tradeoff | Good bias and variance tradeoff |
    | High chance of overfitting | Generalized model | Generalized model | Generalized model |

## Shrinkage Methods

* F: _Explain how forward stepwise selection works in 3 steps._ 
* F: _Explain how backward stepwise selection works in 3 steps._ 
* F: _Compare the subset selection methods forward and backward stepwise selection._ 
* F: _When is it desirable to use backward stepwise selection and when is it desirable to use forward stepwise selection?_ 
* F: _What is an alternative to subset selection methods?_ 
* F: _What are the reasons why shrinkage methods such as LASSO are preferred over subset selection methods such as forward stepwise selection?_
* F: _Compare the stepwise inclusion regression method to stepwise exclusion regression method and standard stepwise regression method._ 
* F: _Explain how the stepwise inclusion regression method / ... /... works._ 
* F: _In which way do stepwise inclusion method and stepwise exclusion method differ?_
* F: _Explain what regularization is and why it is useful_
  * A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* F: _Explain the ridge regression._ ⭐
  * Ridge regression is a regularization approach. Regularization is used to prevent coefficients from fitting so perfectly. This is done by adding a constant multiple to an existing weight vector. Which is sometimes referred to as a regularization term or shrinkage penalty. In case of ridge regression this regularization term. In case of ridge regression it is the sum of the square of the weights.
  * Taking this into account one get's the following formula for ridge regression:

$$
\sum_{i=1}^{n}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} \beta_{j} x_{i j}\right)^{2}+\lambda \sum_{j=1}^{p} \beta_{j}^{2}=R S S+\lambda \sum_{j=1}^{p} \beta_{j}^{2}
$$

* * where $$\lambda \geq 0$$ is a tuning parameter, to be determined separately. The tuning parameter $$\lambda$$ serves as control of the relative impact of these two terms on the regression coefficients. Should be selected using cross-validation.
  * The **shrinkage penalty** is small when $$\beta_1,\cdots, \beta_p$$ are close to zero, and so it has the effect of shrinking the estimates of $$\beta_j$$ towards zero.
  * As such:
    * ridge regression yields non-sparse outputs, as coefficients are shrinked towards zero but never actually are 0.
    * doesn't allow for feature selection. Some reasoning as above.
    * Typically yields better results than LASSO.
* F: _Explain LASSO._
* F: _Explain the difference between LASSO and ridge regression?_ ⭐
  * Both are regularization approaches in order to prevent overfitting of an ordinary linear regression model and introduce smoothness to the model. This is done by adding a constant multiple of an weight vector that prevents the coefficients so perfectly that they overfit.
  * Both shrinkage methods to shrink regression coefficients towards zero.
  * The difference between LASSO and ridge regression is that ridge is just the square of the weights, while Lasso is just the sum of the absolute weights in MSE or other loss functions.
  * LASSO:

$$
\underset{\beta}{\operatorname{minimize}} \sum_{i=1}^{n}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} \beta_{j} x_{i j}\right)^{2} \quad \text { subject to } \quad \sum_{j=1}^{p}\left|\beta_{j}\right| \leq s
$$

* Ridge regression:

$$
\underset{\beta}{\operatorname{minimize}} \sum_{i=1}^{n}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} \beta_{j} x_{i j}\right)^{2} \quad \text { subject to } \quad \sum_{j=1}^{p} \beta_{j}^{2} \leq s
$$

* The main difference is, that when doing a subset selection, which will generally select models that involve just a subset of the variables, ridge regression will include all $$p$$ predictors in the final model. However LASSO helps to zero-out coefficients and can yield sparse feature spaces. Whereas ridge regression yields non-sparse outputs and can not be used for feature-selection straight away.
* However in practice ridge regression performs better than LASSO. [\(See here.\)](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* ![](../.gitbook/assets/grafik%20%2828%29.png) 
* F: _In practice, explain what is the main difference between ridge regression and LASSO._ ⭐
  * Both are regularization approaches in order to prevent overfitting of an ordinary linear regression model and introduce smoothness to the model. This is done by adding a constant multiple of an weight vector that prevents the coefficients so perfectly that they overfit.
  * Both shrinkage methods to shrink regression coefficients towards zero.
  * The difference between LASSO and ridge regression is that ridge is just the square of the weights, while Lasso is just the sum of the absolute weights in MSE or other loss functions.
* F: _Explain what is the difference between linear regression and LASSO?_ \(8 points\)
  * The formula for **linear regression** is given by:

$$
\min _{\boldsymbol{\beta}} \sum_{i=1}^{N}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} x_{i j} \beta_{j}\right)^{2}
$$

* where $$\beta_0$$ is the intercept and $$\beta_1 \cdots beta_p$$ are regression coefficients of $$k$$ independent variables.
* The formula for **LASSO** coefficients $$\hat{\beta}_{\lambda}^{L}$$ is given by:

$$
\arg \min _{\mathbf{\beta}} \sum_{i=1}^{n}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} \beta_{j} x_{i j}\right)^{2}+\lambda \sum_{j=1}^{p} \mid \beta_{j} \mid
$$

* Where $$\lambda$$ is a tuning parameter that serves as control of the relative impact of these two terms on the regression coefficients.
* As it can be seen above, linear regression is the most basic form. LASSO includes another term - the so called regularization term or shrinkage penalty. More on that later. The standard linear regression doesn't penalize for the choice of weights and doesn't include a regularization term.
* One could say LASSO is a variant of Linear regression. And linear regression is in general no variant of LASSO.
* Linear regression tries to estimate the coefficients as such, that the residual sum of squares $$(\beta_0 + ...)$$ is minimized.
* This also means that linear regression learns the training heart and is prone to overfitting. LASSO, which is a regularization approach, tries to prevent overfitting through the introduction of regularization term, which prevents the coefficients so perfectly to overfit.
* Another difference is that LASSO is a shrinkage method and can be used for variable selection. Whereas linear regression is not suitable for feature selection.
* For both closed form solutions exist.
* F: _What are the main applications of LASSO?_⭐
* LASSO is suitable for feature selection, as some coefficient estimates are forced exactly to zero, if the tuning parameter $$\lambda$$ is sufficiently large.
* Whenever sparse models models \(models that only include a subset of the variables\) are needed.
* F: _Explain stability selection technique. What is the main advantage of stability selection technique compared to LASSO?._⭐
  * With LASSO regression the variables selected can change even if data is ever-so-slightly changed. Stability selection technique leads to a more stable selection of variables than LASSO.
  * Stability selection works by fitting variables on a subsample of data. Afterwards one can count the proportion of times a variable is selected. This leads to a more stable selection.
* F: _How do we apply the kernel trick to ridge regression?_ 🧠
* F: _Why does it make sense to penalize the norm of the weight vector?_ 🧠
* F: _Which norms can we use and what are the different effects?_ 🧠
* F: _Give the formula for ridge regression and explain its components._
* F: _Give the formula for LASSO and explain its components._
* F: _Name one major advantage of LASSO over ridge regression._
* A: Lasso yields sparse models, that is, models that only involve a subset of other variables.
* F: _How should_ $$\lambda$$ _be selected for ridge regression / LASSO?_
* F: _Explain how selecting tuning parameters works for ridge regression._

## Dimensionality Reduction

* F: _What are the advantages of sparse PCA over PCA?_⭐
  * sparse PCA allows for a better interpretation of economic meaning of each principal component. When having a large number of variables with non-zero factor loadings it's hard to interpret them with ordinary PCA, as PCs are a linear combination of all $$p$$ variables.
  * Compared to SCoTLASS its computationally efficient.
* F: _Intuition about sparse principal component analysis?_
  * SPCA is built on the fact that PCA can be written as a regression-type optimization problem, with a quadratic penalty; the lasso penalty \(via the elastic net\) can then be directly integrated into the regression criterion, leading to a modifiedPCA with sparse loadings.
* F: _What does dimensionality reduction mean?_ 🧠
* F: _What is PCA?_ 🧠
* F: _What are three things, that PCA does?_ 🧠
* F: _What are the roles of the Eigenvectors and Eigenvalues in PCA?_ 🧠
* F: _Can you describe applications of PCA?_ 🧠
* F: _Give the definition for PCA_
* F: _Explain the ordinary PCA._
* F: _Explain the sparse PCA._
* F: _Explain the nonlinear PCA._
* F: _Explain the kernel PCA._
* F: _Explain the major difference of sparse PCA over ordinary PCA._
* F: _Explain the major difference of non-linear PCA over ordinary PCA._
* F: _Explain the major difference of kernel PCA over ordinary PCA._
* F: _Give applications for PCA._
* F: _Compare supervised learning to unsupervised learning. How do they differ?_
* F: _What are advantages / disadvantages of unsupervised learning techniques?_
* F: _What is PCA commonly used for?_
* F: _How can the proportion of variance explained by_ $$m$$ _variables be calculated?_
* F: _Calculate the PCA for the first 2 components?_
* F: _Sketch the algorithm for calculating the first two PCA components._

## Decision Trees

* F: _Explain what a decision tree is._
  * A decision tree is a supervised learning algorithm that can be used used for regression and classification. 
  * Decision Trees try to predict the class or a value of the target by stratifying or segmenting the predictor space into a number of simple regions.
  * There are several measures to learn these splitting rules required for splitting data in a node into separate node. One of them is the Entropy.
* F: _Mention three characteristics of impurity measures?_ ⭐
  * resubstitution error
  * Gini-Index
  * Entropy
* F: _What is the intutition behind an optimal split in a decision tree?_
  * A split should lead to a subset that contains predominantly cases of one class.
  * That means nodes should only contain cases of a single class only or homogenous.
* F: _Name 3 conditions an impurity measure has to fulfil._
  1. _An impurity measure of a node should be at a maximum when the observations are distrbuted evenly over all cases in that node, i. e. at:_ $$\left(\frac{1}{J}, \frac{1}{J}, \ldots, \frac{1}{J}\right)$$ 
  2. An impurity measure of a node should be at minium when all observations belong to a single class in that node, i. e. at $$(1,0, \cdots, 0),(0,1,0, \cdots, 0), \cdots,(0,0, \cdots, 1)$$ 
  3. $$\phi$$ is a symmetric function of $$p_{1}, \ldots, p_{J}$$.
* F: _How can we influence the model complexity of the tree?_ 🧠
* F: _Compare the Gini-Coefficient to Entropy and the resubstitution error._
  * **Resubstitution Error:** $$i(t)=1-\max _{j} p(j \mid t)$$, where where $$p(j \mid t)$$ is the relative frequency of class $$j$$ in node $$t$$.
  * **Gini-Index:** $$i(t)=\sum_{j} p(j \mid t)(1-p(j \mid t))$$
  * **Entropie:** $$i(t)=-\sum_{j} p(j \mid t) \log p(j \mid t)$$
    * ![](../.gitbook/assets/grafik%20%2845%29.png) 
* F: _When should the Gini-Coefficient be used? When is it desirable to use the Entropy? How does the missclassification error compare?_
  * From Hastie p. 309 f.: Cross Entropy and Gini index are differntiable, and hence more amenable to numerical optimization as setting equal with 0 is possible.
  * Gini index and cross-entropy are more sensitive to changes in the node prabilites than the missclassifciation rate. For example, in a two-class problem with 400 observations in each class \(denote, this by \(400,400\)\), suppose one split created nodes \(300,100\) and \(100, 300\), while the other created nodes \(200, 400\) and \(200,0\). Both splits produce a misclassification rate of 0.25, but the second split produces a pure node and is probably preferable. Both the Gini index and cross-entropy are lower for the second split.
  * That means either Gini index or cross-entropy should be used when growing a tree.
  * To guide cost-complexity pruning, any of the three measures will do.
* _F: Explain how numerical features can be split?_
  * If  $$x_{1}, x_{2}, \ldots, x_{p}$$ are a set of numeric variables, we consider all splits of type $$x \leq c$$ for all $$c$$ ranging over $$(-\infty, \infty)$$.
  * If all all observations have a different value, we have at most n distinct values $$x_{1}, x_{2}, \cdots, x_{n}$$ of $$x$$. Which means there are at max. $$n-1$$ distinct splits of type $$m=1, \ldots, n \leq n$$, where $$m=1, \ldots, n \leq n$$ , where $$c_m$$ are taken **halfway** between **consecutive** distinct values of $$x$$ .
* F: _How can continuous attributes be handled in Decision Trees?_ ⭐
  * Assume  $$x_{1}, x_{2}, \ldots, x_{p}$$ are a set of numeric variables. If x is categorical, taking values in $$V(x)= \{ b_{1}, b_{2}, \cdots, b_{L} \}$$ , we consider all splits of type $$x \in S$$ , where $$S$$ is any non-empty proper subset of $$V(x)$$.
  * If every categorical variable x with L distinct values there are at max. $$2^{L-1}-1$$ splits. 
  * Alternatively, variables can be label-encoded and treated as numeric variables. \([see here.](https://towardsdatascience.com/decision-trees-d07e0f420175)\)
* Alternative answerIt's necessary to discretize continuous values. One could either use:

  1. Comparison operator, which separates into two classes by a threshold. Threshold could be chosen by:
     1. brute force: trying out every single value of continuous variables
     2. sorting values for continuous attributes and taking the midpoint of the adjacent values in the sorted array. See here:
     3.  ![](../.gitbook/assets/grafik%20%2847%29.png) 
  2. Split continuous values into bins. One would get multi-way splits. Splitting into bins could happen by frequency or width. \(comp. Equi-width histograms vs. equi-depth histogram\) [\(see here.\)](https://medium.com/geekculture/handling-continuous-attributes-in-decision-trees-bbc044986621)

* F: _Explain how numerical features can be split?_
  * Assuming there are at most n distinct values of x. There are at most n-1 distinct splits of type $$x \leq c_m$$, where $$c_m$$ are taken halfway between consecutive distinct values of $$x$$ 
* F: _What is the motivation to prune a decision tree?_
  * Pruning is done to to avoid overfitting. The tree learns the data by heart, but new data can very slightly differ. There fore, it makes sense to cut back the tree to deliver good results on unseen data.
  * Pruning reduces the size of a decision tree by removing unrelevant attributes from the tree / cutting back the tree. \(AGD\) 
  * A smaller tree with fewer splits might lead to lower variance and better interpretation at the cost of a little bias.
* _F: How does pruning a using minimal-cost complexity decision tree works?_
  * A very large tree $$T_0$$ is grown and then cut back afterwards.
  * Since the tree can be tested while cutting it down it could lead  to favourable results. 
  * It defines the a measurement called cost-complexity measurement, for a dataset X and a tree T where \|T\| defines the amount of terminal nodes:
  * $$
    \sum_{m=1}^{|T|} \sum_{x_{i} \in R_{m}}\left(y_{i}-\hat{y}_{R_{m}}\right)^{2}+\alpha|T|
    $$
  * $$\alpha$$ is a non-negative tuning parameterand is called the complexity parameter. $$R_m$$ ist the rectangel \(i. e. the subset of predictor space\) coressponding to the m-th terminal node, and $$\hat{y}{R{m}}$$ is the mean of training observations in $$R_m$$ .
  * $$\alpha$$ is usually selected using cross-validation.
  * When pruning the tree the algorithm tries to minimize this measure. Its obvoius that a large number of nodes in a subtree is punished for a high value of $$\alpha$$. Therefore the algorithm will search for subtrees with high missclassification error or high number of nodes. Of course it is complicated looking at the number of nodes since it is heavily dependent on the number of attributes in $$T$$. Hence there has to be the parameter $$\alpha$$ in order to finde the right punishment for large tree sizes.  [\(see here.\)](https://www5.in.tum.de/lehre/seminare/datamining/ss17/paper_pres/08_decision_tree/paper.pdf)
* F: _Explain how growing a decision tree works?_
  1. At each node, "split the data into two leaf nodes
  2. Splits are chosen using a binary splitting criterion e. g. cross-entropy.
  3. We stop when each terminal node has fewer than some minimum nuber of observations.
  4. Alternatively: Algorithm on page 27. But emphasis is on **building**?
* F: _How can decision trees be applied to a regression case?_
  * The predicted value of a node is the average response variable for all observations in that node.
* F: _Name several advantages / disadvantages of decision trees_
  * Easy to interpret, if trees are small.
  * Competitive in terms of accuracy.
  * Inexpensive to construct.
* F: _What are advantages of decision trees over random forests?_ ⭐
  * easier to explain \(+\) 
  * computionally simpler and quicker to fit than random forests \(+\)
  * less robust than random forests. If we change the data for a decision tree a little, the tree can change a lot. Interpretation is not as straightforward as it seems. \(-\)
  * Most of the times random forests achieve a better accuracy, as they are trained on  random sub samples. This however comes at the expense of loss interpretation.
* _F: What are tuning parameters for Decision Trees?_

## Bagging, Boosting and RF

* F: _What ensemble techniques can be applied?_
  * _Bagging_ 
  * _Boosting_
  * _Random Forests_
* F: _What is an ensemble algorithm?_ 
  * Ensemble methods are meta-algorithms that combine several machine learning techniques into one predictive model in order to decrease variance \(**bagging**\), bias \(**boosting**\) or  improve predictions \(**stacking**\). \([see here.](https://blog.statsbot.co/ensemble-learning-d1dcd548e936)\)
* F: _Explain what Bagging is._
  * Bootstrap aggregating or bagging is an ensemble technique  designed to improve stabilty and accuracy of ML algorithms for classification and regression.
  * In the regression case bagging fits a $$\hat{f}_{b}(x)=\hat{\beta}_{b} X_{b}$$ regression model to $$b$$-th bootstram stamples $$X_b$$ and then bagging takes the mean of these estimation over a collection of boostrap samples. The bagging estimator is made in the following form:
  * $$f_{\text {Bagging }}(X)=\frac{1}{B} \sum_{b=1}^{B} \hat{f}_{b}(X)$$
* F: _How does Bagging work for regression?_
  * Each bootstrap regression tree will include different nodes. The bagging estimator is the **mean** of these $$B$$ regression tree predictions.
* F: _How does Bagging work for classification?_
  * For each test observation we record th class predicted by each of the $$B$$ trees, and take a **majority vote**. That means the overall prediction is the most commonly occurring class among the  $$B$$ predictions.
* F: _What are tuning parameters for Bagging?_
  * The number of bootstrap samples / regression treess over which the mean or majority vote is estimated.
* F: _Explain the intution of Boosting._
  * Boosting tries to improve predictive performance by combining several weak learners \(e. g. simple trees\) which are trained sequentially on the data. The error is analysed. In every step consecutive weak learners are fitted, so that the accuracy is increased. \([see here.](https://analyticsindiamag.com/primer-ensemble-learning-bagging-boosting/)\)
* F: Explain, how Boosting works in natural language.
  * Boosting is used to create a collection of predictors.  In this technique, learners are learned sequentially with early lerners fitting simple models to the data and then anlyse data for errors. Consecutive trees \(random sample\) are fit at every step, the goal is to improve the accuracy of the prior tree \([see here](https://analyticsindiamag.com/primer-ensemble-learning-bagging-boosting/).\)
* F: _How does Gradient Boosting work?_
  * Assume we seek to fit a gradient boosting model to the $$\left(X_{1}, y_{1}\right),\left(X_{2}, y_{2}\right), \ldots,\left(X_{n}, y_{n}\right)$$, where $$X_{i}$$ are the explanatory variables for the $$i^{\text {th }}$$ sample and $$y_{i}$$ is its dependent variable. 
  * In the first step, using gradient boosting we fit a base learner $$f_{0}(X)$$ for modeling. We define the corresponding prediction residuals for first regression tree $$e_{i 0}=y_{i}-f_{0}\left(X_{i}\right)$$ for $$i=1,2, \ldots, n$$ . 
  * In the next step, a regression tree $$f_{1}\left(X_{i}\right)$$ to $$\left(X_{1}, e_{10}\right),\left(X_{2}, e_{20}\right), \ldots,\left(X_{n}, e_{n 0}\right)$$ is fit, and a recovery rate prediction will be equal to $$f_{0}\left(X_{i}\right)+e_{i 1}$$. Here $$e_{i 1}$$ is the corresponding predicted residuals from $$f_{1}\left(X_{i}\right)$$. The gradient boosting estimation after $$B$$ iterations is defined as:

    $$
    \widehat{y}_{i}=f_{0}\left(X_{i}\right)+\sum_{b=1}^{B} e_{i b}
    $$

    Different loss functions such as least-squares and least absolute deviation can be used with the gradient-boosting methodology.

  * The loss function depends on whether gradient boosting is done for a classification case or a regression case.
    * For regression trees squared error is commonly used 
    * For classification logarithmic loss is used. \([see here.](https://machinelearningmastery.com/gentle-introduction-gradient-boosting-algorithm-machine-learning/)\)
* F: _What are tuning parameters for Boosting?_ ⭐
  * **number of trees** $$B$$. Unlike bagging and random forests, boosting can overfit if $$B$$ is too large, although this overfits tends to occur slowly if at all. We use cross-validation to select B.
  * The **shrinkage parameter** at which boosting learns. Typical values are 0.01 or 0.001 and the right choice depends on the problem. Very small shrinkage parameter can require using a very large value of B in order to achieve good performance.
  * The **number of splits** $$d$$ in each tree, which controls the complexity of the boosted ensemble. Often $$d=1$$ works well, in which case each tree is a stump, consisting of a single split resulting in an additive model. More generally d is the interaction depth, and controls the interaction order of the boosted model, since d splits can invole at most $$d$$ variables.
* F: _How does Bagging differ from Boosting? Explain the difference._
  * **Bagging:** 
    * Goal is achieve minimum variance
    * Bagging combines the results of multiple models to a generalized result trough voting or averaging. 
    * The trees are built in parallel on bootstrap samples, which is data chosen with replacement from the original data.
    * Equal weight is given to all models
  * **Boosting:** 
    * Goal is to increase accuracy / decrease bias 
    * Boosting is a sequential process, where each subsequent model attempts to correct the errors of the previous model. That means succeeding models are dependent on previous models \([see here.](https://medium.com/swlh/difference-between-bagging-and-boosting-f996253acd22)\)
    * Weights a model's contribution by its performance.
  * Visualization:
    * ![](../.gitbook/assets/grafik%20%2846%29.png) 
* F: What are similarities between bagging, random forests and boosting algorithms.
  * Like random forests, boosting algorithms are an ensemble of many different models with high inter-group diversity.
  * Boosting algorithms allso aggregate the predictions of each constituent model into an overall predicition. 
  * Both algorithms make use of tree models. However, Boosting can also combine other weak learners. \([see here.](https://medium.com/@toprak.mhmt/gradient-boosting-and-weak-learners-1f93726b6fbd)\)
* F: _What is the main advantage and disadvantage of a random forest over a decision tree?_ ⭐
  * A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* F: _Compare Boosting trees to Random Forests. What are the differences?_
  1. random forest algorithm uses a **small random subset** of explanatory variables for growing in each particular tree while boosting selects from a **complete list of explanatory** **variables** for growing the best classification tree.
  2. Boosting trees sequentially depend on the error rate of the previous iteration, while random trees can be built independently at each iteration.
  3. In random forests each tree is a strong learner. They would do just fine as a decisioin tree on their own. In boosting algoirthms, trees are artificially limited to very shallow depth \(usually only one split\), to ensure that each model is only slightly better than random chance. \([see here](https://medium.com/@toprak.mhmt/gradient-boosting-and-weak-learners-1f93726b6fbd).\)
* F: _Explain what a Random Forest is?_
  * A random forest is an **advanced variant of bagging**.It fits a large set of classfication trees, and then classifies using the majority of the classes of  built clasification trees. 
  * Random forests use a small **random subset of explanatory variables** for growing in each particular tree.
* F: _When can it be advantageous to use Random Forests over Decision Trees?_
  * _Better accuracy \(+\)_
  * _Reduced variance \(+\)_
  * _More difficult to interpret \(-\)_
* F: _What are tuning parameters for Random Forests?_
  * Number of trees
  * Number of predictors used to build each tree
* _F: Give on example for an ensemble algorithm from the class of an ensemble model that gave improved performance over a base model._
  * random forests and boosting used to predict defaults for commercial  real estate property loans.

## k-means Clustering

* F: _Explain the_ $$k$$_-means clustering algorithm_ ⭐

  1. Randomly assign a number, from $$1$$ to $$K$$ to each of the observations. These serve as initial cluster assignments for the observations. 
  2. Iterate until the cluster assignments top changing:
     * for each of the $$K$$ clusters, compute the cluster centroid. The $$k$$th cluster centroid is the vector of the $$p$$ features means for the observations in the $$k$$th cluster.
     * Assign each observation to the cluster whose centroid is closest \(where closest is defined using Euclidean distance\).

  To achieve a faster convergence, one can use an improved initialization of cluster centres. One approach is **k-means++**.

  More formal definition: 

  1.  Pick $$K$$ arbitrary cluster centers 
  2. Assign each sample to its closest centroid $$z_{n}=\arg \min {k}\left|\boldsymbol{c}_{k}-\boldsymbol{x}_{n}\right|^{2}$$ 
  3. Adjust the centroids to be the means of the samples assigned to them $$\boldsymbol{c}_{k}=\frac{1}{\left|X_{k}\right|} \sum{\boldsymbol{x}_{i} \in X_{k}}  \boldsymbol{x}_{i}, X_{k}= \{\boldsymbol{x}_{n} z_{n}=k \}$$ 
  4. Goto step 2 until no change

* F: What properties do sets of Clusterings satisfy?
  * Each observation belongs to at least to one of the$$K$$clusters.
  * The clusters are non-overlapping, no observation belongs to more than one cluster.
* F: _What is the main idea of clustering?_
  * The idea behind $$k$$-means clustering is that a good clustering is one for which the within-cluster variation is as small as possible.
  * $$\operatorname{WCV}(C_k)$$ is the degree by which observations differ from each other within a cluster.

    Hence we want to solve the problem: 

    * $$\operatorname{ minimize }\left\{\sum_{k=1}^{K} W C V\left(C_{K}\right)\right\}$$

    For Euclidean distance: 

    * $$\operatorname{ minimize }\left\{\sum_{k=1}^{K} \frac{1}{\left|C_{K}\right|} \sum_{i, i^{\prime} \in C_{K}} \sum_{j=1}^{P}\left(x_{i j}-x_{i^{\prime} j}\right)^{2}\right\}$$
* F: _What is the main \(dis-\)advantage of the_ $$k$$_-means clustering algorithm?_ ⭐
  * Works in an unsupervised setting / doesn't require labelled data \(+\)
  * Relatively simple to implement \(+\)
  * Scales to large data sets \(+\)
  * Guarantees convergence \(+\)
  * warm-start the positions of centroids possible \(+\)
  * easily adapts to new examples \(+\)
  * generalize the clusters of different shapes and sizes, such as elliptical clusters. [\(see here.\)](https://developers.google.com/machine-learning/clustering/algorithm/advantages-disadvantages)
  * $$k$$-means clustering requires us to pre-specify the number of clusters. However no of clusters is often not known \(-\)
* F: _What properties does a set has to fulfil when_ $$k$$_-means clustering should be applied._
  * Datasets with less noise
  * Spherical clusters of roughly the same size
  * Counter "mouse" example \([see here.](https://stats.stackexchange.com/questions/79741/data-sets-suitable-for-k-means)\)
  * \_\_![](../.gitbook/assets/grafik%20%2848%29.png) __
* F: _What are alternatives to_ $$k$$_-means clustering?_
  * DBSCAN
  * Agglomerative Hierarchical Clustering
  * Birch \([see here.](https://towardsdatascience.com/the-5-clustering-algorithms-data-scientists-need-to-know-a36d136ef68) / AGD\)
* F: _How does minimizing the WCV relate to solving the clustering problem?_
  * \_\_
* F: _Name distance measures, that can be used with in conjunction with_ $$k$$ _means. When should they be used._
  * _Euclidean distance_
  * _Manhatten distance_
  * _Average distance_
  * _Minkowski sum \(_[_see here\)_](https://storage.googleapis.com/plos-corpus-prod/10.1371/journal.pone.0144059/1/pone.0144059.pdf?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=wombat-sa%40plos-prod.iam.gserviceaccount.com%2F20210715%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20210715T194736Z&X-Goog-Expires=86400&X-Goog-SignedHeaders=host&X-Goog-Signature=04ede785d000ebd5f299bfbbab8c90d6eadccd88325d10335ed298244a0ecf7a930ab527d0c521cf7a014d40565bdaeec1721d2a96b9a8c02025c5a2d02a8c5cb315c9241feeff1e3e2e5faa8fb0d7df7a4093901e580a4454e37c51a1c63487e1cfdbb86243603498f00b69a242f76ee0ddb744f9e2555e15627fd23febc4dbac8107aa0ffef08b59a1923f71f8c214347c481256c4a769c830868d160f1cdb2fe75b8af9458875ec5a441e93729bb2896ced623dec5be33f41346fcef8188f47e8e3efe87c3424bfe2a3bac0a3446788d38c091052835476328901902840be36576b9b327ae8d12aebd783be1dafaefc5a5edf41a88d7280f23c90a8b80768)\_\_
* F: _What are the 2 main steps of_ $$k$$_-means?_ 🧠
  * Pick $$k$$ arbitrary cluster centers
  * Assign each sample to the closest cantroid and adjust the centroids to be the means of the samples assigned to them.
* F: _Why does_ $$k$$_-means converge? What is it minimizing._ 🧠
  * We have only a finite number of possible values for the centroid.
  * Every assignment or adjustment step is reducing the SSD or remains constant.
  * TODO: More detailled in ML slides.
* F: _Does_ $$k$$_-means find a global minimum of the objective?_ 🧠
  * No, the objective \(see question above\) is an NP-hard problem, so we can't expect any algorithm to minimize the cost without essentially checking \(near to\) all assignments.
  * It heavily depends on the initialisation of the centroids.
* F: _How is the clustering problem defined?_ 🧠
  * 
* F: _Why is clustering called unsupervised?_ 🧠
  * Clustering is an unsupervised machine learning task that automatically devides the data into clusters, or groups of similar items. It does this without having been told how the groups should look ahead of time. As we may not even know what we're looking for, clustering is used for knowledge discovery rather than prediction. \([see here](https://hub.packtpub.com/introduction-clustering-and-unsupervised-learning/).\)
* F: _How do clustering methods work? What is the rule of the cluster-2-cluster distance and which distances can we use?_  🧠
  * 
* F: _Name similarity measures. \(Name an advantage and disadvantage for each of them.\)_
* F: _Compare similarity measures for low and high-dimensional spaces._
  * \_\_
* F: _In unsupervised learning, if a ground truth about a dataset is unknown, how can we determine the most useful number of clusters to be?_
  * [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* F: _When is a clustering optimal?_
  * A clustering is optimal, if the within-cluster variation \(summed over all Clusters $$K$$\) is a as small as possible.
* F: _Draw a dendrogram from a given clustering._
  *   ![](http://127.0.0.1:50852/paste-adaa6f08036c23cf81befcf5dda658803dcb008b.jpg)

  *   ![](http://127.0.0.1:50852/paste-1510742dce8bacd2cfabfe464bc70dfd6d94ad8e.jpg)

    ![](http://127.0.0.1:50742/paste-1510742dce8bacd2cfabfe464bc70dfd6d94ad8e.jpg)
* F: _Explain how the algorithm for hierarchical clustering works._
  1. Begin with n observations and a measure \(such as Euclidean distance\) of all the $$\left(\begin{array}{c}n \\ 2\end{array}\right)=n(n-1) / 2$$ pairwise dissimilarities. Treat each observation as its own cluster.
  2. For $$i=n, n-1, \ldots, 2$$

  * Examine all pairwise inter-cluster dissimilarities among the $$i$$ clusters and identify the pair of clusters that are least dissimilar \(that is, most similar\). Fuse these two clusters. The dissimilarity between these two clusters indicates the height in the dendrogram at which the fusion should be placed.
  * Compute the new pairwise inter-cluster dissimilarities among the $$i-1$$ remaining clusters.
* F: _Name and explain different linkage types, that can be used for clustering._
  * **Complete:** Maximal intercluster dissimilarity. Comput all  pairwise dissimilarities between the observations in a cluster A and the observations in a cluster B, and record the largest of theese dissimilarities. **Alternative:** Maximum distance between two points from the 2 cluster
  * **Single:** Minimal intercluster dissimilarity. Compute all pairswise dissimilarities between the observations in cluster A and the observations in cluster B, and record the smallest of these dissimiliarties. Single linkage can result in extended, trailing clusters in which single observations are fused one-at-a-time. **Alternative:** Minimum distance between two points from the 2 cluster
  * **Average:** Mean intercluster dissimilarity compute all pairwise dissimilarities between the observations in cluster A and the observations in Cluster B,  and record the average of these dissimilarities. **Alternative:** Average distance between 2 pairs
  * **Centroid:** Dissimilarity between the centroid for cluster A \(a mean vector of lenth p\) and the centroid for B. Centroid linkage can result in undesirable inversions. **Alternative**: Distance between the 2 centroids
* F: _Draw different linkage types visually._
  * ![](http://127.0.0.1:50852/12Qo9ezWv8KRs8zRMKxh.png)_​_

    _​_

    ![](http://127.0.0.1:50852/137Cmij89B1D5vvNh58X.png)

    ​
* F: _What is the impact of using different linkage types?_
  * \([see here.](https://stats.stackexchange.com/questions/195446/choosing-the-right-linkage-method-for-hierarchical-clustering)\)
  * ![](../.gitbook/assets/grafik%20%2849%29.png) 
* F: _Name practical issues that arise with hierarchical or_ $$k$$_-means clustering._
  * decision whether observations or features should be standardized i. e. zero mean / standard deviation of 1
  * Choice of similarity measure
  * Choice of linkage types
  * Decide on no. of clusters
* F: _Give applications for clustering._
  * Outlier detection
  * Compact summary of data for classification, hypothesis testing,...
  * Data reduction and summarization
  * Dynamic trend detection
  * Social network analysis
  * Multimedia data analysis
  * Recommendersysteme e. g. CF

## SVMs

* F: _Explain what a SVM is._
* F: _Required scaling for SVMs?_ ⭐
  * Features should be scaled to the interval $\[0,1\]$.
* F: _Name advantages and disadvantages of SVMs over logistic regression._ ⭐
  * SVMs can do better than logistic regression, in cases where data is \(nearly\) separable.
  * Logistic regression allows to estimate probabilities. This is however not possible with SVMs.
  * Logistic regression is faster.
  * Logistic regression is easier to interpret.
  * Etwas ausführlicher bereits beantwortet...
* F: _Recommendations to improve results of a SVM._ ⭐
* F: _Why is it good to use a maximum margin objective for classification?_ 🧠
* F: _How can we define the margins as optimization problem?_ 🧠
* F: _What are slack variables and how can they be used to get a "soft" margin?_ 🧠
* F: _How is hinge loss defined?_ 🧠
* F: _What is the relation between the slack variables and the hinge loss?_ 🧠
* F: _What are the advantages and disadvantages in comparison to logistic regression?_ 🧠
* F: _What is the difference between gradients and subgradients?_ 🧠
* F: _What is the definition of a kernel and its relation to an underlying feature space?_ 🧠
* F: _Why are kernels more powerful than traditional feature-based methods?_ 🧠
* F: _What do we mean by the kernel trick?_ 🧠
* F: _What is the central idea of SVMs?_
* A: We try to find a plane that separates the classes in the feature space. If that's not possible, we get creative in two ways:
  * We soften what we mean by separates through the introduction of support vectors.
  * We enrich and enlarge the feature space so that separation is possible. This means the feature space get's transformed.
* F: _What does a Maximal Margin Classifier maximize for?_
* F: _How do a Maximal Margin Classifier, SVMs and Logistic Regression relate?_
* F: \*What is the purpose of the support vectors $$\epsilon$$? 
* F: _Explain what is referred to as_ feature expansion\*?
* F: _Name and define kernels that can be used with SVMs._
* F: _Compare SVMs to logistic regression_
  * Logistic regression focuses on maximizing the probability of the data. The farther the data lies from the separating hyperplane \(on the correct side\), the better logistic regression is.
  * An SVM tries to find the separating hyperplane that maximizes the distance of the closest points to the margin \(the support vectors\). If a point is not a support vector, it doesn't really mater  [\(see here.\)](http://www.cs.toronto.edu/%7Ekswersky/wp-content/uploads/svm_vs_lr.pdf)
* A:
  * When classes are not linearly separable, SVM does better than logistic regression. \([See here](https://stats.stackexchange.com/a/95348)\)
  * Otherwise, the performance of logistic regression \(with ridge penalty\) and SVM are very similar. 
  * To estimate probabilities, the choice should be logistic regression.
  * If interpretability and speed is a major concern, logistic regression should be used.
* F: _Explain how Least-Squares Support Vector Regression improves ordinary SVMs for bond recovery rate prediction._
* F: _Explain how semiparametric Least-squares Support Vector Regression improves ordinary SVMs for bond recovery rate prediction._
* F: _Name proper alternatives to standard SVMs for default prediction._

## Neural Net

* F: _Explain what a Neural Network is._
* F: _How does logistic regression relate to neural networks?_ 🧠
* F: _What kind of functions can single layer NN learn?_ 🧠
* F: _Why do we need non-linear activation functions?_ 🧠
* F: _What activation functions can we use and what are advantages / disadvantages of those?_ 🧠
* F: _What output layer and loss function use given the task \(regression / classification\)?_ 🧠
* F: _Why not use a sigmoid activation function?_ 🧠
* F: _Why neural networks can overfit and what are the options to prevent it?_ 🧠
* F: _Early stopping, cross-validation and network pruning are techniques to prevent overfitting of Neural Nets. Explain them._ 
* F: _What makes an Ordinary Least Square Regression different from a neural net?_
* F: _Explain what Principal Component Regression is._
* F: _Explain how Principal Component Regression works._
* F: _Explain the purpose of activation functions._
* F: _Define different activation functions and sketch them._
* F: _Sketch a neural network with 3 input units, 4 hidden units and 2 output units. Make sure to label its components._
* F: _How is a recurrent neural net different from an ordinary neural network?_
* F: _Explain how back-propagation works in neural network._
* F: \*What is necessary to apply Neural Nets to classification tasks?
* F: For a fully-connected deep network with one hidden layer, increasing the number of hidden units should have what effect on bias and variance? 🧑‍🚒
* F: _What is the problem of Neural nets with many parameters?_ 
* F: _What is the impact of a higher number of layers and hidden units in a neural net?_
* A:
  * the more layers and more hidden units in a model, the more capacity it has.
  * There might not be enough data. A high capacity model easily overfits training data and results in a bad performance during testing.
* F: _Explain what network pruning is._
* F: _Explain how early stopping works with Neural Nets._
* F: _Consider the following two multilayer perceptrons, where all of the layers use linear activation functions. Give an advantage of Network A over Network B._ 🏕️

  ![Network architectures](../.gitbook/assets/network_architecture.jpg)

## RNN

* F: _Explain Recurrent Neural Networks \(RNN\)_ ⭐
* F: _What types of RNN were discussed in class?_
* F: _Give applications of RNNs._
* F: _What are key components of RNNs?_

## LSTM

* F: _Explain LSTMs._ ⭐
  * LSTMs are RNNs, that feature:
    * a forgetting mechanism \(whether specific information has already ended\)
    * a saving mechanism \(whether information is worth saving\)
  * That means LSTMs transform its memory in a very precise way: by using specific learning mechanisms for which pieces of information to remember, which to update, and which to pay attention to. 
  * One variant of LSTMs are GRUs where long-term and working memories are fused.
* F: _LSTMs are suitable for which type of analysis?_ ⭐
  * sequence modelling, with variable input and output length
  * time series analysis
* F: _How can we use LSTMs for time series dataset?_ ⭐
  * First of all time series forecasting problem must be re-framed as supervised learning problem.
  * One approach is to reframe time series data by considering past observations as input variables and future observations as the output variable.
  * Example:
    * Time series: 1, 2, 3, 4, 5, 6, 7
    * For $$I = 1$$, we can reframe our timeseries to the following supervised learning problem: \(x,y\): $$(1,2), (2,3), (3,4), (4,5) \cdots$$
* F: _Explain how LSTMs update their memory._
* F: _Give applications of LSTMS._

## Methods in NLP

* F: _How does the concept of Word2Vec work?_
* F: _How can the notion of similarity be embedded in a vector-to-word conversion?_
* F: _Sketch and explain the process of applying Continous Bag of Words to text prediction._
* F: _Why is Softmax used in a CBOW model?_
* F: _How does the Skip-Gram Model work_?
* F: _Compare the Skip-Gram Model to CBOW. In which way are they different?_
* F: _Explain different types of NLP applications including examples._
* F: _Explain what is commonly referred to as 'Named Entity Recognition'_
* F: _Name different approaches for 'Named Entity Recognition'. How do they relate._
* F: _Explain what a Sentiment Analysis is._
* F: _Name different Deep Learning Models used in NLP._

## RNNs / GRUs / Bidirectional LSTMs

* F: _Explain RNNs._
  * TODO:
  * RNNs maintain an internal memory about the world \(weights assigned to different pieces of information\) to help perform its classification.
  * A hidden state computed in a previous step e. g. timestep is fed back to the next step.
  * The most basic form of RNNs is called vanilla RNN and has a similar structure to standard neural networks.
  * Improvements of RNNs over Standard Networks
  * RNNs can be handle variable length input and output
  * Standard networks do not share previously learned features across different positions in a given text.
  * RNNs can be extended to a LSTM. RNNs can only overwrite their memory in an fairly uncontrolled fashion. LSTMs solve the vanishing gradient problem of RNNs. The vanishing gradient problem is the increasing difficulty of back propagating to the first layers with an increasing depth of the network.
* F: _Explain GRUs._
* F: _Explain Bidirectional LSTMs._
* F: _Explain Differences between RNNs and GRUs._
* F: _Explain 'Bidirectional Long Short Term Memory Network'._
* F: _What problem of RNN's do LSTMs solve?_
* F: _Explain what is called the 'vanishing gradient problem'._
* F: _Why is it desirable to use RNNs instead of standard networks for NLP?_
* F: _Explain why sigmoid activation results tend to be almost_ $$0$$ _or_ $$1$$_?_
* F: _Adding more hidden layers will solve the vanishing gradient problem for a 2 layer neural network._ 🧑‍🚒
* F: _xxx suffer\(s\) from the vanishing gradient problem. Circle all that apply and JUSTIFY YOUR ANSWER._ 🧑‍🚒
* F: _Adding L2-regularization will help with vanishing gradients_ 🧑‍🚒

## Misc

* F: _Techniques that can be used for default prediction._ ⭐
  * logistic regression
* F: _How do you evaluate this work? what is your main concern about his work?_ ⭐
  * Positive about his work is that he tried several models and that he used grid search for parameter optimization.
  * His work shows some sustainable problems.
  * The dataset is highly imbalanced, as non-default loans appear 4 times more often than defaulted loans. However he doesn't compensate for this by either upsampling the training data for model training \(I\) and by choosing the right might metric \(II\).
  * There are different costs for rejected loans and handed out, but defaulted loans. Defaulted loans are much more expensive than rejected loans. The used measure accuracy doesn't acknowledge that. 
  * As SVMs can be derived from logistic regression. That means a SVM with a linear kernel should at least perform as good as the logistic regression. \(further research required\)
  * TODO: Formel for Accuracy für Datenset berechnen wenn Mehrheitsklasse / 80 % / 
* F: _What is your suggestion?_⭐
  * I'd recommend to choose $$F_1$$ as a measure or other measures that can handle imbalanced data and apply different cost. 
  * It might be wise to plot ROC curves to find a sweet spot \(combination with greatest ascend\) between True Positive and False Positive Rate.
  * Analyse der False negatives
  * TODO: Up-sampling / down-sampling synthetic sampling Smote. Implement dummy classifier \(majority vote\)  as baseline.
* F: _Do you have any recommendation for improving the SVM results?_ ⭐
  * I'd recommend the following:
    * Scaling features to a $$[0,1]$$ range.
    * Apply feature expansion and fit Support Vector classifier on a larger feature space
    * train SVMs on up-sampled data to have an equal balance of defaulted and non-defaulted loans.
    * Varying more parameters with grid search such as degree of polynomial or width of support vectors.
    * TODO: improved data preprocessing
* F: _Calculate the information gain of the input attribute age and income using entropy._ ⭐
* F: _Which variable \(income or age\) do you suggest for first splitting? Why?_ \(2+2\)
* F: _List other machine learning techniques that can be used for default prediction._⭐
  * Decision Tree for classification
  * Bagging for classification 
  * Gradient Boosting for Classification such as XGBoost, CatBoost
  * Random Forest for classification
  * Deep Learning
  * Neural Nets

