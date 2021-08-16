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
  * Variety refers to the diversity of types of data. Data can come in structured, semi-structured, or even unstructured types.
  * Velocity refers to the sheer speed at which data is generated \(and processed\).
  * Veracity refers to the quality of data or accuracy of the collected data. To resolve data quality issues one has to apply sophisticated pre-processing.
* F: _What is the difference between veracity and variety?_

  Veracity refers to the quality of data \(e. g. noise in data\). While variety refers to types of data \(e. g. unstructured data\) in which data can come. As data is often collected from different sources both their types and their quality can differ.

## ML vs. Statistics vs. Econometrics

* F: _Compare ML to Statistics. What are the most significant differences?_

  Statistics is:

  * based on hypothesis, then a collection of data and analysis
  * model-oriented with an emphasis on parametric models
  * focus on understanding and hypothesis testing

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
  * using all sorts of data-driven models e. g. Trees, NN, etc.  

## Structure of data / CRISP-DM / Taxonomy

* F: _What are the characteristics of unstructured data? Explain them._ ⭐

  Unstructured data is:

  * **Nonnumeric:** No predefined numeric representation for the constructs of interests. Requires manual or automatic coding prior to analysis.
  * **Multifaceted:** A single unit of unstructured data posses multiple facets. Each aspect of data provides unique information for studying and different types of research goals. E. g. voice data present information about the speaker such as pitch, speech rate. Data can be used both in psychology and communication. 
  * **Concurrent representation:** The simultaneous presence of a single data unit's multiple facets that each provides unique information, which allows to represent of different phenomena at the same time. One can study different research questions with one single unit of unstructured data.

* F: What is 'structured data'?
  * Structured data is data that adheres to a pre-defined data model and is therefore straightforward to analyze.
  * Structured data conforms to a tabular format with a relationship between the different rows and columns.
* F: _What is **unsupervised learning**?_ ⭐
  * Observe data and construct a low complexity description of the data. 
  * That means in unsupervised learning the dataset that a data set transforms into is _not previously known_ or understood. Data is not labeled. \(Grooking p. 13\) 
  * We observe only the features $$X_1, X_2,\ldots, X_P$$. We are not interested in prediction, because we do not have an associated response variable $$Y$$.
* F: _What is **supervised learning**?_ ⭐
  * We observe both a set of features $$X_1,X_2,\ldots,X_P$$ for each object, as well as a response or outcome variable $$Y$$. The goal is then to predict $$Y$$ using $$X_1, X_2,\ldots,X_P$$.
  * Examples include clustering and PCA.
* F: _What are **advantages / disadvantages** of **unsupervised learning techniques**?_
  * No labeled data required, which is often expensive and laborious. \(+\) 
  * Adding labels to the data after clustering is often easier \(+\) \(own\)
  * Unsupervised techniques such as clustering help with data understanding of the raw data. \(+\) \(own\)
  * Unsupervised learning is more subjective, as there is no simple objective \(-\)
* F: _Name practical applications of unsupervised learning._
  * Subgroups of breast cancer patients grouped by their gene expression measurements
  * Groups of shoppers characterized by their browsing and purchase histories
  * Movies grouped by ratings assigned by movie raters
* F: _What is the goal of unsupervised learning?_
  * The goal of unsupervised learning is to discover interesting things about the measurements on how to **visualize data** and **finding subgroups** among variables or observations.
* F: _Give two examples for unsupervised learning techniques._ 
  * Clustering algorithms such as $$k$$-means
  * Dimensionality reduction techniques such as PCA
* F: _Give examples for structured/unstructured data._

  **Unstructured:** \(low degree of organization\)

  * Video Data, as the video comes in different formats, compression ratios, sizes, where the video has to be transformed first to extract information from every single frame
  * Image Data, just like videos.

  **Structured:** \(high degree of organization\)

  * Numeric secondary data e. g. sales figures, as they come in a standardized format and easy to process format e. g. float with $$x$$ decimal places 
  * Categorial data e. g. gender, as there are predefined formats

* F: _Give a brief explanation of categorical, binary, ordinal, and numeric variables._
  *  **categorical/nominal:** Names of things or symbols.
  * **binary:** A nominal variable with two categories or states: 0 or 1.
  * **ordinal:** Ordinal variables have a meaningful order or ranking among them, but the magnitude between successive values is not known.
  * **numeric:** A quantitative variable. Numeric variables could be interval-scaled or ratio-scaled.
* F: _Which steps are part of the CRISP-DM model? Explain them in-depth._
  1. **Business understanding** i. e. developing an understanding of business objects and requirements of the data mining
  2. **Data understanding** i. e. identify and collect the data set needed to fulfill the business goals
  3. **Data preparation** i. e. prepare data for modeling
  4. **modeling** i. e. build several models and assess them on a technical level.
  5. **Evaluation** i. e. Evaluate whether models are able to help achieve the business goals. Plan on the next steps.
  6. **Deployment** i. e. Deploy model to production. Make it accessible to customers.
* F: _Explain common techniques for data gathering._
  * **Bulk downloads:** Downloading large amounts of data. Often done using sophisticated software.
  * **APIs:** Accessing data through machine-readable interfaces. Examples include Google Maps API.
  * **Web Scraping:** Extraction of data from websites. Often done using bots and web crawlers or manually.
* F: _Why is it desirable to work on normalized data?_
  * Some algorithms require normalized data, such as $$k$$-means clustering, which is 'isotropic' in all directions of space and therefore tens to produce more or less round shapes. Not standardizing data would give more relative on variables with a smaller variance. \([See here.](https://stats.stackexchange.com/a/21226)\) 
* F: _Explain common techniques to analyze the relationship between variables._ 
  * A scatter plot \(or scatter diagram\) is used to show the relationship between variables
  * Bar plot for high dimensional data
  * Mean graph for categorical data
  * Correlation analysis
* F: _How can missing data be replaced? Explain._
  * **mean-based imputation:** i. e. mean is calculated from all observations
  * **median-based imputation:** Same as above but with median.
  * **stratified imputation:** i. e. categories/ structure of data is considered for replacements. E. g. missing height is different for gender male and female.
  * **regressed imputation:** i. e. replacing missing values by predictions of a regression model
* F: _Explain 3 patterns in which missing data can occur._
  * **Completely random / MCAR:** Missing values have no pattern. Can not be predicted.
  * **Missing at random / MaR:** Missing values can be predicted using other data available for observation. Assign a categorial value.
  * **Latent, yet unknown variable:** Missing value depends on a latent and highly correlated variable.
* F: _What is a training, test, and validation set for?_
  * **Training set** is used to fit all potential models
  * **Validation set** is used to select hyperparameters of a model
  * **Test set** is used to estimate the predictive power of a model on unseen data
* F: _What is the risk with tuning hyperparameters using a test dataset?_ 🧑‍🚒
  * Tuning model hyperparameters to a test set means that the hyperparameters may overfit that test set. If the same test set is used to estimate performance, it will produce an overestimate. Using a separate validation set for tuning and test set for measuring performance provides an unbiased, realistic measurement of performance. \(Berkley p. 14\)

## LR, Ridge, and Lasso

* F: _Explain how **best subset selection** works in 3 steps._
  1. Let $$\mathcal{M}_{0}$$ denote the null model, which contains no predictors. This model simply predicts the sample mean for each observation. 2. For $$k=1,2, \ldots p$$ : 
* a. Fit all $$\left(\begin{array}{l}p \\ k\end{array}\right)$$ models that contain exactly $$k$$ predictors.
* b. Pick the best among these $$\left(\begin{array}{l}p \\ k\end{array}\right)$$ models, and call it $$\mathcal{M}_{k}$$. Here best is defined as having the smallest RSS, or equivalently largest $$R^{2}$$.
* Select a single best model from among $$\mathcal{M}{0}, \ldots, \mathcal{M}{p}$$ using cross-validated prediction error, $$C_{p}$$ \(AIC\), BIC, or adjusted $$R^{2}$$.
* F: _Explain how **forward stepwise selection** works in 3 steps._
  * **Intuition:**

    Instead of searching through all possible subsets, we can seek a good path through them. Forward stepwise selection starts with the intercept, and then sequentially adds into the model the predictor that most improves the fit. Like best subset regression, forward stepwise produces a sequence of models indexed by $$k$$, the subset size, which must be determined. \(Hastie p. 59\)

  * **More formal description:** 1. Let $$\mathcal{M}_{0}$$ denote the null model, which contains no predictors. 2. For $$k=0, \cdots, p-1$$: a. Consider all $$p-k$$ models that augment the predictors in $$\mathcal{M}_{k}$$ with one additional predictor. b. Choose the best among these $$p-k$$ models, and call it $$\mathcal{M}_{k+1}$$. Here best is defined as having smallest RSS or highest $$R^{2}$$. 3. Select a single best model from among $$\mathcal{M}_{0}, \ldots, \mathcal{M}_{p}$$ using cross-validated prediction error, $$C_{p}$$, AIC, BIC, on adjusted $$R^{2}$$.
* F: _Explain how **backward stepwise selection** works in 3 steps._
  * Backward- stepwise selection starts with the full model and sequentially deletes the predictor that has the least impact on the fit. The candidate for dropping is the one with the largest RSS and lowest $$R^2$$. \(Hastie p. 60\)
  * **More formal definition:**

    Let $$\mathcal{M}_{p}$$ denote the full model, which contains all $$p$$ predictors.

    1. For $$k=p, p-1, \ldots, 1$$ : a. Consider all $$k$$ models that contain all but one of the predictors in $$\mathcal{M}{k}$$, for a total of $$k-1$$ predictors. b. Choose the best among these $$k$$ models, and call it $$\mathcal{M}_{k-1}$$. Here best is defined as having smallest RSS or highest $$R^{2}$$.
    2. Select a single best model from among $$\mathcal{M}_{0}, \ldots, \mathcal{M}_{P}$$ using cross-validated prediction error, $$C_{p}$$, AIC, BIC, or adjusted $$R^{2}$$.
* F: _Compare the **best subset selection** to **forward selection**._ 
  * **Forward stepwise selection** begins with a model containing no predictors, and then adds predictors to the model, one-at-a-time, until all of the predictors are in the model.
  * **Best Subset Selection** does not add predictors one-at-a-time but chooses from models containing **exactly** $$k$$ variables. Predictors might be **different** for different $$k$$s.
  * **Best Subset Selection** becomes infeasible for large number of variables \($$\geq 40$$\). \(Hastie p.59\)
* F: _Compare the subset selection methods **forward** and **backward stepwise selection**._ 
  * **Backward stepwise selection** is pretty much the inverse of **forward stepwise selection**.
* F: _When is it desirable to use **backward stepwise selection** and when is it desirable to use **forward stepwise selection or best subset selection**?_
  * Computationally best subset selection is most demanding and becomes infeasible for a large number of features.
  * All three deliver similar results \(See the comparison in Hastie p. 59\)
* F: _What is an alternative to subset selection methods presented in the lecture?_ 
  * **Forward-stagewise regression**
* F: _What are the reasons why shrinkage methods such as **LASSO** are preferred over subset selection methods such as **best subset selection**?_
  * If the **best subset** can be found, it is indeed better than the LASSO in terms of selecting the variables that actually contribute to the fit.
  * In practice **LASSO** is still preferred as it is computationally much easier to estimate e. g. through the calculation of regularization paths using pathwise coordinate descent. Whereas **best subset selection** is a NP-hard problem. \([see here.](https://stats.stackexchange.com/questions/350587/why-is-best-subset-selection-not-favored-in-comparison-to-lasso)\)
  * TODO: Lasso ist wenig nachvollziehbar
* F: _Explain how **Linear Regression** works._
  * Linear regression is a linear model \(aka a model that assumes a **linear relationship** between input variables $$X$$and the single output variable $$y$$\). $$y$$ is a linear combination of the input variables $$x_1$$ to $$x_k$$. To best describe the relationship between input variables and output variables a line or hyperplane is fitted to the point cloud. \(own\)
  * The multiple linear regression model for the population is defined as:

    $$
    y=\beta_{0}+\beta_{1} x_{1}+\beta_{2} x_{2}+\cdots+\beta_{k} x_{k}+\epsilon
    $$

    $$\beta_{0}$$ is intercept, $$\beta{1}, \ldots, \beta_{k}$$ are regression coefficients of $$k$$ independent variables, and $$\epsilon$$ is error. $$x$$are the input variables and $$y$$ the dependent variable. We can present this equation in vector notation:

    $$
    y=\beta X+\epsilon
    $$
* F: _What is the purpose_ $$\beta$$ _in a **Multiple Linear Regression Model**?_
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

* F: _Does standard Linear Regression require scaling?_
  * No, as multiplying $$X_i$$ with a constant $$c$$leads to a scaling of the least square coefficient estimates by a factor $$1/c$$.  
* F: Why do we optimize for the SSE for?
  * It is fully differentiable 
  * Easy to optimize
  * It also makes sense as:

    $$
    f^{*}(x)=\operatorname{argmin}_{f(x)} \mathrm{SSE} \Rightarrow f^{*}(x)=\mathbb{E}[y \mid x]
    $$
* F: _Give the definition for the **SSE**._
  * $$
    S S T=\sum_{i=1}^{n}\left(y_{i}-\bar{y}\right)^{2}
    $$
  * where$$\bar{y}$$ is the observed mean of $$y$$.
* F: _Give the definition for the **SSR**._
  * $$
    S S R=\sum_{i=1}^{n}\left(\hat{y}_{i}-\bar{y}\right)^{2}
    $$
  * where $$\hat{y}$$is the prediction for $$y$$ and $$\bar{y}$$the observed mean.
* F: _Give the definition for the **SST**._
  * $$
    S S E=\sum_{i=1}^{n}\left(y_{i}-\hat{y}_{i}\right)^{2}=\sum_{i=1}^{n} e_{i}^{2}
    $$
  * where $$\hat{y}$$is the prediction for $$y$$. 
* _F: Give a graphical intuition for the **SSE**, **SSR** and **SST**._
  * \_\_![](../.gitbook/assets/visualization-of-sse-ssr-sst.png)
  * \(see [here.](https://www.researchgate.net/figure/Visualization-of-SSE-SSR-SST_fig17_322398615)\)
* F: _Name two measure to test the goodness of fit of a Linear Regression model._
  * Total Sum of Squares \(SST\)
  * $$R^2$$ 
* F: _Write the definitions_ $$R^2$$_, Adj._ $$R^2$$_, MAE, RMSE._ 
  * $$R^{2}=1-\frac{S S E}{S S T}$$ 
  * $$\text { Adjusted } R^{2}=1-\left(1-R^{2}\right)\left(\frac{n-1}{n-k-1}\right)$$ 
  * $$\text{RMSE}=\sqrt{\frac{1}{n} \sum_{i=1}^{n}\left(y_{i}-\hat{y}_{i}\right)^{2}}$$ 
  * $$\text{MAE}=\frac{1}{n} \sum_{i=1}^{n}\left|y_{i}-\hat{y}_{i}\right|$$ 
  * TODO: n, k einführen....
* F: _Give an intuition for_ $$R^2$$ _, MAE and RMSE._
  * $$R^2$$ / adj. $$R^2$$**:** How well can my model explain the variance?
  * **MAE:** How does the model perform on average?
  * **RMSE:** How many large prediction derivations does the model have? \(lecture BDA p. 43\)
* F: _Compare_ $$R^2$$_, Adj._ $$R^2$$ _to MSE, MAE and RMSE. Name advantages and drawbacks._  
  * **MSE:**
    * MSE is differentiable, which is important for finding optima. \(+\)
  * **MAE:** 
    * The scale of MAE, RMSE depends on the scale of the dependent variable. \(-\)
    * MAE is not differentiable. \(-\)
    * MAE is more robust to outliers. \(+\)
  * $$R^2$$ **:** 
    * Measure always increases by adding new independent variables which can lead to the addition of redundant variables in the model. \(-\)
* F: _Compare MAE to RMSE._
  * **RMSE** penalizes large errors more than MAE. This can be useful if being off by ten is more than twice as bad as being of by 5. If however being off by 5 is just as bad as being of by 10, MAE should be preferred. \([See here](https://medium.com/human-in-a-machine-world/mae-and-rmse-which-metric-is-better-e60ac3bde13d).\)
* F: _Compare_ $$R^2$$_, Adj._ $$R^2$$ _to MAE, RMSE. Which of these is normed._ 
  * $$R^2$$ and Adj. $$R^2$$ between$$[0,1]$$. TODO: worse than 0 if prediction is worse than mean  / large SSE vs small SST.
  * MAE, RMSE between$$[0, \infty)$$. If RMSE is acceptable depends on the scale of the variables. [\(see here\)](https://stats.stackexchange.com/a/56332). RMSE and MAE are $$0$$ for models with a perfect fit.
* F: _In which way does the adjusted_ $$R^2$$ _improve the standard_ $$R^2$$_?_ 
  * A model might have a good fit in-sample but poor fit on out-of-sample, if to many regressors are used.
  * Adj. $$R^2$$ is a $$R^2$$ which has been corrected by a penalty function and takes into account the number of $$k$$ regressors in the model.
* F: _Explain the three steps in fitting a regression model._ 
  * **Specification:** 
    * Determine dependent and explanatory variables. 
    * Exclude explanatory variables without predictive power. 
    * Collect data for dependent and explanatory variables.
  * **Fitting / Estimating:**
    * Estimating regression coefficients.
  * **Diagnosis:**
    * Determine the quality of the regression model with e. g. $$R^2$$, adj.$$R^2$$ , MSE and MAE.
    * Determine the model's significance and the significance of the regression coefficients.
    * analyze standard deviation of regression errors.
* F: _Explain how one can test for the significance of a regression model. Give_ $$H_{0}$$ _and_ $$H_{1}$$ _Hypothesis for regression models._
  * $$H_{0}$$ states that all regression coefficients are equal to zero, which means none of the explanatory variables play any role.

    $$
    H_{0}: \beta_{0}=\beta_{1}=\cdots=\beta_{k}=0
    $$

    $$H_{1}$$ states that at least one coefficient is different from zero.

    $$
    H_{1}: \beta_{j}\neq0 \text { for at least one } j
    $$
* F: _Give an intuition for the Analysis of Variance \(ANOVA\) test._
  * The ANOVA-Test compares whether the means of two separate sets are equal.
  * The observation $$x_{i,j}$$ which is the $$j$$-th observation of $$i$$th can be decomposed into the **between-groups variance** $$\left(\bar{x}_{i}-\bar{x}\right)$$, the **within-group variance** $$\left(x_{i,j}-\bar{x}_i\right)$$ and the **between-groups mean** $$\bar{x}$$. One gets: 
  * $$x_{i,j} = \bar{x} + \left(\bar{x}_{i}-\bar{x}\right) +\left(x_{i j}-\bar{x}_{i}\right)$$
  * Now the $$F$$statistic is simply the **ratio** of the **between-groups variance** and the **within-group variance** \([see here.](https://www.uni-wuerzburg.de/fileadmin/10040800/user_upload/hain/SPSS/ANOVA.pdf)\) \([see here.](https://statisticsbyjim.com/anova/f-tests-anova/)\)
* F: _How is the ANOVA test /_ $$F$$_-test defined?_
  * $$
    F=\frac{\frac{S S R}{k}}{\frac{S S E}{n-k-1}}=\frac{M S R}{M S E},
    $$
  * where$$n$$ is sample size, $$k$$number of parameters in model, $$k-1$$number of slope parameters.
* F: _Explain how one can interpret the_ $$F$$_-Test._
  * If the $$p$$-Value of the $$F$$-Test is less than a significance level $$\alpha$$, the model does explain some variation of the dependent variable $$y$$.
  * One needs to have a $$F$$table for the corresponding $$\alpha$$.
* F: _Explain what **multicollinearity** is._
  * Multicollinearity refers to the situation in which more than two explanatory variables in a multiple regression model are **highly correlated**.
  * Tests for multicollinearity are necessary after the models significance has been determined and all significant independent variables as if strong multicollinearity is present, a change in one explanatory variable will also lead to a change of another explanatory variable.
* F: _Name three possible indicators for **multicollinearity**._
  * Sensitivity of regression coefficients to the inclusion of additional explanatory variables
  * change from significance to insignificance after more explanatory variables have been added
  * An increase in the model’s standard error of the regression
* F: _How can one test for multicollinearity?_
  * One can use the **variance inflation factor \(VIF\)**
* F: _Give the definition for the **variance inflation factor**._
  * To check the $$j$$th variable for multicollinearity, one can calculate the VIF as following:
  * The $$j$$-th variable is regressed on the remaining $$k-1$$ variables. The resulting regression would look like:

    $$
    x_{j}=c+b_{1}^{(j)} x_{1}+\cdots+b_{j-1}^{(j)} x_{j-1}+b_{j+1}^{(j)} x_{j+1}+\cdots+b_{k}^{(j)} x_{k} \quad j=1,2, \cdots, k
    $$

    Then we obtain coefficients of determination of this regression, $$R_{j}^{2}$$.
* F: _What is the intuition of the **Variance Inflation Factor**?_
  * The $$j$$th variable is regressed on the remaining $$k-1$$ variables / features. 
  * If $$R^2$$is large, that means the remaining variables can explain the $$j$$th variable and so the resulting **VIF** will be large.
  * TODO: Formula!
* F: _How can **VIF** be interpreted._
  * A VIF of 10 indicates a severe impact due to multicollinearity.
* F: _How can one test for **linearity**?_
  * Plot regression residuals on the vertical axis and values of the explanatory variables on the horizontal axis. Repeat for every explanatory variable. If errors are randomly scattered, around zero the model assumption is correct.
  * ![](../.gitbook/assets/residuals-2.png) 
  * Image downloaded from [here](https://www.scikit-yb.org/en/latest/api/regressor/residuals.html).
* F: _Why is it not desirable to use **Linear Regression** for default prediction?_ 
  * In default prediction one searches for provability of default $$\operatorname{Pr}(\text { default }=\text { Yes } \mid \text { balance })$$ , which ranges between $$0$$ and $$1$$ .
  * Fitting a line between to a binary response variable \(1 = default / 0 = non-default\), could lead to estimates outside the $$[0,1]$$ interval, making them hard to interpret as probabilities i. e. if probabilities are negative.
  * Nevertheless, the predictions provide an ordering and can be interpreted as crude probability estimates.
* F: _Explain scenarios, where Ridge Regression would be preferred over LASSO._ 
  * Ridge only performs parameter shrinkage and no variable selection.
  * Ridge regression is preferred if one wants to insert some prior knowledge into the approach. With ridge, one has the ability to say that all features have at least some weight, even if it is very little [\(See here.\)](https://qr.ae/pG4QYT)
* F: _Explain scenarios where LASSO are preferred over Ridge Regression._ 
  * As with ridge regression, the LASSO shrinks the coefficient estimates towards zero.
  * However, in the case of LASSO some coefficient estimates are forced to be exactly equal to zero \(zeroed out\) when the tuning parameter $$\lambda$$ is sufficiently large. 
  * Therefore, LASSO does variable selection automatically and shrinkage of parameters.
* F: Name two approaches for shrinking regression coefficients towards zero.
  * ridge regression
  * LASSO
* F: _Explain what regularization is and why it is useful_
  * A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* F: _Explain the ridge regression._ ⭐
  * TODO: extension to Linearen Regression
  * Ridge regression is a regularization approach. Regularization is used to prevent coefficients from fitting so perfectly. This is done by adding a constant multiple to an existing weight vector. Which is sometimes referred to as a **regularization term** or **shrinkage penalty**. In case of **ridge regression** this **regularization term**. In case of **ridge regression** it is the sum of the square of the weights.
  * Taking this into account one get's the following formula for ridge regression:

$$
\sum_{i=1}^{n}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} \beta_{j} x_{i j}\right)^{2}+\lambda \sum_{j=1}^{p} \beta_{j}^{2}=R S S+\lambda \sum_{j=1}^{p} \beta_{j}^{2}
$$

* * where $$\lambda \geq 0$$ is a tuning parameter, to be determined separately. The tuning parameter $$\lambda$$ serves as control of the relative impact of these two terms on the regression coefficients. Should be selected using cross-validation. 
  * Still ridge regression seeks coefficient estimates that fit the data well through minimizing the RSS. 
  * The **shrinkage penalty** is small when $$\beta_1,\cdots, \beta_p$$ are close to zero, and so it has the effect of shrinking the estimates of $$\beta_j$$ towards zero. However, $$\beta_0$$is left out from the penalty term, as penalizing the intercept would just shift$$y_i$$ by some amount $$c$$. \(Hastie p. 64\)
  * As such:
    * ridge regression yields non-sparse outputs, as coefficients are shrinked towards zero but never actually are 0.
    * doesn't allow for feature selection. Same reasoning as above.
    * Typically yields better results than LASSO.
* F: Why is the intercept$$\beta_0$$**not** part of the regularization term? 
  * The intercept $$β_0$$ has been left out of the penalty term. Penalization of the intercept would make the procedure depend on the origin chosen for $$Y$$; that is, adding a constant $$c$$ to each of the targets $$y_i$$ would not simply result in a shift of the predictions by the same amount $$c$$. \(Hastie p. 64\)
  * Indeed, in the presence of the intercept term, adding $$c$$ to all $$y_i$$ will simply lead to $$\beta_0$$ increasing by $$c$$ as well, and correspondingly all predicted values $$y_i$$ will also increase by $$c$$. This is not true if the intercept is penalized: $$\beta_0$$ will have to increase by less than c.  \([see here.](https://stats.stackexchange.com/a/161689)\)
* F: Match $$\ell_1$$norm,$$\ell_2$$norm, ridge regression and LASSO to its counterparts.
  * ridge: $$\ell_2$$
  * LASSO: $$\ell_1$$
* F: How is the $$\ell_2$$norm defined?
  * $${||\beta||}_{2}=\sqrt{\sum_{j=1}^{p} \beta_{j}^{2}}$$
* F: How is the $$\ell_1$$norm defined?
  * $${||\beta||}_{1}=\sum_{j=1}^{p} |\beta_{j} |$$
* F: _Explain LASSO._
  * Lasso regression is a regularization approach. Regularization is used to prevent coefficients from fitting to perfectly. This is done by adding a constant multiple with an existing weight vector. Which is referred to as **regularization term** or **shrinkage penalty**. In the case of LASSO regression, it is the **sum of absolute weights**.
  * Taking this into account one get's the following formula for ridge regression:

    $$
    \sum_{i=1}^{n}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} \beta_{j} x_{i j}\right)^{2}+\lambda \sum_{j=1}^{p} |\beta_{j}|=R S S+\lambda \sum_{j=1}^{p} |\beta_{j}|,
    $$

    where $$\lambda \geq 0$$ is a tuning parameter, to be determined separately. The tuning parameter $$\lambda$$ serves as control of the relative impact of these two terms on the regression coefficients. Should be selected using cross-validation.

  * Still ridge regression seeks for coefficient estimates that fit the data well through minimizing the RSS.
  * The **shrinkage penalty** is small when $$\beta_1,\cdots, \beta_p$$ are close to zero, and so it has the effect of shrinking the estimates of $$\beta_j$$ towards zero. However, $$\beta_0$$is left out from the penalty term. Some coefficient estimates are even forced to be exactly zero, if $$\lambda$$is sufficiently large. 
  * As such:
    * Lasso regression yields sparse models. That is, models that involve only a subset of the variables.
    * Can be used for feature selection.
* F: _Explain the difference between LASSO and ridge regression?_ ⭐
  * Both are regularization approaches in order to prevent overfitting of an ordinary linear regression model and introduce smoothness to the model. This is done by adding a constant multiple of an weight vector that prevents the coefficients so perfectly that they overfit.
  * Both shrinkage methods to shrink regression coefficients towards zero.
  * The difference between LASSO and ridge regression is that ridge is just the square of the weights, while Lasso is just the sum of the absolute weights in MSE or other loss functions.
  * TODO: l1 and l2 norm
  * LASSO:

$$
\underset{\beta}{\operatorname{minimize}} \sum_{i=1}^{n}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} \beta_{j} x_{i j}\right)^{2} \quad \text { subject to } \quad \sum_{j=1}^{p}\left|\beta_{j}\right| \leq s
$$

* Ridge regression:

$$
\underset{\beta}{\operatorname{minimize}} \sum_{i=1}^{n}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} \beta_{j} x_{i j}\right)^{2} \quad \text { subject to } \quad \sum_{j=1}^{p} \beta_{j}^{2} \leq s
$$

* The main difference is, that when doing a subset selection, which will generally select models that involve just a subset of the variables, ridge regression will include all $$p$$ predictors in the final model. However, LASSO helps to zero-out coefficients and can yield sparse feature spaces. Where as ridge regression yields non-sparse outputs and can not be used for feature-selection straight away.
* However, in practice ridge regression performs better than LASSO. [\(See here.\)](https://github.com/iamtodor/data-science-interview-questions-and-answers) According to the script there is no clear tendency.
* **Visualization:**
* ![](../.gitbook/assets/grafik%20%2828%29.png) 
* F: _In practice, explain what is the main difference between ridge regression and LASSO._ ⭐
  * Both are regularization approaches to prevent overfitting of an ordinary linear regression model and introduce smoothness to the model. This is done by adding a constant multiple of an weight vector that prevents the coefficients so perfectly that they overfit.
  * Both shrinkage methods to shrink regression coefficients towards zero.
  * The difference between LASSO and ridge regression is that ridge is just the square of the weights, while Lasso is just the sum of the absolute weights in MSE or other loss functions.
  * TODO: Formel 
* F: _Explain what is the difference between Linear Regression and LASSO?_ \(8 points\) ⭐
  * TODO: Def. lin regression
  * The formula for **linear regression** is given by:

$$
\min _{\boldsymbol{\beta}} \sum_{i=1}^{N}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} x_{i j} \beta_{j}\right)^{2}
$$

* where $$\beta_0$$ is the intercept and $$\beta_1 \cdots \beta_p$$ are regression coefficients of $$k$$ independent variables.
* The formula for **LASSO** coefficients $$\hat{\beta}_{\lambda}^{L}$$ is given by:

$$
\arg \min _{\mathbf{\beta}} \sum_{i=1}^{n}\left(y_{i}-\beta_{0}-\sum_{j=1}^{p} \beta_{j} x_{i j}\right)^{2}+\lambda \sum_{j=1}^{p} \mid \beta_{j} \mid
$$

* Where $$\lambda$$ is a tuning parameter that serves as control of the relative impact of these two terms on the regression coefficients.
* As it can be seen above, linear regression is the most basic form. LASSO includes another term - the so-called regularization term or **shrinkage penalty**. More on that later. The standard linear regression doesn't penalize for the choice of weights and doesn't include a regularization term.
* One could say LASSO is a variant of Linear Regression. And linear regression is in general no variant of LASSO.
* Linear regression tries to estimate the coefficients as such, that the residual sum of squares $$(\beta_0 + \dots)$$ is minimized.
  * This also means that linear regression learns the training heart and is prone to overfitting. LASSO, which is a regularization approach, tries to prevent overfitting through the introduction of regularization term, which prevents the coefficients so perfectly to overfit.
  * Another difference is that LASSO is a shrinkage method and can be used for variable selection. Where as linear regression is not suitable for feature selection.
  * For both closed-form solutions exist.
* F: _What are the main applications of LASSO?_⭐
  * LASSO is suitable for feature selection, as some coefficient estimates are forced exactly to zero, if the tuning parameter $$\lambda$$ is sufficiently large.
  * Whenever sparse models \(models that only include a subset of the variables\) are needed.
* F: _Explain stability selection technique. What is the main advantage of stability selection technique compared to LASSO?_⭐
  * With LASSO regression the variables selected can change even if data is ever-so-slightly changed. Stability selection technique leads to a more stable selection of variables than LASSO.
  * Stability selection works by fitting variables on a subsample of data. Afterward one can count the proportion of times a variable is selected. This leads to a more stable selection.
* F: _Name one major advantage of **LASSO** over **ridge regression**._
  * Lasso yields sparse models, that is, models that only involve a subset of other variables.
* F: _How should_ $$\lambda$$ _be selected for **ridge regression** / **LASSO**?_
  * Cross-validation provides a simple way to tackle this problem. We choose a grid of $$\lambda$$ values, and compute the cross-validation error rate for each value of $$\lambda$$. We then select the tuning parameter value for which the cross-validation error is smallest and fit the model on all available observations.
* F:  _Should inputs be scaled for **ridge regression?** If so, how?_
  * The ridge solutions are not equivariant under scaling the inputs. That means regression coefficients can change substantially when multiplying a given predictor with a constant $$c$$, and so one normally standardizes the inputs before solving. One might use the following formula:
  * $$\bar{x}_{i j}=\frac{x_{i j}}{\sqrt{\frac{1}{n} \sum_{i=1}^{n}\left(x_{i j}-\bar{x}_{j}\right)^{2}}}$$
* F: Should inputs be scaled for Lasso?
  * TODO: yes: [https://stats.stackexchange.com/questions/86434/is-standardisation-before-lasso-really-necessary](https://stats.stackexchange.com/questions/86434/is-standardisation-before-lasso-really-necessary)
* F: _Name common assumptions about error terms._ 1. Regression Errors are normally distributed 2. The variance of regression errors is constant 3. The error terms from different points in time are independent

  * **But:** Linear Regression doesn't need the normal assumption, the estimator can be calculated without any need of such assumption. However, it is convenient from a user point of view to use errors are normally distributed to calculate confidence intervals etc. [\(see here.\)](https://stats.stackexchange.com/a/148812)

  **But:** Linear Regression doesn't need the normal assumption, the estimator can be calculated without any need of such assumption. However, it is convenient from a user point of view to use errors are normally distributed to calculate confidence intervals, etc. [\(see here.\)](https://stats.stackexchange.com/a/148812)

## Logistic Regression

* F: _In which way do logistic regression and linear regression differ?_
  * _Linear regression is applied to **regression problems**, whereas logistic regression is used for **classification**._
  * _The loss function in linear regression is calculated using SSE, whereas in logistic regression it's maximum likelihood estimation._
  * _The output of linear regression is continuous. The output of logistic regression is discrete_
* F: _Explain what logistic regression is._ 
  * Logistic regression is a classification approach. 
  * It is a predictive analysis that describes data and explains the relationship between variables.
  * Logistic regression gives discrete outputs between 0 and 1 for an input variable $$X$$. To do so, a logistic function is utilized:$$p(X)=\frac{e^{\beta_{0}+\beta_{1} X}}{1+e^{\beta_{0}+\beta_{1} X}}$$, which produces a S-shaped like curve.
  * The regression coefficients $$(\beta_0, \beta_1X_1+\cdots+\beta_PX_P)$$ are estimated using the maximum likelihood method.
  * TODO: exponential trick, why log?
* F: _How is the maximum likelihood estimated in a logistic regression setting?_
  * We try to maximize likelihood to estimate the parameters:

    $$\ell\left(\beta_{0}, \beta_{1}\right)=\prod_{i: y_{i}=1} p\left(x_{i}\right) \prod_{i: y_{i}=0}\left(1-p\left(x_{i}\right)\right)$$

  * The estimates $$\beta_0$$ and $$\beta_1$$ are chosen to maximize the likelihood of the observed data.
* F: _How can logistic regression enhanced to a multiple logistic regression case?_

  * We can generalize to the following form: 

  $$p(X)=\frac{e^{\beta_{0}+\beta_{1} X_{1}+\ldots+\beta_{p} X_{p}}}{1+e^{\beta_{0}+\beta_{1} X_{1}+\ldots+\beta_{p} X_{p}}}$$ , where $$X=\left(X_{1}, \ldots, X_{P}\right)$$ are $$p$$ is the number of predictors.

  * $$\log \left(\frac{p(X)}{1-p(X)}\right)=\beta_{0}+\beta_{1} X_{1}+\ldots+\beta_{P} X_{P}$$ 

* F: _What are the advantages of logistic regression over SVMs?_
  * _When classes are \(nearly\) separable, SVM does better than logistic regression._ \(-\)
  * _When not, logistic regression with \(ridge penalty\) and SVMs are very similar._\(+\)
  * If probability estimates are need, logistic regression is the best choice. \(+\)
  * logistic regression is fast and very easy to interpret. Good as baseline. \(+\)
  * Kernels in logistic regression are computationally expensive \(-\)
* F: _What is the effect on the coefficients of logistic regression if two predictors are highly correlated?_
  * A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* F: _Calculate the probabilities of the credit card example using logistic regression model._
  * _See script p. 18._

## Classification Evaluation

* F: _Draw a confusion matrix. Include the metrics, that are inside the cells._ 
  * ![](../.gitbook/assets/confusion_matrix.svg) 
* F: _Define precision / recall / sensitivity / False Positive Rate._ 
  * ![](../.gitbook/assets/grafik%20%283%29%20%281%29%20%281%29%20%282%29%20%282%29%20%285%29%20%285%29%20%285%29%20%281%29.png) 
* F: _Give an intuition for precision / recall / sensitivity..._ 
  * **Accuracy**: The share of instance that are correctly classified
  * **Precision**: Of examples recognized as cat, what % are actually cats? 95 % means: When classifier says 'cat', in 95 % it is a cat.
  * **Recall:**  Of all images that really are cats, what % were correctly recognized? Of all cats in the data, the classifier pulled 90 % of them. \(BDA lecture, slide 43\)
* F: _Is it better to have many false positives or too many false negatives?_
  * \([See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)\)
* F: _How can a standard_ $$2 \times 2$$ _confusion matrix be enhanced for a multi-classification case?_ 
* F: _What is an imbalanced dataset in classification?_ ⭐
  * A classification data set where class proportions are screwed. A class is called majority class, if it makes up a large proportion of the data set. Classes that make up a small proportion are called minority classes. [\(see here.\)](https://developers.google.com/machine-learning/data-prep/construct/sampling-splitting/imbalanced-data)
* F: _How do you deal with imbalanced data in classification?_
  * _An effective way to treat imbalanced data is to downsample and upweight the majority class._ 
  * _Downsampling means training on a disproportionally low subset of the majority class examples._
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
  * Training error \(error of learning method on seen data\) is quite different from test error rate, and in particular the former can be quite different from the test error rate and in particular the former can underestimate the latter.
  * One reason to use a separate test set is to avoid overfitting.
* F: _Explain what precision and recall are. How do they relate to the ROC-Curve?_
  * \([see here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)\)
* F: Explain what a ROC curve is.
  * A ROC curve is a diagnostic tool to investigate a classifier with different threshold values and the effect on the true positive rate and the false positive rate. It allows to select the best parameter combinations of the classification model.
* F: _Draw a ROC curve._
  * ![](../.gitbook/assets/roc-draft-xkcd-style.svg) 
* F: _How can a ROC curve be enhanced to multi-class model?_
  * We plot n number of ROC curves for n classifiers using a One vs. All methodology. So for example, if you have three classes named $$X$$, $$Y$$ and Z, another ROC for y classified against X and Z, and the third one of Z classified against Y and X.
* F: _Derive a receiver operating characteristic \(ROC\) Curve from classification results._
  * \(see exam St. Andrews\)
* F: _Interpret a ROC Curve._ 
  * A line close to the diagonal indicates the result of a random guess.
  * A perfect classifier would yield a point in the upper left corner at \(0,1\). 
* F: What is AUC?
  * AUC stands for Area under the Curve and measures the entire two-dimensional area underneath the entire ROC curve from \(0,0\) to \(1,1\). \([see here.](https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc)\)
  * It can be seen as the probability that a model ranks a random positive example more highly than a random negative example.
* F: How can AUC be interpreted?
  * AUC ranges from 0 to 1. 
  * A model, that gets all predictions wrong has an AUC of 0.
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
* F: _How is Kappa statistic defined?_  
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
* F: _How is the_ $$F_1$$ _measure defined?_ 
  * $$F_{1}=\frac{2}{\frac{1}{\text { precision}}+\frac{1}{\text { recall }}}=2 * \frac{\text { precision } * \text { recall }}{\text { precision }+\text { recall }}$$ 
* F: _Give an intuition for the_ $$F_1$$ _-measure._
  * _Combined measure of precision and recall to take trade-off into account._
  * $$F_1$$ _is the harmonic mean between precision and recall._
* F: _What values can a_ $$F_1$$ _measure take?_ 
  * $$F_1$$ is at max 1, if precision and recall are perfect.
  * $$F_1$$ is 0, if either precision or recall is 0.
* F: _In which way does the_ $$F_1$$ _-measure improve over simpler measures like accuracy?_
  * $$F_1$$ measure is useful if costs for false positives or false negatives are different e. g. prediction of illness
  * $$F_1$$ is useful when data is imbalanced.
  * However, accuracy is easier to interpret. \([see here.](https://deepai.org/machine-learning-glossary-and-terms/f-score)\)
* F. _How to access model performance? Name four criteria._
  * Speed 
  * Interpretability
  * Robustness \(the ability of the classifier to classify noisy data or data with missing values.\)
  * Scalability \(the ability of the classifier to work with a large amount of data.\)
* F: _What kinds of datasets are difficult for a linear classifier to correctly classify?_
  * _moon-shaped_
  * _circular or interwoven shapes_

## Cross-Validation

* F: What is commonly understood under resampling methods?
  * Resampling methods involve repeatedly drawing samples from a training set and refitting a model of interest on each sample in order to obtain additional information about the fitted model.
  * One example is the Cross-Validation method.
* F: Name important resampling methods.
  * Cross-Validation
    * Validation Set approach / Hold-Out-method
    * K-Fold cross-validation
    * Leave-One-Out Cross-Validation
    * Purged K-Fold Cross-Validation
    * Embargoed K-Fold Cross-Valdiation
  * Bootstrap Resampling.
* F: _Name at least techniques four for cross-validation._
  * Validation Set approach / Hold-Out-method
  * K-Fold cross-validation
  * Leave-One-Out cross-validation
  * Purged K-Fold cross-validation
* F: _What is the motivation to use resampling methods such as cross-validation?_  
  * Better estimates of variability of fitting a model on different samples of the test data opposed to fitting a model only once on an original training example.
* F: _What are drawbacks of resampling approaches?_ 
  * Computational complexity, as they involve fitting the same statistical method multiple times using different subsets of the training data.
* F: _What is the difference between test and training error?_
  * _The test error is the average error that results from using a statistical learning method to predict the response on a new observation, one that was not used in training the method._
  * _The training error is the average error of a statistical learning method on seen data. It's used to get an unbiased estimate of how good the model does._
  * _Error of the final model on training data is biased, since the data is used to select the model._
  * ![](../.gitbook/assets/model_complexity_error_training_test.jpg) 
  * Model complexity decreases prediction error until a point \(the bias trade-off\) where we are adding just noise. The train error goes down, but the test error is starting to go up. That's overfitting. One want's to find the model with the smallest test error.
* F: What is the difference between variance and bias?
  * **Bias** is the amount that a model's prediction differs from the target due to simplifying assumptions a model makes to approximate a target function. Can be resolved using resampling methods.
  * **Variance** indicates how much the estimate of the target function differs from its expected value. Variance measures the inconsistency of different predictions if different training data is used.
  * If a model is too simple and has few parameters, then it may have high bias and low variance. For models with many parameters, it has high variance and low bias. 
  * In ML we strike for a low bias and variance.
* F: _What are bias and variance, and what are their relation to modeling data?_
  * [\(See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)\)
* F: _Explain the validation set approach?_ 
  * In this method, the original data is randomly divided into a **train set** and a **validation** or **hold-out set**.
  * The model is fitted on the **training set**.
  * The fitted model is then used to predict the response for observations on the **validation set**.
  * Test error is estimated on the **test set**.
* F: _What is the advantage/disadvantage of the hold-out method?_
  * _simple \(+\)_
  * Data is often scarce. So we can not afford to set aside test sets \([see here.](http://www.columbia.edu/~mh2078/MachineLearningORFE/ResamplingMethods.pdf)\).
  * Performance on the validation set is a  \(often highly variable\) random variable depending on the data-split into training and validation sets. \(-\)
  * In the validation approach, only a subset of the observations those that are included in the training set rather than in the validation set are used in fitting the model \(-\)
  * The error on the validation set tends to over-estimate the test-error rate on small data sets, as models perform worse when trained on few data. \(see [here.](https://rstudio-pubs-static.s3.amazonaws.com/65561_43c0eaaa8565414eae333b47038f716c.html)\) \(-\)
* F: _Explain_ $$k$$_-fold cross-validation._ 
  * k-fold cross-validation randomly divides data into $$K$$ equal-sized parts.
  * We leave out part $$k$$, fit the model to the other $$K-1$$ parts \(combined\), and then obtain predictions for the left-out $$k$$ -th part.
  * This is done in turn for each part $$k = 1,2, \cdots, K$$, and then the results are combined.
* F: _Explain the Leave-One-Out Cross-Validation._ 
  * Leave -One-Out validation divides data into $$K$$ parts with $$K=N$$. That means every single observation used to test the model.
  * We leave out part $$k$$, fit the model to the other $$N-1$$ parts \(combined\), and then obtain predictions for the left-out $$k$$ -th part.
  * This is done in turn for each part $$k = 1,2, \cdots, N$$, and then the results are combined.
* F: _What is the advantage/disadvantage of_ $$k$$_-fold CV?_
  * Very little bias, as the model has been trained on multiple data constellations. \(+\)
  * Computationally very expensive, as training of the model happens multiple times \(-\)
  * Can not prevent data leakage \(-\)
* F: _What is the motivation to perform **purged**_ $$k$$_**-Fold cross-validation.**_ 
  * Observations can e. g. in finance often not assumed to be drawn from an IID process. Leakage takes place when the training set contains information that also appears in the testing set. \(see e. g. stock quotes, where market information is priced in from the previous days\)
  * One way to reduce leakage is to purge from the training set all observations whose labels overlap in time with those labels included in the testing set. 
* F: How does purged $$k$$-Fold cross-validation work?⭐

  * de Padro describes it[ here.](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3257420) Consider a label $$Y_{j}$$ that is a function of observations in the closed range $$t \in\left[t_{j, 0}, t_{j, 1}\right], Y_{j}=f\left[\left[t_{j, 0}, t_{j, 1}\right]\right]$$ .
  * For example, in the context of the triple barrier labelling method, it means that the label is the sign of the return spanning between price bars with indices $$t_{j, 0}$$ and $$t_{j, i}$$, that is $$\operatorname{sgn}\left[r{t_{j, 0}, t_{j, 1}}\right]$$. 
  * A label $$Y_{i}=f\left[\left[t_{j, 0}, t_{j, 1}\right]\right]$$ overlaps with $$Y_{j}$$ if any of the three sufficient conditions is met:

  $$
  t_{j, 0} \leq t_{i, 0} \leq t_{j, 1} ; t_{j, 0} \leq t_{i, 1} \leq t_{j, 1} ; t_{i, 0} \leq t_{j, 0} \leq t_{j, 1} \leq t_{i, 1}
  $$

* F: What is the motivation for **embargoed K-Fold CV**?
  * Since financial features often include series that exhibit serial correlation \(like ARMA\) processes, we should eliminate from the training set observations that immediately follow an observation in the testing set. This process is called embargo. [\(see here.\)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3257420)
  * ![](../.gitbook/assets/purged_embargo_cv.png) 
* F: _How should we divide data into training and testing for a time series dataset?_ ⭐
  * When choosing models, it is common practice to separate the available data into two portions, training and test data, where the training data is used to estimate any parameters of the forecasting method, and the test data is used to evaluate its accuracy. The test set is typically about 20% of the total sample. \([see here.](https://otexts.com/fpp2/accuracy.html)\)
  * For time series cross-validation using a rolling window approach is commonly used. That means, a small subset of consecutive data serves for **training,** forecasting the **consecutive** data points, that are part in **the test set**. As the training set only includes observations prior to the observations in the test set, no future observations are used for forecasting. The same forecasted data points are then included as part of the next training dataset and subsequent data points are forecasted. \([see here.](https://medium.com/@soumyachess1496/cross-validation-in-time-series-566ae4981ce4)\) \([see here.](https://otexts.com/fpp2/accuracy.html)\)
  * Sometimes a separate validation set to tune the hyperparameters of the model is used.
  * ![](../.gitbook/assets/grafik%20%2843%29.png) 
  * Blue Points are used for training red points are used for testing.
  * **TODO:** Sketch in lecture looks different. However, it's not clear, what's the difference between the blue and green dots. Probably train and validation set. Rolling window with the variable size vs. fixed size?
* F: _Explain what bootstrap is._ 
  * Bootstrap is a flexible and powerful statistical tool can be used to quantify the uncertainty with a given estimator or statistical learning method. \([see here.](http://www.columbia.edu/~mh2078/MachineLearningORFE/ResamplingMethods.pdf)\)
  * Bootstrap relies on resampling the data many times to compute some measure of variability.  Sample data is repeatedly drawn with replacement from a data source to estimate a population parameter. \([see here.](https://datamites.com/blog/resampling-methods-in-machine-learning/)\)
  * The bootstrapped data sets are the same size as the original data set. That's why some observations appear more than once in a given bootstrap data set or not at all. 
* F: _Why is bootstrapping used? Why is bootstrapping desirable?_ 
  * It's used, if analytic measures of variability are not available \(or not automatically output by statistical software\) 
  * Large scale resampling can be easily done on modern computers \(+\) \([see here.](http://www.columbia.edu/~mh2078/MachineLearningORFE/ResamplingMethods.pdf)\)
  * Bootstrapping doesn't assume a parametric distribution \(+\) \([see here.](https://stats.stackexchange.com/questions/280725/pros-and-cons-of-bootstrapping/280728)\)
  * A bootstrap sample can only tell about the original sample, but won't give any insights on the real population. \(-\) \([see here.](https://stats.stackexchange.com/questions/280725/pros-and-cons-of-bootstrapping/280728)\)
* F: _How should we tune parameters for machine learning models?_ ⭐
  * Hyper parameter tuning should happen using validation set which is solely used for tuning different models/hyperparameters.
  * Testing should still happen on the testing set and training on the training set.
  * To find the best parameter combinations a systematic approach such as grid search should be used.
  * If grid search is not possible for computational reasons a randomized search might help.
* F: Compare the Hold out Validation, to Leave-One-Out Cross-Validation, $$k$$ -Fold cross-validation and Bootstrap.
  * Adapted from [here](https://datamites.com/blog/resampling-methods-in-machine-learning/).

    | **Hold out Validation** | **Leave-One-Out Cross-Validation** | **k-Fold Cross-Validation** | **Bootstrap** |
    | :--- | :--- | :--- | :--- |
    | Use it when data have less features | Medium-sized dataset | Large dataset with large features | Use it with any shape of data |
    | High chance of bias | Less bias | Good bias and variance tradeoff | Good bias and variance tradeoff |
    | High chance of overfitting | Generalized model | Generalized model | Generalized model |

## Dimensionality Reduction

* F: _Give the definition for PCA._
* F: _What does dimensionality reduction mean?_ 🧠
  * Dimensionality reduction is simply, the process of reducing the dimension of your feature set. e. G. from a hypersphere to some spherical shape. This is commonly done to fight the curse of dimensionality. \([see here.](https://towardsdatascience.com/dimensionality-reduction-for-machine-learning-80a46c2ebb7e)\)
* F: _What are the advantages and disadvantages of dimensionality reduction?_
  * **Advantages:**
    * It helps in data compression, and hence reduces storage space
    * It reduces computation time.
    * It helps remove redundant features, if present
  * **Disadvantages:**
    * May lead to some amount of data loss.
    * PCA tends to find linear correlations between variables, which is sometimes not desirable.
    * PCA fails in cases where mean and covariance are not enough to define datasets.
* F: _What is PCA commonly used for?_
  * Produce a **low-dimensional representation** of the dataset. It finds a sequence of linear combinations of variables with **maximal variance** and are **mutually uncorrelated**.
  * ![](../.gitbook/assets/1-v3jwbvxb92uo116bpxa3tw.png) 
* F: _What are the advantages of sparse PCA over PCA?_⭐
  * Sparse PCA allows for a better interpretation of the economic meaning of each principal component. When having a large number of variables with non-zero factor loadings it's hard to interpret them with ordinary PCA, as PCs are a linear combination of all $$p$$ variables.
  * By applying an $$\ell_{1}$$ and an $$\ell_{2}$$ penalty \(Elastic Net\) to the coefficients of the PCA regression formulation, sparse principal components can be estimated.
  * Compared to SCoTLASS it is computationally efficient.
* F: _Intuition about sparse principal component analysis?_
  * SPCA is built on the fact that PCA can be written as a regression-type optimization problem, with a quadratic penalty; the lasso penalty \(via the elastic net\) can then be directly integrated into the regression criterion, leading to a modified PCA with sparse loadings.
* F: _Explain the \(standard\) PCA._
  * TODO: Welche Variante ist hier besser? Kommt zwei mal ähnlich in Folien vor.
* F: _What are three things, that PCA does?_ 🧠
  * PCA projects data into linear subspace
  * PCA maximizes the variance of projection
  * PCA minimizes the error of reconstruction
* F: _What are the roles of the Eigenvectors and Eigenvalues in PCA?_ 🧠
* F: _Can you describe applications of PCA?_ 🧠
* F: _Explain the sparse PCA._
  * By applying an $$\ell_{1}$$ and an $$\ell_{2}$$ penalty to the coefficients of the PCA **regression formulation**, sparse principal components can be estimated.
* F: _Explain the nonlinear PCA._
  * Nonlinear PCA uses an inconsistency index as information criterion to avoid overfitting in the choice of hyperparameters.
  * Nonlinear PCA uses an **auto-associative neural network** for calculation of the PCAs. Autoassociative neural networks have one input layer, three hidden layers, and one output layer. One of the hidden layers is a so-called "bottleneck layer". The input layer and output layer have a size of the feature space.
  * The network is trained to perform an **identity mapping**, where the input is approximated at the output.
  * Since the number of hidden neurons in the middle hidden layer is restricted to the number of bottleneck neurons, which are fewer than the output neurons, one effectively calculates the **principal components**.
  * The mean squared error \(MSE\) between the input layer and the output layer is minimized. In the process, the nonlinear principal components in the middle hidden layer, that is the bottleneck layer, are calculated. \(compare script + Kramer paper\)
* F: _Explain the kernel PCA._
  * Kernel PCA uses a nonlinear transformation $$\phi(X)$$from the original feature space into a higher dimensional feature space. Then standard PCA is applied in the higher dimensional feature space. The calculation requires the calculation of the dot product$$\phi(X)\phi(X)^{T}$$. Consequently, kernels can be used.
  * TODO: nachlesen, was Produkt einspart? [https://medium.com/@zxr.nju/what-is-the-kernel-trick-why-is-it-important-98a98db0961d](https://medium.com/@zxr.nju/what-is-the-kernel-trick-why-is-it-important-98a98db0961d)
* F: _Explain the major difference of sparse PCA over ordinary PCA._
  * Ordinary PCA with many variables with non-zero factor loadings make it difficult to interpret the economic meaning of each PC. 
  * Sparse PCA applies an elastic net regularization to the calculation of PCs. The $$L_1$$ and $$L_2$$penalty is applied to the coefficients in the PCA regression formulation to prevent overfitting of the coefficients.  
* F: _Explain the major difference of kernel PCA over non-linear PCA._
  * Kernel PCA doesn't require any nonlinear optimizations. So the danger of finding a solution that is a local minimum is eliminated. \(Nazemi et al. Improving corporate bond recovery p. 5\)
* F: _Explain the major difference of non-linear PCA over ordinary PCA._
* F: _Explain the major difference of kernel PCA over ordinary PCA._
  * Kernel PCA doesn't require a non-linear optimization.
  * Kernel PCA transforms features into higher dimensional feature space first, before applying PCA.
* _F: What is the purpose of the measure **proportion variance explained**?_
  * In order to understand the strength of each component, one needs to know the proportion of variance explained by each one.
* F: _How can the proportion of variance explained by_ $$m$$ _variables be calculated?_
  * The total variance of a data set is defined as: 
  * $$\sum_{j=1}^{P} \operatorname{Var}\left(X_{j}\right)=\sum_{j=1}^{P} \frac{1}{n} \sum_{i=1}^{n} x_{i j}^{2}$$
  * where $$P$$is the number of features and $$n$$is the number of observations.
  * The variance explained by the \(m\) principal components is defined as: $$\operatorname{Var}\left(P C A_{m}\right)=\frac{1}{n} \sum_{i=1}^{n} p c a_{i m}^{2}$$ 
  * Therefore, the proportion of variance explained of the \(m\) th principal component is given by the positive quantity between 0 and 1
  * $$\frac{\sum_{i=1}^{n} p c a_{i m}^{2}}{\sum_{j=1}^{P} \sum_{i=1}^{n} x_{i j}^{2}}$$ 
  * TODO: What does P, n etc. stand for?
* _F: What scaling should be applied before doing a PCA?_
  * If variables are in different units, scaling each to have a standard deviation equal to one is recommended. \(script p. 16\)
  * Normalizing data is important in PCA, as it's a variance maximizing exercise. It projects original data onto directions that maximize the variance. If some variables have a large variance and some a small, PCA will load on the large variables. This might want to be avoided. \([see here.](https://stats.stackexchange.com/questions/69157/why-do-we-need-to-normalize-data-before-principal-component-analysis-pca)\) 
* F: _Calculate the PCA for the first two components for a given example._
* F: _Sketch the algorithm for calculating the first two PCA components._
  * Suppose we have a $$n \times p$$ data set $$X$$. Since we are only interested in variance, we assume that each of the variables in $$X$$ has been centered to have mean zero \(that is, the column means of $$X$$ are zero\).
  * We then look for the linear combination of the sample feature values of the form

    $$P C A_{i 1}=\phi_{11} X_{i 1}+\phi_{21} X_{i 2}+\ldots+\phi_{P 1} X_{i P}$$

    for $$i=1, \ldots, n$$ that has largest sample variance, subject to the constraint that $$\sum_{j=1}^{p} \phi_{j 1}^{2}=1$$.

  * Since each of the $$x_{i j}$$ has mean zero, then so does $$\text{PCA}_{i 1}$$ \(for any values of $$\phi_{j 1}$$ \). Hence the sample variance of the $$P C A_{i 1}$$ can be written as $$\frac{1}{n} \sum_{j=1}^{p} \text{PCA}_{i 1}^{2}$$.
  * Plugging into the last equation the first principal component loading vector solves the optimization problem maximize.

    $$\frac{1}{n} \sum_{i=1}^{n}\left(\sum_{j=1}^{P} \phi_{j 1} x_{i j}\right)^{2}\text{ subject to }\sum_{j=1}^{p} \phi_{j 1}^{2}=1$$

  * This problem can be solved via a singular-value decomposition of the matrix $$X$$, a standard technique in linear algebra.
  * We refer to $$\text{PCA}_{1}$$ as the first principal component, with realized values $$\text{pca}_{11}, \ldots, \text{pca}_{n1}$$
  * The second principal component is the linear combination of $$X_{1}, X_{2}, \ldots, X_{P}$$ that has **maximal variance** among all linear combinations that are **uncorrelated** with $$\text{PCA}_{1}$$. 
  * The second principal component scores $$z_{12}, z_{22}, \ldots, z_{n 2}$$ take the form

    $$\text{PCA}_{i 2}=\phi_{12} X_{i 1}+\phi_{22} X_{i 2}+\ldots+\phi_{P 2} X_{i P}$$

    where $$\phi_{2}$$ is the second principal component loading vector, with elements $$\phi_{12}, \ldots \phi_{p 2}$$.

  * It turns out that constraining $$\text{PCA}_{2}$$ to be uncorrelated with $$\text{PCA}_{1}$$ is equivalent to constraining the direction $$\phi_{2}$$ to be orthogonal to the direction $$\phi_{1}$$.
* F: _Explain what **Principal Component Regression** is._
  * One extracts principal components as features and then models the target \(response variable\) as a linear function of these Features. That means, the response variable responds indirectly and linearly to changes in the inputs.

## Decision Trees

* F: _Explain what a decision tree is._
  * A decision tree is a supervised learning algorithm that can be used for regression and classification. 
  * Decision Trees try to predict the class or a value of the target by stratifying or segmenting the predictor space into several simple regions.
  * There are several measures to learn these splitting rules required for splitting data in a node into separate nodes. One of them is the entropy.
* F: _Mention three impurity measures?_ 
  * resubstitution error
  * Gini-Index
  * Entropy
* F: _What is the intuition behind an optimal split in a decision tree?_
  * A split should lead to a subset that contains predominantly cases of one class.
  * That means nodes should only contain cases of a single class only or homogenous.
* F: _Name 3 conditions an impurity measure has to fulfill._ ⭐
  1. _An impurity measure of a node should be at a maximum when the observations are distributed evenly over all cases in that node, i. e. at:_ $$\left(\frac{1}{J}, \frac{1}{J}, \ldots, \frac{1}{J}\right)$$ 
  2. An impurity measure of a node should be at minimum when all observations belong to a single class in that node, i. e. at $$(1,0, \cdots, 0),(0,1,0, \cdots, 0), \cdots,(0,0, \cdots, 1)$$ 
  3. $$\phi$$ is a symmetric function of $$p_{1}, \ldots, p_{J}$$.
* F: _How can we influence the model complexity of the tree?_ 🧠
* F: _Compare the Gini-Coefficient to Entropy and the resubstitution error._
  * **Resubstitution Error:** $$i(t)=1-\max _{j} p(j \mid t)$$, where where $$p(j \mid t)$$ is the relative frequency of class $$j$$ in node $$t$$.
  * **Gini-Index:** $$i(t)=\sum_{j} 2 p(j \mid t)(1-p(j \mid t))$$
  * **Entropie:** $$i(t)=-\sum_{j} p(j \mid t) \log p(j \mid t)$$
    * ![](../.gitbook/assets/grafik%20%2845%29.png) 
* F: _When should the Gini-Coefficient be used? When is it desirable to use the Entropy? How does the misclassification error compare?_
  * From Hastie p. 309 f.: cross-entropy and Gini index are differentiable, and hence more amenable to numerical optimization as setting equal with 0 is possible.
  * Gini index and cross-entropy are more sensitive to changes in the node probabilities than the misclassification rate. For example, in a two-class problem with 400 observations in each class \(denote, this by \(400,400\)\), suppose one split created nodes \(300,100\) and \(100, 300\), while the other created nodes \(200, 400\) and \(200,0\). Both splits produce a misclassification rate of 0.25, but the second split produces a pure node and is probably preferable. Both the Gini index and cross-entropy are lower for the second split.
  * That means either Gini index or cross-entropy should be used when growing a tree.
  * To guide cost-complexity pruning, any of the three measures will do.
* _F: Explain how numerical features can be split?_
  * If  $$x_{1}, x_{2}, \ldots, x_{p}$$ are a set of numeric variables, we consider all splits of type $$x \leq c$$ for all $$c$$ ranging over $$(-\infty, \infty)$$.
  * If all all observations have a different value, we have at most n distinct values $$x_{1}, x_{2}, \cdots, x_{n}$$ of $$x$$. Which means there are at max. $$n-1$$ distinct splits of type $$m=1, \ldots, n \leq n$$, where $$m=1, \ldots, n \leq n$$ , where $$c_m$$ are taken **halfway** between **consecutive** distinct values of $$x$$ .
* F: H_ow can categorical attributes be handled?_
  * TODO: + Folie 23
  * Alternatively, variables can be label-encoded and treated as numeric variables. \([see here.](https://towardsdatascience.com/decision-trees-d07e0f420175)\)
* F: _How can continuous attributes be handled in Decision Trees?_ ⭐
  * **Alternative answer:** It's necessary to discretize continuous values. One could either use:
    1. Comparison operator, which separates into two classes by a threshold. The threshold could be chosen by:
       1. brute force: trying out every single value of continuous variables
       2. sorting values for continuous attributes and taking the midpoint of the adjacent values in the sorted array. See here:
       3. ![](../.gitbook/assets/grafik%20%2847%29.png) 
    2. Split continuous values into bins. One would get multi-way splits. Splitting into bins could happen by frequency or width. \(comp. Equi-width histograms vs. equi-depth histogram\) [\(see here.\)](https://medium.com/geekculture/handling-continuous-attributes-in-decision-trees-bbc044986621)
  * TODO: like numerical attributes
* F: _Explain how numerical features can be split?_
  * Assuming there are at most n distinct values of x. There are at most $$n-1$$ distinct splits of type $$x \leq c_m$$, where $$c_m$$ are taken halfway between consecutive distinct values of $$x$$ 
* F: _What is the motivation to prune a decision tree?_
  * Pruning is done to avoid overfitting. The tree learns the data by heart, but new data can be different. Therefore, it makes sense to cut back the tree to deliver good results on unseen data.
  * Pruning reduces the size of a decision tree by removing not-relevant attributes from the tree / cutting back the tree. \(AGD\) 
  * A smaller tree with fewer splits might lead to lower variance and better interpretation at the cost of a little bias.
* _F: How does pruning a using minimal-cost complexity decision tree works?_
  * A very large tree $$T_0$$ is grown and then cut back afterward.
  * Since the tree can be tested while cutting it down, it could lead to favourable results. 
  * It defines a measurement called cost-complexity measurement, for a dataset X and a tree T where \|T\| defines the amount of terminal nodes:
  * $$
    \sum_{m=1}^{|T|} \sum_{x_{i} \in R_{m}}\left(y_{i}-\hat{y}_{R_{m}}\right)^{2}+\alpha|T|
    $$
  * $$\alpha$$ is a non-negative tuning parameter and is called the complexity parameter. $$R_m$$ ist the rectangle \(i. e. the subset of predictor space\) corresponding to the $$m$$-th terminal node, and $$\hat{y}{R{m}}$$ is the mean of training observations in $$R_m$$ .
  * $$\alpha$$ is usually selected using cross-validation.
  * When pruning the tree the algorithm tries to minimize this measure. Its obvious that a large number of nodes in a subtree is punished for a high value of $$\alpha$$. Therefore the algorithm will search for subtrees with high misclassification error or high number of nodes. Of course, it is complicated looking at the number of nodes since it is heavily dependent on the number of attributes in $$T$$. Hence there has to be the parameter $$\alpha$$ in order to find the right punishment for large tree sizes.  [\(see here.\)](https://www5.in.tum.de/lehre/seminare/datamining/ss17/paper_pres/08_decision_tree/paper.pdf)
* F: _Explain how growing a decision tree works?_
  1. At each node, split the data into two leaf nodes
  2. Splits are chosen using a binary splitting criterion e. g. cross-entropy.
  3. We stop when each terminal node has fewer than some minimum number of observations.
  4. TODO: Replace by algorithm on page 27.
* F: _How can decision trees be applied to a regression case?_
  * The predicted value of a node is the average response variable for all observations in that node.
* F: _Name several advantages/disadvantages of decision trees_
  * Easy to interpret, if trees are small.
  * Competitive in terms of accuracy.
  * Inexpensive to construct.
* F: _What are the advantages of decision trees over random forests?_ ⭐
  * easier to explain \(+\) 
  * computationally simpler and quicker to fit than random forests \(+\)
  * less robust than random forests. If we change the data for a decision tree a little, the tree can change a lot. Interpretation is not as straightforward as it seems. \(-\)
  * Most of the time random forests achieve better accuracy, as they are trained on random sub samples. This, however, comes at the expense of loss interpretation. \(-\)
* _F: What are tuning parameters for Decision Trees?_
  * _TODO: alpha, impurity measure, min entries per node_
* _F: disadvantages and advantages of trees?_
  * _TODO: p. 28_

## Bagging, Boosting, and RF

* F: _What ensemble techniques can be applied?_
  * _Bagging_ 
  * _Boosting_
  * _Random Forests_
* F: _What is an ensemble algorithm?_ 
  * Ensemble methods are meta-algorithms that combine several machine learning techniques into one predictive model in order to decrease variance \(**bagging**\), bias \(**boosting**\) or  improve predictions \(**stacking**\). \([see here.](https://blog.statsbot.co/ensemble-learning-d1dcd548e936)\)
* F: _Explain what Bagging is._
  * Bootstrap aggregating or bagging is an ensemble technique designed to improve stability and accuracy of ML algorithms for classification and regression.
  * In the regression case bagging fits a $$\hat{f}_{b}(x)=\hat{\beta}_{b} X_{b}$$ regression model to $$b$$-th bootstrap samples $$X_b$$ and then bagging takes the mean of these estimation over a collection of bootstrap samples. The bagging estimator is made in the following form:
  * $$f_{\text {Bagging }}(X)=\frac{1}{B} \sum_{b=1}^{B} \hat{f}_{b}(X)$$
* F: _How does Bagging work for regression?_
  * Each bootstrap regression tree will include different nodes. The bagging estimator is the **mean** of these $$B$$ regression tree predictions.
* F: _How does Bagging work for classification?_
  * For each test observation we record the class predicted by each of the $$B$$ trees, and take a **majority vote**. That means the overall prediction is the most commonly occurring class among the  $$B$$ predictions.
* F: _What are tuning parameters for Bagging?_
  * The number of bootstrap samples/regression trees over which the mean or majority vote is estimated.
* F: _Explain the intuition of Boosting._
  * Boosting tries to improve predictive performance by combining several weak learners \(e. g. simple trees\) which are trained sequentially on the data. The error is analyzed. In every step, consecutive weak learners are fitted, so that the accuracy is increased. \([see here.](https://analyticsindiamag.com/primer-ensemble-learning-bagging-boosting/)\)
* F: Explain how Boosting works in natural language.
  * Boosting is used to create a collection of predictors.  In this technique, learners are learned sequentially with early learners fitting simple models to the data and then analyze data for errors. Consecutive trees \(random sample\) are fit at every step, the goal is to improve the accuracy of the prior tree \([see here](https://analyticsindiamag.com/primer-ensemble-learning-bagging-boosting/).\)
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
  * TODO: Gradient Boosting nachlesen in Hasties.
* F: _What are tuning parameters for Boosting?_ ⭐
  * **number of trees** $$B$$. Unlike bagging and random forests, boosting can overfit if $$B$$ is too large, although this overfits tends to occur slowly, if at all. We use cross-validation to select B.
  * The **shrinkage parameter** at which boosting learns. Typical values are 0.01 or 0.001 and the right choice depends on the problem. Very small shrinkage parameter can require using a very large value of B in order to achieve good performance.
  * TODO: Aussage der Learning rate
  * The **number of splits** $$d$$ in each tree, which controls the complexity of the boosted ensemble. Often $$d=1$$ works well, in which case each tree is a stump, consisting of a single split resulting in an additive model. More generally d is the interaction depth, and controls the interaction order of the boosted model since $$d$$ splits can involve at most $$d$$ variables.
* F: _How does Bagging differ from Boosting? Explain the difference._
  * **Bagging:** 
    * Goal is to achieve minimum variance
    * Bagging combines the results of multiple models to a generalized result through voting or averaging. 
    * The trees are built in parallel on bootstrap samples, which is data chosen with replacement from the original data.
    * Equal weight is given to all models
  * **Boosting:** 
    * Goal is to increase accuracy/decrease bias 
    * Boosting is a sequential process, where each subsequent model attempts to correct the errors of the previous model. That means succeeding models are dependent on previous models \([see here.](https://medium.com/swlh/difference-between-bagging-and-boosting-f996253acd22)\)
    * Weights a model's contribution by its performance.
  * Visualization:
    * ![](../.gitbook/assets/grafik%20%2846%29.png) 
* F: What are the similarities between bagging, random forests, and boosting algorithms.
  * Like random forests, boosting algorithms are an ensemble of many different models with high inter-group diversity.
  * Boosting algorithms also aggregate the predictions of each constituent model into an overall prediction. 
  * Both algorithms make use of tree models. However, Boosting can also combine other weak learners. \([see here.](https://medium.com/@toprak.mhmt/gradient-boosting-and-weak-learners-1f93726b6fbd)\)
* F: _What is the main advantage and disadvantage of a random forest over a decision tree?_ ⭐
  * A: [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* F: _Compare Boosting trees to Random Forests. What are the differences?_
  1. random forest algorithm uses a **small random subset** of explanatory variables for growing in each particular tree while boosting selects from a **complete list of explanatory** **variables** for growing the best classification tree.
  2. Boosting trees sequentially depend on the error rate of the previous iteration, while random trees can be built independently at each iteration.
  3. In random forests each tree is a strong learner. They would do just fine as a decision tree on their own. In boosting algorithms, trees are artificially limited to very shallow depth \(usually only one split\), to ensure that each model is only slightly better than random chance. \([see here](https://medium.com/@toprak.mhmt/gradient-boosting-and-weak-learners-1f93726b6fbd).\)
* F: _Compare Bagging and Random Forest?_
  * TODO: findet auch Auswahl auf Datensatz statt oder nur random feature selection?
* F: _Explain what a Random Forest is?_
  * A random forest is an **advanced variant of bagging**. It fits a large set of classification trees, and then classifies using the majority of the classes of built classification trees. 
  * Random forests use a small **random subset of explanatory variables** for growing in each particular tree.
* F: _When can it be advantageous to use Random Forests over Decision Trees?_
  * _Better accuracy \(+\)_
  * _Reduced variance \(+\)_
  * _More difficult to interpret \(-\)_
* F: _What are tuning parameters for Random Forests?_
  * Number of trees
  * Number of predictors used to build each tree
* _F: Give on example for an ensemble algorithm from the class of an ensemble model that gave improved performance over a base model._
  * random forests and boosting used to predict defaults for commercial real estate property loans.

## k-means clustering

* F: _Explain the_ $$k$$_-means clustering algorithm_ ⭐

  1. Randomly assign a number, from $$1$$ to $$K$$ to each of the observations. These serve as initial cluster assignments for the observations. 
  2. Iterate until the cluster assignments top changing:
     * for each of the $$K$$ clusters, compute the cluster centroid. The $$k$$th cluster centroid is the vector of the $$p$$ features means for the observations in the $$k$$th cluster.
     * Assign each observation to the cluster whose centroid is closest \(where closest is defined using Euclidean distance\).

  To achieve faster convergence, one can use an improved initialization of cluster centeres. One approach is **k-means++**.

  More formal definition:

  1. Pick $$K$$ arbitrary cluster centers
  2. Assign each sample to its closest centroid $$z_{n}=\arg \min {k}\left|\boldsymbol{c}_{k}-\boldsymbol{x}_{n}\right|^{2}$$ 
  3. Adjust the centroids to be the means of the samples assigned to them $$\boldsymbol{c}_{k}=\frac{1}{\left|X_{k}\right|} \sum{\boldsymbol{x}_{i} \in X_{k}}  \boldsymbol{x}_{i}, X_{k}= \{\boldsymbol{x}_{n} z_{n}=k \}$$ 
  4. Goto step 2 until no change

* F: What properties do sets of clusterings satisfy?
  * Each observation belongs to at least to one of the $$K$$ clusters.
  * The clusters are non-overlapping, no observation belongs to more than one cluster.
* F: _What is the main idea of clustering?_
  * The idea behind $$k$$-means clustering is that a good clustering is one for which the within-cluster variation is as small as possible.
  * $$\operatorname{WCV}(C_k)$$ is the degree by which observations differ from each other within a cluster.

    Hence we want to solve the problem:

    * $$\operatorname{ minimize }\left\{\sum_{k=1}^{K} W C V\left(C_{K}\right)\right\}$$

    For Euclidean distance:

    * $$\operatorname{ minimize }\left\{\sum_{k=1}^{K} \frac{1}{\left|C_{K}\right|} \sum_{i, i^{\prime} \in C_{K}} \sum_{j=1}^{P}\left(x_{i j}-x_{i^{\prime} j}\right)^{2}\right\}$$
* F: _What is the main \(dis-\)advantage of the_ $$k$$_-means clustering algorithm?_ ⭐
  * Works in an unsupervised setting / doesn't require labeled data \(+\)
  * Relatively simple to implement \(+\)
  * Scales to large data sets \(+\)
  * Guarantees convergence \(+\)
  * warm-start the positions of centroids possible \(+\)
  * easily adapts to new examples \(+\)
  * generalize the clusters of different shapes and sizes, such as elliptical clusters. [\(see here.\)](https://developers.google.com/machine-learning/clustering/algorithm/advantages-disadvantages)
  * $$k$$-means clustering requires us to pre-specify the number of clusters. However, no of clusters is often not known \(-\)
* F: _What properties does a set has to fulfill when_ $$k$$_-means clustering should be applied._
  * Datasets with less noise
  * Spherical clusters of roughly the same size
  * Counter "mouse" example \([see here.](https://stats.stackexchange.com/questions/79741/data-sets-suitable-for-k-means)\)
  * ![](../.gitbook/assets/grafik%20%2848%29.png) 
* F: _What are alternatives to_ $$k$$_-means clustering?_
  * DBSCAN
  * Agglomerative Hierarchical Clustering
  * Birch \([see here.](https://towardsdatascience.com/the-5-clustering-algorithms-data-scientists-need-to-know-a36d136ef68) / AGD\)
* F: _How does minimizing the WCV relate to solving the clustering problem?_
* F: _Name distance measures, that can be used with in conjunction with_ $$k$$ _means. When should they be used._
  * _Euclidean distance_
  * _Manhattan distance_
  * _Average distance_
  * _Minkowski sum \(_[_see here\)_](https://storage.googleapis.com/plos-corpus-prod/10.1371/journal.pone.0144059/1/pone.0144059.pdf?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=wombat-sa%40plos-prod.iam.gserviceaccount.com%2F20210715%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20210715T194736Z&X-Goog-Expires=86400&X-Goog-SignedHeaders=host&X-Goog-Signature=04ede785d000ebd5f299bfbbab8c90d6eadccd88325d10335ed298244a0ecf7a930ab527d0c521cf7a014d40565bdaeec1721d2a96b9a8c02025c5a2d02a8c5cb315c9241feeff1e3e2e5faa8fb0d7df7a4093901e580a4454e37c51a1c63487e1cfdbb86243603498f00b69a242f76ee0ddb744f9e2555e15627fd23febc4dbac8107aa0ffef08b59a1923f71f8c214347c481256c4a769c830868d160f1cdb2fe75b8af9458875ec5a441e93729bb2896ced623dec5be33f41346fcef8188f47e8e3efe87c3424bfe2a3bac0a3446788d38c091052835476328901902840be36576b9b327ae8d12aebd783be1dafaefc5a5edf41a88d7280f23c90a8b80768)\_\_
* F: _What are the two main steps of_ $$k$$_-means?_ 🧠
  * Pick $$k$$ arbitrary cluster centers
  * Assign each sample to the closest centroid and adjust the centroids to be the means of the samples assigned to them.
* F: _Why does_ $$k$$_-means converge? What is it minimizing._ 🧠
  * We have only a finite number of possible values for the centroid.
  * Every assignment or adjustment step is reducing the SSD or remains constant.
  * TODO: More detailed in ML slides.
* F: _Does_ $$k$$_-means find a global minimum of the objective?_ 🧠
  * No, the objective \(see question above\) is an NP-hard problem, so we can't expect any algorithm to minimize the cost without essentially checking \(near to\) all assignments.
  * It heavily depends on the initialization of the centroids.
* F: _Why is clustering called unsupervised?_ 🧠
  * Clustering is an unsupervised machine learning task that automatically divides the data into clusters or groups of similar items. It does this without having been told how the groups should look ahead of time. As we may not even know what we're looking for, clustering is used for knowledge discovery rather than prediction. \([see here](https://hub.packtpub.com/introduction-clustering-and-unsupervised-learning/).\)
* F: _In unsupervised learning, if a ground truth about a dataset is unknown, how can we determine the most useful number of clusters to be?_
  * [See here.](https://github.com/iamtodor/data-science-interview-questions-and-answers)
* F: _When is clustering optimal?_
  * A clustering is optimal if the within-cluster variation \(summed over all Clusters $$K$$\) is as small as possible.
* F: _Draw a dendrogram from a given clustering._
  * ![](http://127.0.0.1:49726/paste-adaa6f08036c23cf81befcf5dda658803dcb008b.jpg)
  * ![](http://127.0.0.1:49726/paste-1510742dce8bacd2cfabfe464bc70dfd6d94ad8e.jpg)

    ![](http://127.0.0.1:50852/paste-1510742dce8bacd2cfabfe464bc70dfd6d94ad8e.jpg)
* F: _Explain how the algorithm for hierarchical clustering works._ 1. Begin with n observations and a measure \(such as Euclidean distance\) of all the $$\left(\begin{array}{c}n \\ 2\end{array}\right)=n(n-1) / 2$$ pairwise dissimilarities. Treat each observation as its own cluster. 2. For $$i=n, n-1, \ldots, 2$$
  * Examine all pairwise inter-cluster dissimilarities among the $$i$$ clusters and identify the pair of clusters that are least dissimilar \(that is, most similar\). Fuse these two clusters. The dissimilarity between these two clusters indicates the height in the dendrogram at which the fusion should be placed.
  * Compute the new pairwise inter-cluster dissimilarities among the $$i-1$$ remaining clusters.
* F: What is the purpose of linkage types?
  * To merge two clusters, one needs to take the distance between the \(existing\) clusters and therefore define the distance between two clusters.
* F: _Name and explain different linkage types, that can be used for clustering._
  * **Complete:** Maximal inter-cluster dissimilarity. Compute all pairwise dissimilarities between the observations in a cluster A and the observations in a cluster B, and record the largest of these dissimilarities. **Alternative:** Maximum distance between two points from the 2 clusters.
  * **Single:** Minimal inter-cluster dissimilarity. Compute all pairwise dissimilarities between the observations in cluster A and the observations in cluster B, and record the smallest of these dissimilarities. Single linkage can result in extended, trailing clusters in which single observations are fused one-at-a-time. **Alternative:** Minimum distance between two points from the 2 clusters.
  * **Average:** Mean inter-cluster dissimilarity compute all pairwise dissimilarities between the observations in cluster A and the observations in Cluster B,  and record the average of these dissimilarities. **Alternative:** Average distance between 2 pairs.
  * **Centroid:** Dissimilarity between the centroid for cluster A \(a mean vector of length p\) and the centroid for B. Centroid linkage can result in undesirable inversions. **Alternative**: Distance between the two centroids.
* F: _Draw different linkage types visually._
  * ![](http://127.0.0.1:49726/12Qo9ezWv8KRs8zRMKxh.png)
  * ![](http://127.0.0.1:49726/137Cmij89B1D5vvNh58X.png)

    ​
* F: _What is the impact of using different linkage types?_
  * \([see here.](https://stats.stackexchange.com/questions/195446/choosing-the-right-linkage-method-for-hierarchical-clustering)\)
  * ![](../.gitbook/assets/grafik%20%2849%29.png) 
* F: Name disadvantages of linkage types.
  * Single Linkage: Tends to build chains.
  * Complete Linkage: Tends to create small groups. \([see here](https://de.wikipedia.org/wiki/Hierarchische_Clusteranalyze).\)
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
  * recommender systems e. g. CF

## SVMs

* F: What is the motivation for SVMs?
  * We try to find a **plane** that separates the **classes in feature space**. If separating is not possible:
    * one **softens**, what is meant by separating
    * or **enrichens** or **enlargens** the **feature space** so that separation is possible.
* F: _Give an intuition of what an SVM is._ 
  * _With Support Vector Machines one maps the data into a higher dimensional input space and constructs an optimal separating hyperplane in this space. This involves solving a quadratic programming problem. \(Suykens Vandewalle p. 1\)_
* _F: Give the definition of a hyperplane_
  * a hyperplane in $$p$$ dimensions is an affine subspace of dimension $$p-1$$dimension.
  * The equation for a hyperplane is given by:
    * $$\beta_{0}+\beta_{1} X_{1}+\beta_{2} X_{2}+\ldots+\beta_{P} X_{P}=0$$
* F: _What is hyperplane in two dimensions? What in three dimensions?_
  * $$p=2$$: line
  * $$p=3$$: plane
* F: _What is the meaning of the vector_ $$\beta$$ _of a hyperplane?_
  * $$\beta=\left(\beta_{0}, \beta_{1}, \beta_{2}, \ldots, \beta_{P}\right)$$is the normal.
* F: How can a **hyperplane** be used for **classification**?
  * If $$f(x)=\beta_{0}+\beta_{1} X_{1}+\beta_{2} X_{2}+\ldots+\beta_{P} X_{P}$$, then $$f(x)>0$$ for points on one side of the hyperplane, and $$f(x)<0$$ for points on the other. 
  * That means one can classify test observations based on which side of the hyperplane it lies \(James et al.\)
* F: _Explain the **Maximal Margin Classifier**?_
  * A **Maximal Margin Classifier** is a classification approach, where one tries to find a hyperplane of all possible hyperplanes, that gives the biggest gap between the two classes. This hyperplane is called the **maximal margin hyperplane**. The smallest distance between the hyperplane and training observations is called margin. 
  * Finding the maximal margin hyperplane is a constrained optimization problem, which can be formulated as follows.
  * Based on a set of $$n$$ training observations based on a set of $$n$$ training observations $$x_{1}, \ldots, x_{n} \in \mathbb{R}^{p}$$ and associated class labels $$y_{1}, \ldots, y_{n} \in{-1,1}$$ . Briefly, the maximal margin hyperplane is the solution to the optimization problem:
  * $$
    \begin{aligned}
    &\underset{\beta_{0}, \beta_{1}, \ldots, \beta_{p}, M}{\operatorname{maximize}} M \\
    &\text { subject to } \sum_{j=1}^{p} \beta_{j}^{2}=1, \\
    &y_{i}\left(\beta_{0}+\beta_{1} x_{i 1}+\beta_{2} x_{i 2}+\ldots+\beta_{p} x_{i p}\right) \geq M \forall i=1, \ldots, n 
    \end{aligned}
    $$
  * The constraint $$y_i \cdots$$ guarantees that each observation will be on the correct side of the hyperplane, provided that $$M$$ is positive. The first constraint is not a real constraint on the hyperplane itself. The first constraint though adds meaning to the second constraint, as this constraint gives the perpendicular distance from the $$i$$th observation to the hyperplane given by $$y_{i}\left(\beta_{0}+\beta_{1} x_{i 1}+\beta_{2} x_{i 2}+\ldots+\beta_{p} x_{i p}\right)$$.  
  * Hence,$$M$$ represents the margin of our hyperplane and the optimization problem chooses $$\beta_0, \beta_1,\cdots,\beta_p$$ to maximize $$M$$. \(James et. al. 343\)
* F: _What does a **Maximal Margin Classifier** maximize for?_
  * It tries to find a hyperplane where the distance between two classes is maximal.
* F: _Why are **Support Vector Classifiers** even necessary if **Maximal Margin Classifiers** already exist?_
  * In order to use a maximal margin classifier, a separating hyperplane has to exist. If there is no separating hyperplane to the optimization problem from above has no solution for $$M > 0$$. The extension of the separating hyperplane is the soft margin and the generalization of the **maximal margin classifier** the **support vector classifier**. \(james et. al. p. 343\)
* F: Give an example for Feature Expansion:
  * Suppose we use $$\left(X_{1}, X_{2}, X_{1}^{2}, X_{2}^{2}, X_{1} X_{2}\right)$$ instead of just $$\left(X_{1}, X_{2}\right)$$. Then the decision boundary would be of the form:  $$\beta_{0}+\beta_{1} X_{1}+\beta_{2} X_{2}+\beta_{3} X_{1}^{2}+\beta_{4} X_{2}^{2}+\beta_{5} X_{1} X_{2}=0$$ 
* F: _Explain what **Feature Expansion** is._
  * Enlargen the space of features by including transformations; e. g. $$X_{1}^{2}, X_{1}^{3}, X_{1} X_{2}, X_{1} X_{2}^{2}, \ldots$$. Hence go from a $$p$$-dimensional space to a $$M > P$$ dimensional space.
  * This leads to a **non-linear decision boundary** in the original space.
  * We consider enlarging the feature space using functions of the predictors such as quadratic and cubic terms, to achieve non-linearity. 
* F: _Explain the Support Vector Classifier._
  * A support vector classifier classifies a test observation depending on which side of a hyperplane it lies. The hyperplane is chosen to separate most of the training observations into two classes, but may misclassify a few observations. \(softens criteria what means "separates"\)
  * It is the solution to the optimization problem:
  * $$\begin{aligned} &\underset{\beta_{0}, \beta_{1}, \ldots, \beta_{p}, \epsilon_{1}, \ldots, \epsilon_{n}, M}{\operatorname{maximize}} M \\ &\text { subject to } \sum_{j=1}^{p} \beta_{j}^{2}=1, \\ &y_{i}\left(\beta_{0}+\beta_{1} x_{i 1}+\beta_{2} x_{i 2}+\ldots+\beta_{p} x_{i p}\right) \geq M\left(1-\epsilon_{i}\right), \\ &\epsilon_{i} \geq 0, \sum_{i=1}^{n} \epsilon_{i} \leq C \end{aligned}$$ 
  * where $$C$$ is a non-negative tuning parameter, $$M$$is the width of the margin, which should be at max. $$\epsilon_{1}, \ldots, \epsilon_{n}$$ are slack variables that allow individual observations to be on the wrong side of the margin or hyperplane. If $$\epsilon_{i}$$is $$0$$, then the $$i$$th observation is on the correct side of the margin. If $$\epsilon_{i}>0$$ the $$i$$-th observation violates the margin. If $$\epsilon_{i}>1$$ is on the wrong side of the hyperplane. $$C$$ bounds the sum of the $$\epsilon_i$$'s, and so determines the number and severity of the margin violations it will tolerate. If $$C=0$$then there is no budget for violations of the margins. One gets a **maximal margin classifier**.
  * When $$C$$ is small, we seek narrow margins that are rarely violated; this amounts to a classifier that is highly fit to the data, which may have low bis but high variance. For larger $$C$$s more violations are possible. Data is fitted less hard and the classifier is potentially more biased but may have a lower variance. 
  * If the above equations are solved, a test observation $$x^{*}$$ is classified by determining on which side of the hyperplane it lies. This is, we classify the test observation based on the sign of $$f\left(x^{*}\right)=\beta_{0}+\beta_{1} x_{1}^{*}+\ldots+\beta_{p} x_{p}^{*}$$ . \(James et al. p. 347\)
* F: _Give the definition for a linear kernel._
  * $$K\left(x_{i}, x_{i^{\prime}}\right)=\sum_{j=1}^{p} x_{i j} x_{i^{\prime} j}$$ 
  * \(James et al. p. 353\)
* F: Give the definition for a polynomial kernel.
  * $$K\left(x_{i}, x_{i^{\prime}}\right)=\left(1+\sum_{j=1}^{p} x_{i j} x_{i^{\prime} j}\right)^{d}$$ 
  * where $$d$$ is the degree of the polynomial. Higher degrees lead to a more flexible decision boundary. The support vector classifier is fitted in a higher-dimensional space involving polynomials of degree $$d$$ rather than the original feature space. \(James et al.  p 353\)
* F: Give the definition for the rbf kernel.
  * $$K\left(x_{i}, x_{i^{\prime}}\right)=\exp \left(-\gamma \sum_{j=1}^{p}\left(x_{i j}-x_{i^{\prime} j}\right)^{2}\right)$$ 
  * $$\gamma$$ is a positive constant, known as the bandwidth parameter.
  * The radial kernel has a local behavior, in a sense that only nearby training observations have an effect on the class label of a test observation.
  * TODO: Kernel prüfen.
* F: Why do we use kernels instead of simply enlarging the original feature space?
  * One advantage is computational, and it amounts to the fact that using kernels, one only compute $$K\left(x_{i}, x_{i^{\prime}}\right)$$ for all $$\left(\begin{array}{c}n \\ 2\end{array}\right)$$ distinct pairs $$i, i^{\prime}$$. This can be done without explicitely working in the enlargend feature space.
* F: _Explain how Least-Squares Support Vector Regression works._
  * $$
    \begin{aligned}
    \min J\left(w, b, u_{i}\right) =\frac{1}{2}\|w\|^{2}+\frac{C}{2} \sum_{i=1}^{N} u_{i}^{2} \\
    \text { s.t. } \quad r_{i}=w^{T} \phi\left(X_{i}\right)+b+u_{i}, \quad i=1, \ldots, N,
    \end{aligned}
    $$

    where $$w$$ is the weight vector of the independent variables while $$b$$ is the intercept. The regularization parameter $$C$$ scales the error terms $$u_{i}^{2}$$ and $$\phi(X)$$ denotes the kernel function for the feature mapping.
* F: _Required scaling for SVMs?_ ⭐
  * Features should be scaled to the interval $$[0,1]$$.
  * **Justification:**
    * The main advantage is to avoid attributes in greater numeric ranges dominate those in smaller numeric ranges. 
    * Another advantage is to avoid numerical difficulties during the calculation. Because kernel values usually depend on the inner products of feature vectors, e. g. the linear kernel and the polynomial kernel, large attribute values might cause numerical problems. \(Hsu, A Practical Guide to Support Vector Classification, p. 4\)
* F: _Name advantages and disadvantages of SVMs over logistic regression._ ⭐
  * SVMs can do better than logistic regression, in cases where data is \(nearly\) separable.
  * Logistic regression allows estimating probabilities. This is however not possible with SVMs.
  * Logistic regression is faster.
  * Logistic regression is easier to interpret.
  * If classes are not separable, both perform very similar.
  * We try to find a plane that separates the classes in the feature space. If that's not possible, we get creative in two ways:
    * We soften what we mean by separates through the introduction of support vectors.
    * We enrich and enlarge the feature space so that separation is possible. This means the feature space gets transformed.
* F: _How do a Maximal Margin Classifier, SVMs, and Logistic Regression relate?_
  * TODO: James et. al p. 356
  * A SVM with $$C=0$$is a **Maximal Margin Classifier**, as there is no budget for margin violations.
* F: _What is the purpose of the support vectors_ $$\epsilon$$_?_ 
* F: _Compare SVMs to logistic regression_
  * Logistic regression focuses on maximizing the probability of the data. The farther the data lies from the separating hyperplane \(on the correct side\), the better logistic regression is.
  * An SVM tries to find the separating hyperplane that maximizes the distance of the closest points to the margin \(the support vectors\). If a point is not a support vector, it doesn't really matter  [\(see here.\)](http://www.cs.toronto.edu/%7Ekswersky/wp-content/uploads/svm_vs_lr.pdf)
* A:
  * When classes are not linearly separable, SVM does better than logistic regression. \([See here](https://stats.stackexchange.com/a/95348)\)
  * Otherwise, the performance of logistic regression \(with ridge penalty\) and SVM are very similar. 
  * To estimate probabilities, the choice should be logistic regression.
  * If interpretability and speed are a major concern, logistic regression should be used.
* F: _Explain how Least-Squares Support Vector Regression improves ordinary SVMs for bond recovery rate prediction._
  * Least-Squares Support Vector Regression can be extended, so that the accuracy for bond recovery rates is improved. 
  * Different intercepts $$b_s$$of $$S$$seniority classes can be set. A certain homogeneity within seniority classes is assumed, which is represented by the different intercepts.
  * $$\begin{array}{r} \min J\left(w, b_{s}, u_{s j}\right)=\frac{1}{2}\|w\|^{2}+\frac{1}{2} \sum_{s=1}^{S} b_{s}^{2}+\frac{C}{2} \sum_{s=1}^{S} \sum_{j=1}^{n_{s}} u_{s j}^{2} \\ \text { s.t. } \quad r_{i}=w^{T} \phi\left(X_{s j}\right)+b_{s}+u_{s j}, \quad j=1, \ldots, n_{s}, s=1, \ldots, S \end{array}$$ 
* F: _Explain how semiparametric Least-squares Support Vector Regression improves ordinary SVMs for bond recovery rate prediction._
  * Semiparametric Least-Squares Support Vector Regression is an extension to the SVM. 
  * A model is constructed that assumes the impact from the different seniority classes is linear. The dummy variables for the seniorty classes $$z_{sj}$$and $$\beta$$ is a vector of fixed effects for the seniority of the respective group.$$\begin{aligned} &\min J\left(w, b, u_{i}\right)=\frac{1}{2}\|w\|^{2}+\frac{1}{2} \beta^{T} \beta+\frac{1}{2} b^{2}+\frac{c}{2} \sum_{s=1}^{s} \sum_{j=1}^{n_{k}} u_{s j}^{2} \\ &\text { s.t. } r_{i}=\mathbf{w}^{T} \phi\left(X_{i}\right)+\beta^{T} z_{s j}+b+u_{s j}, \quad j=1, \ldots, n_{s}, s=1, \ldots, S \end{aligned}$$ 

## Neural Net

* F: _Explain what a Neural Network is._
* F: _How can overfitting be avoided with Neural Networks?_
  * Use early stopping with cross-validation
  * Use network pruning -&gt; A kind of regularization, where the complexity of the network is reduced in order to reduce the generalization error. 
  * Standard ways to limit the capacity of a neural net
    * limit number of hidden parameters 
    * limit the size of weights
* F: _What is the impact of a high number of layers and hidden units?_
  * The more layers and more hidden units in a model, the more capacity it has.
* F: _Compare Logistic Regression to Neural Networks. What are their advantages and what are their disadvantages?_
* _F: Which activation function is good for which use case? -&gt; Classification / Sigmoid etc._
* F: _Explain the purpose of activation functions._
  * An activation function decides in a neural net whether the neuron should be activated or not.

    The activation function defines the output of that node given an input or set of inputs.

  * Activation functions introduce **non-linearity** to Neural Nets.
* F: _Define different **activation functions** and sketch them._
  * **Sigmoid**: $$\sigma(z)=\frac{1}{1+\exp (-z)}$$\*\*\*\*
  * **Tanh**: $$\tanh (z)=\frac{\exp (z)-\exp (-z)}{\exp (z)+\exp (-z)}$$\*\*\*\*
  * **ReLU \(Rectified Linear Unit\)**: $$\operatorname{ReLU}(z)=\max (0, z)$$
  * ![](../.gitbook/assets/sigmoid_tanh_relu.jpg) 
* F: _Sketch a 2-layer neural network with 3 input units, 4 hidden units and 2 output units. Make sure to label its components._
  * \_\_![](../.gitbook/assets/neural_net.jpg) \_\_
  * Note: the output layer counts as a layer. The input layer does not count.
* F: _Explain how **back-propagation** works in neural networks._
  * **Back propagation** is an algorithm used in a neural network to compute the partial derivative of $$\partial C / \partial w$$ of a cost function $$C$$ with respect to any weight $$w$$.\(see [here.](http://neuralnetworksanddeeplearning.com/chap2.html)\) The algorithm consists of several steps:
    1. Initialize weights with random values and set other network parameters
    2. Read in the inputs and desired outputs.
    3. Compute the actual output \(by working forward through the layers\)
    4. Compute the error \(difference between the actual and desired output\)
    5. Change the weights by working backward through the hidden layers.
    6. Repeat \(until convergence or other stop criteria\) \(see BDA lecture p. 29\)
  * TODO: Herleitung / Aufnahme Formel \(Standord Video\)
* F: _How can Neural Nets be used for classification._
  * _One can use the **Sigmoid activation function** for classification._
* F: _How does **logistic regression** relate to **neural networks**?_ 🧠
  * **Logistic regression** can be thought of as a one-layer neural network with no hidden layers.
  * One uses the **Sigmoid activation function**.
  * $$
    z_{k}=w_{k 0}+\sum_{j=1}^{J} x_{j} w_{k j}
    $$
  * $$
    o_{k}(\mathbf{x})=\frac{1}{1+\exp \left(-z_{k}\right)}
    $$
* ![](../.gitbook/assets/logistic_regression_nn.png) 
* F: _What is the impact of a higher number of layers and hidden units in a neural net?_
  * the more layers and more hidden units in a model, the more capacity it has.
  * There might not be enough data. A high capacity model easily overfits training data and results in a bad performance during testing.

## Methods in NLP

* F: _How does the concept of Word2Vec work?_
  * Each word in a vocabulary is mapped to a point in $$m$$-D space, where $$m$$ is the dimensionality of the feature space.
  * If two words are close they will be related or synonymous, otherwise more distant.
  * Vector $$C(i)$$is associated with the $$i^{th}$$ word $$w(t)$$.
  * ![](../.gitbook/assets/grafik%20%2852%29.png) 
  * **Example:**
  * ![](../.gitbook/assets/grafik%20%2851%29.png) 
  * E. g. attorney and lawyer have a closer proximity than lawyer and penguin.
* F: _How can the notion of similarity be embedded in a vector-to-word conversion?_
  * _Words that are related should lie closer together in feature space._ 
  * _Also mathematical operations like subtraction of king - queen should make sense._
* F: _Sketch and explain the process of applying **Continuous Bag of Words \(CBOW\)** to text prediction._
  * The CBOW is an approach to predict the next likely word for a given context. The CBOW averages the vectors of the words in the context. This resulting vector e.g. $$[c_1,\cdots, c_m]$$ is then send through a multi-layer perceptron \(MLP\). On top of the MLP is a Softmax function \(due multi-class classification nature\), which tells us the probability that each of the $$v$$words in the Vocabulary is the missing word. The order of words in the context are **not relevant** for the CBOW model. \(see [here.](https://www.coursera.org/lecture/machine-learning-duke/methods-for-learning-model-parameters-VvzJY)\)
* F: _Why is **Softmax** used in a **CBOW model**?_
  * As the outcome of a CBOW model is not binary, we use a softmax function, which can be used for multi-class-classification.
* F: _How does the **Skip-Gram Model** work_?
  * **Skip-Gram Model** is an approach to predict the next likely word. It takes the $$n$$th word as an input, sends the vector consisting of the components $$[c_1,\cdots,c_m]$$ into a multi-layer perceptron with a Softmax function on top of it to predict the propability of each of the $$v$$words in the vocabulary $$V$$ \(see [here.](https://www.coursera.org/lecture/machine-learning-duke/methods-for-learning-model-parameters-VvzJY)\)
* F: _Compare the **Skip-Gram Model** to **CBOW**. In which way are they different?_
  * _CBOW uses the average of the words in the context as input. Order of words doesn't matter. Hence, a bag of words._
  * _Skip-Gram uses a single word as an input. \(_[_see here._](https://www.coursera.org/lecture/machine-learning-duke/methods-for-learning-model-parameters-VvzJY)_\)_
* F: _Explain **Sentiment Analysis** using an averaging strategy works._
  * Sentiment Analysis **averages the word vectors** for all $$n$$ words in a document. This single resulting vector consisting of $$\left[c_1, c_2, c_3, \cdots\right]$$ is then send to a logistic regression classifier characterized by the parameter $$W$$. A sigmoid function is used to obtain the sentiment in terms of a probability. \(see [here.](https://www.coursera.org/lecture/machine-learning-duke/simple-and-effective-alternative-methods-for-neural-nlp-2vlJK)\)
* F: _Explain **Simple Word-Embedding Based Models** \(SWEMs\) works for Sentiment Analysis._
  * SWEMs utilizes **component-wise maximization**. 
  * For every component in our word vector across all the words in our document one takes the maximum of that value across all words in a document e. g. $$\left[max(c_1(W_1), c_1(W_2),\cdots),max( \cdots)\right]$$ The word that has the largest value for that component will then be used. We plug the resulting vector into a logistic classifier and parameters $$W$$ and make a prediction and obtain a probability for the sentiment. \(see [here.](https://www.coursera.org/lecture/machine-learning-duke/simple-and-effective-alternative-methods-for-neural-nlp-2vlJK)\)
* _F: Name different fields in **Natural Language Processing**._
  * **Syntax**_:_ Grammer induction, lemmatization, morphological segmentation, part-of-speech tagging, parsing, sentence breaking, stemming, word segmentation, terminology extraction
  * **Semantics**: lexical semantics, distributional semantics, machine translation, named entity recognition, OCR, question answering, relationship extraction, semantic analysis and topic segmentation.
  * **Discourse:** Automatic summarization, coreference resolution, discourse analysis
  * **Speech**: e. g. speech recognition, Text to speech,  speech segmentation.
* F: _Explain what is referred to as 'Named Entity Recognition'_
  * Named-entity recognition \(NER\) semantically analyzes unstructured textual data and pursuits to locate and classify named entities into pre-defined categories such as the persons and organizations names, locations, and time expression.
* F: _Name different approaches for 'Named Entity Recognition'. How do they relate._
  * **Rule-based**
    * contextual patterns
  * **Statistical**
    * Generative e. g. Hidden Markov Models
    * Deep Learning Models e. g. RNN, LSTM, BRNN
    * Conditional e. g. Conditional Random Fields, Maximum Entropy, Markow Models
* F: _Explain what a Sentiment Analysis is._
  * Sentiment Analysis focuses on the emotional content of a text and classifies in pre-defined categories. This can be a binary classification, such as positive or negative, but also other more detailed sentiments, as for example excited, happy, or sad.
* F: _Name different Deep Learning Models used in NLP._
  * Recurrent Neural Networks
  * Long Short Term Memory Networks
  * Bidirectional Long Short Term Memory Networks

## RNNs / Bidirectional RNNs / LSTMs / GRUs / CNNs

### RNNs

* F: _Explain RNNs.⭐_
  * A recurrent neural networks are **networks with loops** in them, allowing information **to persist**.
  * In the diagram below, a chunk of a neural network $$A$$, takes some input $$x_t$$ and outputs a value $$h_t$$ saving a new hidden state at $$t$$. A loop allows information to be passed from one step of the network to the next. A hidden state is always dependent on the input $$x_t$$and the old state $$h_{t-1}$$.
  * If one unrolls this loop, a recurrent neural network can be thought of as multiple copies of the same network, where information is passed to the successor. Unrolling the recursive loop yields the **same type of network** repeated **over and over** \(thus recurrent\):
  * ![](../.gitbook/assets/rnn-unrolled.png) 
  * Image and  \(unrolled recurrent network\) adapted [from here](https://colah.github.io/posts/2015-08-Understanding-LSTMs/).
  * Unique about RNN is that a unit can feed itself, to units in the same or lower level.  
  * RNN can handle input of variable length and are good for predicting words or time series.
  * **RNNs** suffer from 2 types of problems:
    * **Vanishing gradients** \(Problem of gradients becoming close to 0 during learning a deep neural net\), solved by LSTMs
    * **\(Exploding gradients\)**
  * **Additional Information** \(proably not that relevant\)**:**
  * The state consists of a single hidden vector $$h$$:
    * $$\boldsymbol{h}_{t}=f_{\boldsymbol{W}}\left(\boldsymbol{h}_{t-1}, \boldsymbol{x}_{t}\right)$$, where $$h_t$$ is the new hidden state at $$t$$. $$f_{\boldsymbol{W}}$$ a function e. g. $$\tanh$$ and $$x_t$$ the input vector at $$t$$. $$\boldsymbol{W}$$is  a weight matrix. $$h_{t-1}$$is the old state.
    * Or:

      $$\begin{aligned} &\boldsymbol{h}_{t}=\tanh \left(\boldsymbol{W}_{h h} \boldsymbol{h}_{t-1}+\boldsymbol{W}_{x h} \boldsymbol{x}_{t}\right) \\ &\boldsymbol{y}_{t}=\boldsymbol{W}_{h y} \boldsymbol{h}_{t} \end{aligned}$$

    * One can clearly see that the hidden state for $$t$$ is dependent on the Weightmatrix for the last internal state and the input of the neural network. $$\tanh$$ is used to compute the next internal state.
  * Unrolling the time steps of a network at depth $$T$$ gives the following computational graph.
    * ![](../.gitbook/assets/computational_graph_rnn.jpg) 
    * \(ML lecture p. 58\)
* F: _Compare the **Feed-Forward network** to a **Recurrent Neural Network**._
  * Feed-forward nets \(learned through back propagation\) need to be strictly feed-forward and can have no recurrent connections.
  * Nodes in a Feed-forward network are connected only to the nodes in the next layer. Wheres in a recurrent network, nodes in one layer may be connected to the ones in previous layers or within the same layer.
  * Feed-Forward networks can only handle fixed-size vectors as input and output \(e. g. probabilities of different classes\). Whereas, recurrent neural networks can handle sequences/vectors of any size.
  * Recurrent neural networks are unique in a way that a unit within the RNN can **feed itself**. That means it can feed back activation that will affect the output from the network during subsequent iterations. 
* F: _Give an intuition for **Recurrent Neural Networks**._
  * _Human thoughts have persistence. That means humans can rely on their thinking to understand a new context._
  * _RNNs can connect previous information to a present task e. g. in predicting time series data or next word_
* _F: Give two use cases/applications of **Recurrent Neural Networks**._
  * Predicting words
  * Predicting time-series data
* F: _Name different RNN architectures. Also, give an example if possible._ 
  * ![](../.gitbook/assets/rnn_architectures.jpg) 
  * **one-to-one:** Vanilla Neural Network
  * **one-to-many:** e. g. Image Captioning \(single Image to the sequence of words\)
  * **many-to-one:** e. g. Sentiment Classification \(sequence of words to single sentiment\)
  * **many-to-many:** e. g. machine translation, sequence of words to sequence of words
  * **many-to-many:** e. g. video classification, on frame-level \(ML lecture slide 58\)
* F: _Give an example for Recurrent Neural Networks. Explain how information is passed from on layer to another._
  * Vocabulary: \[h,e,l,o\], training sequence: "hello"
  * ![](../.gitbook/assets/grafik%20%283%29.png) 
  * \(lecture ML p. 64\)
* F: _What types of RNN were discussed in class?_
  * Bidirectional RNNs
  * GRUs
  * LSTMs
* F: _Explain the difference between **RNNs** and **GRUs**._
  * GRUs are a variant of the RNN. GRUs include controls to regulate what information to forget and what to remember. RNNs on the other hand are store the entire history.
* F: _Explain the difference between **LSTMs** and **GRUs**._
  * _GRUs are simpler in the following way:_
    * GRUs combine the forget and input gate into a single update gate
    * Cell state and hidden state are merged
* F: _Explain the difference between **RNNs** and **LSTMs**._
  * RNNs can only overwrite their memory in a fairly uncontrolled fashion.
  * Whereas LSTMs have a much more sophisticated mechanism of what to remember and what to forget through the usage of four different gates.
* F: _What problem of **RNN's** do **LSTMs** solve?_
  * The vanishing gradient problem.
* F: _Explain what is called the **vanishing gradient problem**._
  * The vanishing gradient problem refers to the increasing difficulty of back-propagating to the first layers with an increasing depth of the network. Especially for sequence data or when networks are deep.
  * Gradients become close to one and learning is no longer possible \(lecture BDA, p. 43\)
* F: _Explain how simple so-called **vanilla RNNs** are different from **standard neural networks**._
  * _Its behavior and structure is identical._
* F: Explain what the **advantage** is of **RNNs** over standard networks.
  * Input and output can have variable lengths.
  * RNNs allow memorizing context.

### Bidirectional RNNs

* F: _Explain **Bidirectional Long Short Term Memory Network.**_
  * **Bidirectional Recurrent Network** are acyclic graphs, that allow **forward** as well as **backward flow** within the network. Hence, they use information from the **past** and the **future** context within a network.
  * This happens through duplicating the RNN processing chain, so that inputs are processed both in forward and reverse time order. \([see here.](https://devopedia.org/bidirectional-rnn)\) However, an RNNs network blocks can be composed both of RNNs, GRUs, and LSTMs. \([see here.](https://blog.paperspace.com/bidirectional-rnn-keras/)\)
  * It's an evolution to the standard RNN.
  * Standard RNN suffers from the problem, that predictions are difficult at the beginning of the learning, when only view words are known.
  * ![](../.gitbook/assets/grafik%20%2850%29.png) 
  * Adapted from [here.](https://colah.github.io/posts/2015-09-NN-Types-FP/)
* F: _What is the advantage of **Bidirectional Long Short Memory Networks** over standard **RNNs**?_
  * Standard RNNs process observations in a strict temporal order. Bidirectional RNN solves the problem of RNN that predictions are difficult when starting with learning, as they also include **future observations**.
* F: Give applications of **Bidirectional RNNs**.
  * Handwriting recognition
  * Natural Language Processing
  * Speech recognition

### CNNs

* F: _Explain CNNs?_
  * Convolutional neural networks are a kind of network that use many **identical copies** of the same neuron. This allows the network to have lots of neurons and express computationally large models with keeping the actual number of parameters \(describing how neurons behave\) and that need to be learned small. \([see here.](https://colah.github.io/posts/2014-07-Conv-Nets-Modular/)\)
  * A CNN consists of three layers:
    * A convolutional layer
    * A pooling layer
    * A fully connected layer
  * CNN's are commonly used for processing data in a grid-like topology e. g. image data. 

### LSTMs

* F: _Explain LSTMs._ ⭐
  * LSTMs are a type of RNNs, that features a sophisticated **forgetting** and **saving mechanism**. To implement this, a LSTM is made up of four interacting **layers** and three **gates**. 
  * Gates regulate what information is saved and removed from the cell state an LSTM cell. Gates implement a way to let information through. They are composed of a sigmoid neural net layer and pointwise multiplication operation \(the hadamard product\). If the output of a sigmoid layer is close to $$0$$, hardly any information is passed through and vice versa if it's close to $$1$$. \(see [here.](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)\)
  * The gates are commonly referred to as **input gate** \(controlling how much to write to a cell\), **output gate** \(controlling how much to reveal to a cell\), and **forget gate** \(controlling whether to erase a cell\).
  * LSTMs are suitable for NLP and time-series predictions, where both very recent and both more distant information are relevant for predictions.
  * LSTMs have outplayed RNNs, due to their robustness against **vanishing gradients** and their ability to adjust forgetting and remembering past information.
  * TODO: Fomeln + Visualisierung
* F: _LSTMs are suitable for which type of analysis?_ ⭐
  * sequence modeling, with variable input and output length
  * time series analysis
* F: _How can we use LSTMs for time series data?_ ⭐
  * First of all, all time-series forecasting problems must be re-framed as **supervised learning problem**.
  * One approach is to reframe time series data by considering past observations as input variables and future observations as the output variable.
  * Example:
    * Time series: 1, 2, 3, 4, 5, 6, 7
    * For $$I = 1$$, we can reframe our timeseries to the following supervised learning problem: \(x,y\): $$(1,2), (2,3), (3,4), (4,5) \cdots$$
* F: _Explain how LSTMs update their memory._
  * Recall there are four gates:
    * **forget gate:** whether to erase a cell
    * **input gate:** how much to write to a cell
    * **gate gate:** what to write to a cell \(this is no gate in a closer sense?\)
    * **output gate:** how much to reveal a cell \(lecture ML p. 79\)
  * In the first step, we decide what information to throw away from the cell state. This decision is made by a sigmoid layer called **forget gate** layer. It takes $$h_{t-1}$$ and $$x_t$$as an input and outputs a number between $$0$$\(~completely forget\) and $$1$$\(remember entirely\) for the cell state. The boundaries come from the nature of the sigmoid functions. The cell state contains information on the context e. g. gender in a text.
  * ![](../.gitbook/assets/lstm_step_1.png) 
  * In the next step, we decide what to store in the cell state. This has two parts. First, a sigmoid layer called the **input gate** layer decides which values to update. Next, a $$\tanh$$ layer creates a vector of new candidate values $$\tilde{C}_t$$that could be added to the state.
  * ![](../.gitbook/assets/lstm_step_2.png) 
  * In the next step, we update the old state of cell $${C}_{t-1}$$ to the new cell state $$C_t$$. To do so, we multiply the old state by $$f_t$$, forgetting the things we wanted to forget \(step 1\) and then add $$i_t*\tilde{C}_t$$ \(from the **gate gate**\). This gives us the new candidate value, scaled by how much we want to update the state value.
  * ![](../.gitbook/assets/lstm_step_3.png) 
  * Finally, we decide on what to output. The output is based on a cell state, but will be filtered.  A sigmoid layer decides on what parts of the cell state we are going to output. The cell state is then put through a $$\tanh$$ layer and multiplied by the output of the sigmoid gate \(the **output gate**\), so that only the parts we wanted to output are output.
  * ![](../.gitbook/assets/lstm_step_4.png) 
  * Images and text adapted from  [here.](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)

### GRUs

* F: _Explain **GRUs**._
  * GRUs are a variant of RNNs using gates to control what information to remember and what to forget. A GRU is a **simpler variant** of the LSTM. It contains only an **update gate** $$z_t$$ **\*\*\(**fuse of the forget and input gate **or** fuse of long-term and working memory**\) \*\***and **reset gate** $$r_t$$ with different weights.
  * When the **update gate** is closed/inactive, it's possible to propagate information far through the network without losing much of it. The unit has long-term dependencies.
  * Units with short-term dependencies have often active **reset gates**.
  * The **vanishing gradient problem** existing with RNNs is solved, as new input doesn't completely erase past relevant information, which can be kept. 
  * \_\_![](../.gitbook/assets/gru.png) \_\_
* F: _What is the advantage / disadvantage of **GRUs** over **LSTMs**?_
  * GRUs are computationally less expensive. \(+\)
  * LSTMs often deliver better results \(-\)
* F: _Explain how **updating** a memory cell in a **GRU** works._
  * Recall there are two gates:
    * The update gate $$z_t$$
    * The reset gate $$r_t$$
  * The first step is to calculate the **update gate** $$z_t$$, which decides what information to throw away and what new information to add.  We plugin the input $$x_t$$ and the previous hidden state $$h_{t-1}$$, which holds the information for the previous $$t-1$$ timesteps. Both are multiplied with their respective Weight matrices, added and squashed between $$0$$ and $$1$$using the sigmoid function. An update gate close to $$1$$would implies, that information is copied through many times.
  * The next step is to calculate the **reset gate** $$r_t$$.The **reset gate** decides how much past information to forget. The idea is similar to the **update gate**.
  * In the next step is to calculate the current memory content $$\tilde{h}_t$$. First, we multiply the input $$x_t$$ by its weight matrix and then use the Hadamard product of the previous hidden state $$h_{t-1}$$ and the forget gate $$r_t$$. A **reset gate** close to $$0$$ would mean the previous hidden state is ignored. The sum of both is plugged into a $$\tanh$$function.
  * In the last step we calcualte the new $$h_t$$, a vector holding information for the current unit. It is \(weighted\) sum of the hadamard product between the update gate $$z_t$$and $$h_{t-1}$$and the portion of the current memory content, which is the hadamard product of the currrent memory content $$\tilde{h}_t$$ and $$(1-z_t)$$. The result is saved in $$h_t$$. \([see here.](https://towardsdatascience.com/illustrated-guide-to-lstms-and-gru-s-a-step-by-step-explanation-44e9eb85bf21)\) \([see here.](https://towardsdatascience.com/understanding-gru-networks-2ef37df6c9be)\)
  * ![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWnh07mnETIlqhjJW0c%2F-Mf1H_s-otz6p81Dzf15%2F-Mf1TU4zkZB59Jg4riq4%2Fgru.png?alt=media&token=b5ed976f-412c-41a1-a076-36b63ea3cab5)
  * Drawing [see here.](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)
  * TODO: Visualize as for LSTMs [http://colah.github.io/posts/2015-08-Understanding-LSTMs/](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)

## Misc

* F: _Techniques that can be used for default prediction._ ⭐
  * logistic regression
* F: _How do you evaluate this work? what is your main concern about his work?_ ⭐
  * Positive about his work is that he tried several models and that he used grid search for parameter optimization.
  * His work shows some sustainable problems.
  * The dataset is highly imbalanced, as non-default loans appear four times more often than defaulted loans. However, he doesn't compensate for this by either upsampling the training data for model training \(I\) and by choosing the right might metric \(II\).
  * There are different costs for rejected loans and handed out, but defaulted loans. Defaulted loans are much more expensive than rejected loans. The used measure accuracy doesn't acknowledge that. 
  * As SVMs can be derived from logistic regression. That means an SVM with a linear kernel should at least perform as well as the logistic regression. \(further research required\)
  * TODO: Formel for Accuracy für Datenset berechnen wenn Mehrheitsklasse / 80 % / 
* F: _What is your suggestion?_⭐
  * I'd recommend choosing $$F_1$$ as a measure or other measures that can handle imbalanced data and apply different costs. 
  * It might be wise to plot ROC curves to find a sweet spot \(combination with greatest ascend\) between True Positive and False Positive Rate.
  * analyze der False negatives
  * TODO: Up-sampling / down-sampling synthetic sampling Smote. Implement dummy classifier \(majority vote\)  as a baseline.
* F: _Do you have any recommendations for improving the SVM results?_ ⭐
  * I'd recommend the following:
    * Scaling features to a $$[0,1]$$ range.
    * Apply feature expansion and fit Support Vector classifier on a larger feature space
    * train SVMs on up-sampled data to have an equal balance of defaulted and non-defaulted loans.
    * Varying more parameters with grid search such as degree of polynomial or width of support vectors.
    * TODO: improved data pre-processing
* F: _Calculate the information gain of the input attribute age and income using entropy._ ⭐
* F: _Which variable \(income or age\) do you suggest for first splitting? Why?_ \(2+2\)
  * TODO: Add handwritten notes
* F: _List other machine learning techniques that can be used for default prediction._⭐
  * Decision Tree for classification
  * Bagging for classification 
  * Gradient Boosting for Classification such as XGBoost, CatBoost
  * Random Forest for classification
  * Deep Learning
  * Neural Nets

