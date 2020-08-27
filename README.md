# Outline
- [Introduction](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#introduction)
- [Machine learning](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#machine-learning)
    - [1. Models](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#1-models)
        - [1.1 Support vector machine](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#11-support-vector-machine)
        - [1.2 Tree-based models](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#12-tree-based-models)
    - [2. Feature engineering](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#2-feature-engineering)
        - [2.1 Categories](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#21-categories)
        - [2.2 Feature selection](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#22-feature-selection)
        - [2.3 Tools](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#23-tools)
    - [3. Loss function](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#2-loss-function)
    - [4. Evaluation metrics](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#3-evaluation-metrics)
    - [5. Sample projects](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#4-sample-projects)
    - [6. Classical questions](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#5-classical-questions)
    
    
- [Deep learning](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#deep-learning)
    - [Optimization algorithms](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#1-optimization-algorithms)
    - [Exploding/vanishing gradients](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#2-explodingvanishing-gradients)
    - [Batch Normalization](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#3-batch-normalization)
    - [Nerual Networks](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#4-nerual-networks)
    - [Tips of training DL models](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#5-tips-of-training-dl-models)
    - [6. Regularization](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#6-regularization)
        - [6.1 L1 and L2](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#61-l1-and-l2) 
        - [6.2 Dropout](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#62-dropout)
        - [6.3 Other technicals](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#63-other-technicals) 
    - [CNNs](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#7-cnns)
    - [RNNs](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#8-rnns)
    - [Learning Types](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#9-types)
    - [Auto-Encoder](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#10-auto-encoder)

- [Reinforcement Learning](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#reinforcement-learning)
    - [Definitions](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#definitions)
    - [Q-learning](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#q-learning)
        - [DQN](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#dqn)
    - [Policy gradient](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/README.md#policy-gradient)


# Introduction
Since [CS231n](http://cs231n.stanford.edu/), [Andrew Ng's new DL course](https://www.coursera.org/specializations/deep-learning), [Andrew Ng's CS229](https://see.stanford.edu/Course/CS229) and [Google ML course](https://developers.google.cn/machine-learning/crash-course/) are all introducing basic concepts about ML and DL, so I combine them together. Material from [huaxiaozhuan](http://www.huaxiaozhuan.com/) provides good tutorials about commom machine learning algorithms.

# Machine learning
## 1. Models
Model complexity: VC dimension
### 1.1 Support vector machine
#### 1.1.1 Principle
- **Hyperplane**: `w_T * x + b = 0`
- **Margin** (i.e., distance between *positive* support vectors and *negative* support vectors): `2 / ||w||`. 
- **Maximize the margin**: `max 2 / ||w||` s.t. `y_i (w^T * x_i + b) >= 1` -> **Minimize the opposite**: `min 1/2 * ||w||^2` s.t. `y_i (w^T * x_i + b) >= 1`. This formula can be solved directly by quadratic programming (QP), but can also be solved by Lagrance efficiently
- **Lagrance**
- `L(w, b, a) = 1/2 * ||w||^2 + sum(a_i * (1 - y_i * (w_T * x_i + b)))` [1]
- Let the partial derivative of `L` with respect to `w` and `b` euqal to 0, then `w = sum(a_i * y_i * x_i), 0 = sum(a_i * y_i)`. Replace above euqation to [1], then `L = max sum(a_i) - 1 / 2 * sum(sum(a_i * a_j * y_i * y_j * x_i^T.dot(x_j)))`, s.t. `sum(a_i * y_i) = 0 and a_1 >=0` [2], which `a` can be solved by **Sequential Minimal Optimization (SMO)** (select two variables `a_i` and `a_j`, fix other `a`)
- KKT: solution of prime problem == solution of dual problem
#### 1.1.2 Kernel
- Principle: **map low dimension linear non-separable space to high dimension linear separable space use function fai(x)**
- However, `x_i^T.dot(x_j)` -> `fai(x_i).dot(fai(Y_i))` can be hard to compute, then **kernel** perform the linear transformation and return the inner product of this transformation directly. 
- Catetories
    - Linear kernel: `x_i^Tx_j`
    - Polynomial kernel: `(x_i^Tx_j)^d`
    - Gaussian (RBF) kernel: exp(- ||x_i-x_j||^2 / 2sigma^2)
#### 1.1.3 Soft margin SVM
- `min 1/2 * ||w||^2 + C * sum(epison_i)`, s.t. `y_i (w^T * x_i + b) >= 1 - epison_i` and `epison_i >=0`
- `C` is a regularization parameter
- small `C` allows constraints to be easily ignored → large margin
- large `C` makes constraints hard to ignore → narrow margin
- Note, there is only one parameter, `C`
#### 1.1.4 Hinge loss view
- Definition: `max(0, 1-z)`
- SVM: `min 1/2 * ||w||^2 + C * sum(max(0, 1 - y_i(w^T * x_i + b))))`
- Relationship with NN
- SGD with hinge loss
#### 1.1.5 Multi-class SVM
- [one-vs-the-rest](https://scikit-learn.org/stable/modules/generated/sklearn.svm.LinearSVC.html#sklearn.svm.LinearSVC)
- [one-against-one](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html#sklearn.svm.SVC)
#### 1.1.6 Extensions
- [Support Vector Regression](https://www.saedsayad.com/support_vector_machine_reg.htm)
    - Loss function: tube loss, `max(0, |s-y|-epison)`
    
- When two points appears in a range, the loss is zero
- Ranking SVM
- One-class SVM
### 1.2 Tree-based models
#### 1.2.1 Decision tree
- Principle
    - **Recursive partition** of the space with **greedy** strategy (i.e., each partition is optimum), the boundary is **axis-parallel**
    - Hyper parameter: `max-depth`
    - Binary tree, easy interpret (good for medical analysis)
    - Do not need standarizaion or normalization, and missing data cannot affect the model
- Categories
    - ID3
        - Criterion: maximize **information gain**. For one feature `a`, which has 10 different values, `IG = Entropy(D) - sum(v in range(10): |D_v| / |D| * Entropy(D_v))`
        - **Multi-branch** tree
        - Drawback: **perfer features that has many values**
    - C4.5
        - Criterion: maximize **information gain ratio** = information gain / intrinsic value (feature)
        - **Multi-branch** tree
    - CART
        - Criterion: minimize **suqared error** for regression (`min(min(sum(y_i-c_1)^2) + min(sum(y_1-c_2)^2))`, where `c_1` and `c_2` is  mean of two parts splitted by feature value) and **Gini index** for classification (`1 - sum(p_k^2)`)
        - **Binary-branch** tree: is or not is for one feature
        - Relationship between entropy and Gini index, `f(x)=-ln(x)` Tayor expansion with `x=1`, then `f(x)=1-x`, then `entropy = -sum(p_i * ln(p_i)) = sum(p_i * (1-p_i))) = gini index`
	- For [regression](https://www.quora.com/How-do-decision-trees-for-regression-work), **recursive partition** with the principle that splitting the value of a feature that minimizes the sum of squared errors (SSE) of prediction. To avoid overfitting, `|tree size|` is added to SSE
    - Multi-variate decision tree
        - Criterion: each node is a **linear classifier** instead of a univariate feature
- Overfitting
    - Pre-pruning
        - prone to under-fitting
    - Post-pruning
        - For CART, plus the `|tree size|` in SSE
- Features
    - **Continuous feature**
        - To discrete feature via **bi-partition** (e.g., >10 ?)
        - First sort the value, then choose the **median** of two adjacent value as the condition
    - **Categorical feature**
        - Decision subset. E.g. X1: ['A', 'B'], then subset: ['A'], ['B'], ['AB']
- **Missing data**
- **Split termination criterion**
    - All `y` is same: all samples belong to the same category
    - All `X` is same: feature is None, or all samples have same values on all features, no decision stumps
    - No samples available

#### 1.2.2 Random forest
- Principle: **resample the samples** with replacement, and **resample the features** at the same time
- Hyper parameter: `number of trees`, `number of feature for each tree: sqrt(# features)`
- Reduce overfit, and reduce variance

#### 1.2.3 Gradient boosted decision trees
- Principle: **use decision tree to fit the residue**, like Taylor expansion
- Reduce bias
- [tutorial 1](https://medium.com/mlreview/gradient-boosting-from-scratch-1e317ae4587d), [tutorial 2](https://github.com/Freemanzxp/GBDT_Simple_Tutorial)
- [Gradient boosting performs gradient descent](https://explained.ai/gradient-boosting/descent.html)
- [Learning rate](https://rcarneva.github.io/understanding-gradient-boosting-part-1.html), i.e., shrinkage: shrinks the contribution of each tree by learning_rate

#### 1.2.4 Tools
- [LightGBM](https://lightgbm.readthedocs.io/en/latest/), [example](https://medium.com/@pushkarmandot/https-medium-com-pushkarmandot-what-is-lightgbm-how-to-implement-it-how-to-fine-tune-the-parameters-60347819b7fc)



### 1.3 EM
#### Principle
- Expectation Maximization is MLE or MAP with **latent variable**, which is used to estimate the parameter **iteratively**
- Two steps
    - E
        - `product(p(y|theita)) -> sum(lnp(y|theita)) = sum(ln sum(y,z|theita))`, where `sum` in `ln` make derivative equal to `0` cannot be computed
        - `Q(theita, theita_i): sum(p(z|y,theita) * lnp(y,z|theita))`, compute expectation of `lnp(y,z|theita)` with weight `p(z|y,theita)` (you can think that first choose the cluster first in GMM), where `theita_i` is known and `theita` is the parameter that to be estimated
	
    - M
        - `argmax Q` find theita with making partial derivative of `Q` with repect to `theita` equal to `0`
- Applications
    - [K-means and Gaussian mixture model](http://www.cs.cmu.edu/~guestrin/Class/10701-S05/slides/EM-MixGauss4-4-2005.pdf)

### 1.4 MaxEnt
#### 1.4.1 Entropy
- Entropy
    - Information size: `-logp(x)`
- Union entropy
- Condition entropy
- Mutual information
    - Measure the non-linear relationship between two variables
    - Can be used to select feature
- Relative entropy (i.e., KL divergence)
    - Measure the **difference between two distributions**
    - `D(p||q) != D(q||p)`
    - `D(p||q) >= 0`
- Cross entropy
    - Relationship with KL divergence: `CE(p, q) = H(p) + D(p||q)`

### 1.5 Model selection
#### 1.5.1 Under-fitting / Over-fitting
Instead of **learning curve**, we usually look at the **gap** bewteen training accury and testing accury to check whether the model is over-fitting.

#### 1.5.2 [Model ensemble](https://mlwave.com/kaggle-ensembling-guide/), [sklearn](https://scikit-learn.org/stable/modules/ensemble.html)
- Bagging
    - Random feature and random samples
    - Reduce high-variance
- Boosting
    - Reduce high-bias
    - Difference between GBDT and XgBoost: first-order and second-order derivative
- Blending
    - Split data to first-step training data and second-step training data
    - Based on first-step training data, we can train different models `[m_1, m_2, ..., m_n]`
    - Based on second-step training data, first get the predictions `[y_1, y_2, ..., y_n]` using `[m_1, m_2, ..., m_n]`, then a new model (usually simple model such as linear model) fit on `[y_1, y_2, ..., y_n], true-y`
- Stacking
    - Basic idea of Stacking is same as Blending
    - Stacking uses cross-fold-validation (the out-of-fold is used to train the next layer), while Blending uses a holdout validation (part of the train is used in the first layer, part in the second)



## 2. Feature engineering
### 2.1 Categories
- **Numerical**
    - **Scaling**
        - `MinMaxScaler`, `StandardScaler`
    - Log
    - Statistics
        - The gap between the price and the average price
    - **Discreting** (e.g., `age`)
        - `pd.cut`, `pd.qcut`
- **Categorical (enumerated)**
    - **Boolean** (i.e., is it yes or no ?)
        - For example, `red, yellow, green` are categorical feature, a object both have `red` and `green` feature can be represented as `[1, 0, 1]`
	- `pd.get_dummies`
    - Histogram
        - For example, there are `gender` and `hobbies` two features, we can calculate the precent of hobby on `male` and `female` category respectively. And replacing this percent to `hobbies` feature to each sample
- **Time**
    - Continuous
        - During time (i.e., browsing during time)
        - Interval time (i.e., the time between last time buying and now)
    - Discrete
        - The quarter in one year (i.e., 0, 1, 2, 3)
        - The week in one year (i.e., 0, 1, ..., 54)
        - The day in one week (i.e., 0, 1, ..., 6)
        - The hour in one day (i.e., 0, 1, ..., 23)
        - Workday or weekend
- **Missing value**
    - **Additional boolean** feature
    - For example, some sample does not have `age` feature, then additional feature `is_age_defined` is added.

### 2.2 Feature selection
- [**Univariate**](https://scikit-learn.org/stable/modules/feature_selection.html#univariate-feature-selection)
    - Selecting the best features based on univariate statistical tests
    - For example, chi2, Pearson, mutual information
- [**Recursive feature elimination**](https://scikit-learn.org/stable/modules/feature_selection.html#recursive-feature-elimination)
    - Selecting features by recursively considering smaller and smaller sets of features
- [**SelectFromModel**](https://scikit-learn.org/stable/modules/feature_selection.html#feature-selection-using-selectfrommodel)
    - Lasso with L1 regularization
    - Tree-based

### 2.3 Tools
- [Featuretools](https://www.featuretools.com/) for automatic feature engineering.

## 3. Loss function
### 3.1 Categories
- Mean square error (MSE)
    - Linear regression
    - L2 loss
- Logarithmic loss
    - Logistic regression.
    - **L(Y, f(x)) = -logf(x)**. [Fast.ai.wiki](http://wiki.fast.ai/index.php/Log_Loss) gives a detailed explanation of log loss.
- Cross entropy
    - shortcut of KL divergence, relative entropy
- Max-margin loss
    - `J = max(0, 1+s-s_c)`
- Exponential loss
    - Adaboost
- Hinge loss
    - SVM
- Cosine similarity
    - Cosine curve (degree=0, cos_value=1; degree=90, cos_value=0; degree=180, cos_value=-1)
    
### 3.2 Empirical risk minimization (ERM) and Structural risk minimization (SRM)
**ERM = minimize loss**, it may leads to over-fitting phenomenon. For example, maximum likelihood estimation (MLE).  
**SRM = ERM + regulairzation**. For example, maximum a posterior (MAP).  

#### 3.2.1 MLE
- Choose value that maximize the probability of observed data, i.e., `argmax_theita P(D|theita)`

#### 3.2.2 MAP
- Choose value that is most probable given observed data and prior belief, i.e., `argmax_theita P(theita|D) = argmax_theita P(D|theita) * P(theita)`
- MLE is a special case of MAP, where the prior is [uniform](https://wiseodd.github.io/techblog/2017/01/01/mle-vs-map/)

## 4. Evaluation metrics
### 4.1 Accuracy, precision, recall and F1
Consider a scenario that predicting the gender of the user (i.e., male or female). This is a classical **binary classification** prediction problem. Let predicted 1 (i.e., positive) indicates male and predicted 0 (i.e., negative) indicates female.  

**Confusion matrix**:  

|               | Predicted positive |   Predicted negative  |
|   :---:       | :---:             |     :---:                |
|Real positive |      TP             |         FN               |
|Real negative |       FP            |      TN   |  

Multi-class confusion matrix: element at row *i* and column *j* denotes the true class *i* and is being classified in class *j*.  

**Accuracy** = (TP + TN) / (TP+FP+FN+TN), suffer from **class imbalance** problem.  
**Error** = (FP + FN) / (TP+FP+FN+TN) = 1 - accuracy  

**Precision** = TP / (TP + FP) What's the correct proportion of predicted positive ?  
**Recall** = TP / (TP + FN) What's the pick up proportion of all positive obsverations ?  
**F1** = 2 * Precision * Recall / (Precision + Recall).  
Increase **Precision** indicates increase classification threshold; meanwhile, increase **Recall** indicates decrease classification threshold. 

**False Positive** = FP / (FP + TN)  
**True Positive** = TP / (TP + FN), i.e., **Recall**.  

Which model is better?  
Model 1:  

|               | Predicted 1 |   Predicted 0  |
|   :---:       | :---:               |     :---:                |
|Real 1 |      4             |         2              |
|Real 0|       3            |      1   |  

Model 2:  

|               | Predicted 1 |   Predicted 0  |
|   :---:       | :---:               |     :---:                |
|Real 1 |      6            |         0               |
|Real 0 |       4            |      0   |  


Model 1: accuracy = 92%.  
Model 2: accuracy = 95%.  
Model 2 has higher accuracy than model 1, but model 2 is useless. This is called [accuracy paradox](https://en.wikipedia.org/wiki/Accuracy_paradox), which means the model with higher accuracy may not have better generalization power.   
In general, when **TP < FP**, the accuracy will always increase when we change the classifier to always output **'negative'**. Conversely, when **TN < FN**, the same will happen when we change the classifier to always output **'positive'** [1].  

**Recall@k**  

### 4.2 ROC, AUC  
**ROC (Receiver Operating Characteristic curve)**: A curve of true positive rate vs. false positive rate at different **classification thresholds**. The **x-axis** is **False Positive rate**, and the y-axis is **True Positive rate**. [3] .  

Close to the **up left** point (TPR=1.0, FPR=0.0) indicates the model is better. On the diagonal line, TPR = FPR, which means the **random guess**.  


**AUC (Area under the ROC curve)**: aggregate measure of performance across all possible classification thresholds.  
One way of interpreting AUC is as the **probability** that the model ranks a random positive example more highly than a random negative example. [3]

### 4.3 BLEU

References:  
[1] https://tryolabs.com/blog/2013/03/25/why-accuracy-alone-bad-measure-classification-tasks-and-what-we-can-do-about-it/  
[2] https://www.zhihu.com/question/30643044  
[3] https://developers.google.cn/machine-learning/crash-course/classification/true-false-positive-negative  


## 5. Sample projects
- [Vectorized logistic regression](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Logistic%20regression/Logistic_regression_vectorized.py)

![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Logistic%20regression/Logistic%20regression.png)

- [Vectorized neural network](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Neural%20network/Neural_network_vectorized.py)

![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Neural%20network/Neural%20network.png)

## 6. Classical questions
### 6.1 Why is logistic regression a generalized linear model ? 
Suppose that the logistic regression, `p = sigmoid(z)`:
- The input `z`, i.e., `z = WX + b`, is a linear function of x.
- Log-odds, i.e., `log (p/(1-p)) = WX`, is a linear function of parameters `W`.
- **Decision boundary**, i.e., `WX = 0`, is linear. This does not mean LR can only handle linear-separable data. Actually, we can convert low-dimensional data to high-dimensional data with the help of **feature mapping**. And the data are linear-separable in the high-dimensional space.
- Both logistic regression and softmax regression can be modeled by exponential family distribution.

#### What's the difference between linear and non-linear regression ? 
- It is **wrong** that **linear regression model generates straight lines and nonlinear regression model curvature**. Actually, both linear and non-linear models can fit curves.  
- Linear means **linear in parameters `W` but not in `X`**. For example, both functions `f_1 = w_1x_1 + w_2x_2 + b` and `f_2 = w_1x_1 + w_2x_2 + w_3x_2^{2} + b` are linear functions. The most common operation is adding **polynomial terms** (i.e., quadratic term or cubic term) in linear model.
- Example of non-linear function `f_3 = w_1x^{w_1}`
- **`log` transform** can be used to convert nonlinear function `y=e^{b}x_1^{w_1}x_2^{w_2}` to linear function `lny = b + w_1lnx_1 + w_2lnx_2`

#### The influence of classification threshold
![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Logistic%20regression/Precision_Recall_1.png)  
Precision = 0.8, Recall = 0.73.  
![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Logistic%20regression/Precision_Recall_2.png)  
Precision = 0.88, Recall = 0.64.  
![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Logistic%20regression/Precision_Recall_3.png)  
Precision = 0.75, Recall = 0.82.  

References:  
https://www.quora.com/Why-is-logistic-regression-considered-a-linear-model  
https://stats.stackexchange.com/questions/93569/why-is-logistic-regression-a-linear-classifier  
https://stats.stackexchange.com/questions/88603/why-is-logistic-regression-a-linear-model  
http://cs229.stanford.edu/notes/cs229-notes1.pdf  
http://statisticsbyjim.com/regression/difference-between-linear-nonlinear-regression-models/  
http://statisticsbyjim.com/regression/curve-fitting-linear-nonlinear-regression/  
https://developers.google.cn/machine-learning/crash-course/classification/precision-and-recall  
Logistic regression application in Meituan:  
https://tech.meituan.com/intro_to_logistic_regression.html


### 6.2 How to prepare train, dev and test dataset ? 
- Principle: make sure that the distribution of **validation set** and **test set** are **same**.
- Train and dev/test may from slightly different distribution.
- [Learning curve](http://scikit-learn.org/stable/auto_examples/model_selection/plot_learning_curve.html) shows the **training and validation score** along the increases of **training examples**.

### 6.3 Error analysis
- Manually check say 100 mis-classified validaton samples, and count their error types.


# Deep learning
## 1. Optimization algorithms
### 1.1 Exponential weighted averages
- All advanced optimization algorithms are based on **exponentially weighted averages** (`V_t = beta * V_t-1 + (1-beta) * theita_t`), which approximately averages `1/(1-beta)` days. An example, `V_0 = 0, V_1 = 0.9 * V_0 + 0.1 * theita_1, V_2 = 0.9 * V_1 + 0.1 * theita_2`, ..., therefore, `V_2 = 0.1 * theita_2 + (0.1 * 0.9) * theita_1`, the weights of `theita_x` is exponentially decay.  
- At early steps, **bias correction** is used. i.e. `V_t = V_t / (1 - beta^t)`. If `t` is large, then `1 - beta^t` approximates `1`, bias correction does not work now.
### 1.2 Momentum
- `V_dw = beta * V_dw + (1-beta) * dw`
- `w = w - alpha * V_dw`
### 1.3 RMSprop (Root mean square prop)
- `S_dw = beta * S_dw + (1-beta) * dw ** 2`
- `w = w - alpha * dw / [S_dw^(1/2) + epsilon]`, where `** 2` is element-wise multiplication and `epslion=1e-8`.
### 1.4 Adam (Adaptive moment estimation)
- `V_dw = beta_1 * V_dw + (1-beta_1) * dw; S_dw = beta_2 * S_dw + (1-beta_2) * dw ** 2;`
- `V_dw_corr = V_dw / (1-beta_1^t); S_dw_corr = S_dw / (1-beta_2^t)`
- `w = w - alpha * V_dw_corr / [S_dw_corr^(1/2) + epsilon]`
- `beta_1 = 0.9, beta_2 = 0.999, epsilon = 1e-8`
### 1.5 Learning rate decay
- Decay the learning rate after each epoch
- `learning_rate / (1.0 + num_epoch * decay_rate)` 
- Exponential decay: `learning_rate * 0.95^num_epoch`
### 1.6 Saddle points
- First-order derivative is **zero**.
- For one dimension, the saddle point is local maximum, but for another dimension, the saddle point is local minimum.

## 2. Exploding/vanishing gradients  
### 2.1 Vanishing gradients [1, 3]:
- Results: early layers are **converged slower** than later layers. 
- Reason: `sigmoid` and `tanh` activations suffer from vanishing gradients. But `ReLU` activation does not have this problem.
- Solutions:
	- **Activation function**.`ReLU` or `Leaky ReLU`. `ReLU` can have **dying** states (caused by i.e., large learning rate or large negative bias), whose both outputs and gradients are zero. `Leaky ReLU` solves this problem. Variants of `Leaky ReLU` is `randomized leaky ReLU (RReLU)`, `parametric leaky ReLU (PReLU)`. `exponential linear unit (ELU)`.  
	**ELU > Leaky ReLU > ReLU > tanh > sigmoid** [5].
	- **Weights initialization**. i.e., `Xavier` initialization (**Two goal**: the **outputs variance** of each layer is equal to the **inputs variance**; the **gradients variance** before and after flowing through a layer is equal) for `sigmoid` and `tanh`, `He` initialization for `ReLU` and `Leaky ReLU`. 
	- **Batch Normalization**. Address vanishing or exploding gradients problem during training [6].
- Implementation [5]
```
# xavier
tf.contrib.layers.fully_connected(inputs, num_outputs, weights_initializer=initializers.xavier_initializer())

# He
he_init = tf.contrib.layers.variance_scaling_initializer() # default is He initialization that only consider fan-in
tf.contrib.layers.fully_connected(inputs, num_outputs, weights_initializer=he_init)

# elu
tf.contrib.layers.fully_connected(inputs, num_outputs, activation_fn=tf.nn.elu)

# leaky relu
def leaky_relu(z, name=None):
    return tf.maximum(0.01*z, z, name=name)
tf.contrib.layers.fully_connected(inputs, num_outputs, activation_fn=leaky_relu)
```
![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Neural%20network/Xavier_He_initialization.png)

### 2.2 Exploding gradients [2, 3]:
- Results: gradients and cost become `NaN`.
- Reason: large weights and derivative of activation multiplication during back propagation. It is particularly occured in RNNs.
- Solution: **gradients clipping**.
- Implementation:  
```
# pseudo code
if norm(gradients) > max_gradients_norm:
    gradients *= max_gradients_norm/norm(gradients)

# real code
variables = tf.trainable_variables()
gradients = tf.gradients(ys=cost, xs=variables)
clipped_gradients, _ = tf.clip_by_global_norm(gradients, clip_norm=self.clip_norm)
optimizer = tf.train.AdamOptimizer(learning_rate=1e-3)
optimize = optimizer.apply_gradients(grads_and_vars=zip(clipped_gradients, variables), global_step=self.global_step)
```

### 2.3 Why LSTM resistant to exploding and vanishing gradients?
- If the forget gate is on and the input and output gates are off, it just passes the memory cell gradients through unmodified at each time step [4].
- CEC (Constant Error Carrousel) mechanism with gate [7].

References:  
[1] https://ayearofai.com/rohan-4-the-vanishing-gradient-problem-ec68f76ffb9b  
[2] https://www.quora.com/Why-is-it-a-problem-to-have-exploding-gradients-in-a-neural-net-especially-in-an-RNN  
[3] http://www.wildml.com/2015/10/recurrent-neural-networks-tutorial-part-3-backpropagation-through-time-and-vanishing-gradients/  
[4] http://www.cs.toronto.edu/~rgrosse/courses/csc321_2017/readings/L15%20Exploding%20and%20Vanishing%20Gradients.pdf  
[5] Hands on machine learning with Scikit-Learn and TensorFlow p278, P281  
[6] https://www.zhihu.com/question/38102762  
[7] https://www.zhihu.com/question/34878706

## 3. Batch Normalization

![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Neural%20network/Batch_normalization_formula.png)  

- **Covariate shift** means data distribution changes, BN reduces the distribution of neurons shifts. No matter how `z1` and `z2` changes, BN keeps there mean and std same.
- The dimension of `beta` and `gamma` is `(n^l, 1)`, because BN is used to scale the mean and variance of the input `Z` of each neuron.
- He initialization and ELU can reduce the vanishing gradients **at the begining of training**. BN can address the **vanishing gradients** during **training**.
- **Batch** means evaluating the mean and standard deviation of the inputs over current mini-batch.
- BN can reduce vanishing gradients problem, less sensitive to the weight initialization, reduce the need for other regularization techniques (such as dropout).
- At **test time**, use the whole training set's mean and standard deviation, i.e., **exponential weighted averages** of each mini-batch's `beta` and `gamma`.
- `bias=False` 

## 4. Nerual Networks
### 4.1 Definition
- Neural networks essentially automatic learns **feature crosses**, which is necessary for solving **non-linear** problems.
- Each neuron is **f (weighted average of last layers' outputs)**, where `f` is **non-linear** function.
### 4.2 Back propagation
**Chain rule with memorization.**

### 4.3 How to choose the number of hidden layers ? 
DNN could extract features layer by layer, and it has a **hierarchical architecture**. For many problems, **one or two hidden layers** will works fine. For complex problem, you can gradually increase the number of hidden layers, until overfitting occurs.

### 4.4 How to set the number of neurons per hidden layer ? 
A common strategy is to size the number of neurons to form a funnel (i.e., **deeper layer has fewer neruons**). The analogy is many low-level features are coalesce into fewer high-level features.  
A simple approach is to pick a complex model with early stopping to prevent from overfitting.  

References:  
[1] Hands on machine learning with Scikit-Learn and TensorFlow p271
### 4.5 How does batch size influence training speed and model accuracy ?
Batch gradient descent
- slow
- may converge to local minimum, and yield worse performance
- suffer from GPU memory limitation

Stochastic gradient descent
- fast
- not stable

Mini-batch gradient descent
- fast as SGD (matrix operation with GPU)
- escape from local minimum and more stable

How to set mini-batch size
- If the whole training set size is less than 2,000, then use the whole training data
- Otherwize, 64, 128, 256, 512 is common choices

### 4.6 XOR solution
![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Neural%20network/XOR.png)  

One hidden layer with two neurons. The activation in above image is step function.

## 5. Tips of training DL models
### 5.1 Validate the correctness of public repository
Input 10 training samples, shut down the dropout and L2 regularizations, predict the 10 testing samples (same as the 10 training samples). If the cost is approximately 0, the codes may not have mistakes
### 5.2 Hyperparameter tuning
- Don't use grid search (useful when the number of parameters is small), try **random values**. Say parameters `w1` and `w2`, grid search will loop `w1 = 5` and `w2 = 1, 2, 3, 4, 5`, all of the five models have same `w1`. But with random values, five models can have different `w1`
- **Coarse to fine** strategy
- **Log scale** for learning rate
    - Step 1: suppose that we want to choose learning rate from range `[0.0001, ..., 1]`
    - Step 2: we take `log scale` (with `base 10`), then the range becomes `[-4, 0]`
    - Step 3: uniform choose one paramter with `r = -4 * np.random.randn(), alpha = 10^r`
### 5.3 Learning rate decay
### 5.4 Update parameters by moving average
At each step, update the parameters by their moving average.  
References:  
[1] [Use it in tensorflow](http://ruishu.io/2017/11/22/ema/)  
[2] [example](https://stackoverflow.com/questions/45206910/tensorflow-exponential-moving-average)
### 5.5 dynamic batching

## 6. Regularization
### 6.1 L1 and L2
#### Why are the shape of the L1 norm and L2 norm (aka, weight decay) diamond like and circle like respectively? 
See reference [1].

#### Why does L1 lead to sparse weights and L2 lead to small distributed weights?  
L0 norm is the number of non-zero elements, which has sparse property.  
**L1 norm is the best convex approximation to L0 norm**. We can view L1 norm as a compromise between the L0 and L2 norms, inheriting the sparsity-inducing property from the former and convexity from the latter [2].  
The L1 norm despite being convex, is **not everywhere differentiable** (unlike the L2 norm) [2], see picture from [3].  
![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Andrew_Ng_images/Class_2_week_1/L1_derivative.png)  
Traditional gradient descent cannot be used to optimize L1 regularized models, therefore more advanced techniques like **proximal gradient** or primal-dual methods like ADMM are required [2].  
L1 regularization helps performing **feature selection**.  
Since **squaring a number punishes large values more than it punishes small values** [2], L2 regularization leads to small distributed weights.

#### L1 or L2, which one is perfered in differenct scenario?
Both are used for solve over-fitting.  
In Bayesian view:  
L1 regularization is equivalent to MAP estimation using **Laplacian prior**.  
L2 regularization is equivalent to MAP estimation using **Gaussian prior**.  
Always try L2 regularization first, since it will give you the best result [2].

#### L2 regularization Implementation
  - forward propagation computes cost
	```
	# suppose that there are sigler hidden layer neural network
	# W1 and W2 are parameters for input X and hidden neurons
	# Since we add regularization term, the cost cannot be zero at anytime.
	L2_regularization_cost = 1.0 / m * lambd / 2.0 * (np.sum(np.square(W1)) + np.sum(np.square(W2)))
	cost = cross_entropy_cost + L2_regularization_cost
	```
  - back propagation comptutes gradients
	```
	dZ2 = A2 - Y # the cross_entropy loss
    dW2 = 1./m * np.dot(dZ2, A1.T) + W2 * lambd / m
    db2 = 1./m * np.sum(dZ2, axis=1, keepdims = True)
    
    dA1 = np.dot(W2.T, dZ2)
    dZ1 = np.multiply(dA1, np.int64(A1 > 0)) # relu activation
    dW1 = 1./m * np.dot(dZ1, X.T) + W1 * lambd / m
	db1 = 1./m * np.sum(dZ1, axis=1, keepdims = True)
	```
#### L1 regularization Implementation
- [Coordinate gradient descent](http://www.cs.cmu.edu/afs/cs/project/link-3/lafferty/www/ml-stat2/talks/YondaiKimGLasso-SLIDE-YD.pdf)
- [Proximal gradient descent](https://stats.stackexchange.com/questions/177800/why-proximal-gradient-descent-instead-of-plain-subgradient-methods-for-lasso)

#### Lasso (with L1 regularization) and ridge regression (with L2 regularization).  
The following picture is from [2].  
![](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/Andrew_Ng_images/Class_2_week_1/Lasso_and_ridge.png)  

#### Elastic net (combine L1 and L2)  
```
# from http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNet.html
1 / (2 * n_samples) * ||y - Xw||^2_2 + alpha * l1_ratio * ||w||_1 + 0.5 * alpha * (1 - l1_ratio) * ||w||^2_2
```

References:  
[1] https://www.quora.com/Why-does-an-L1-norm-unit-ball-have-diamond-shaped-geometry#!n=12  
[2] https://www.quora.com/What-is-the-difference-between-L1-and-L2-regularization-How-does-it-solve-the-problem-of-overfitting-Which-regularizer-to-use-and-when  
[3] https://stats.stackexchange.com/questions/45643/why-l1-norm-for-sparse-models  
[4] https://feature.engineering/regularization/  

### 6.2 Dropout
- Intuition: can't rely on any one feature.
- At test time, **do not use** dropout.
- Implementation:
```
d1 = np.random.rand(shape[0], shape[1]) < keep_prob
a1 = np.multiply(a1, d1)
a1 /= keep_prob # inverted dropout
```
### 6.3 Other technicals
- Data augmentation: horizontally flip
- Early stopping

## 7. CNNs
### 7.1 Convolution
- Parameter sharing: feature detector that's useful in one part of the image is probably useful in another part of the image
- Sparsity of connection
- Translation invariance
#### 7.1.1 Filter size
- Usually `odd`, i.e., `3*3`, `5*5`, which has a central point
- Filter kernel: `width * height * number of channels`
- Each filter has a `bias`
- After convolution, we should apply non-linearity, i.e., `relu(convolution + bias)`
#### 7.1.2 Padding
- Role
   - Prevent image size ** shrinking** after convolution
   - Put more emphasis on the corner pixel (i.e., top-left, top-right, down-left, down-right), otherwise, the corner pixel will be convolved once
- Types
   - `Valid`: No padding
   - `Same`: output size is the same as the input size, `p = (filter_size - 1) / 2`
#### 7.1.3 Stride
- `stride=2` means stride both on **horizontal** and **vertical** directions
- Image size after convolution, padding and stride
   - Horizontal direction: `round([(horizontal image size + 2 * padding - filter_size) / stride] + 1)`
   - Vertical direction: `round([(vertical image size + 2 * padding - filter_size) / stride] + 1)`

### 7.2 Pooling
- Hyperparameters: filter size and stride
- Pooling layer has but does **not** have any **learnable parameters**
- Dose not change the number of channels

### 7.3 AlexNet
- **Local Response Normalization (LRN)**: across whole channels

### 7.4 VGG16
- Fixed convolution filter size (3 * 3, stride=1) and pooling size (2 * 2, stride=2)
- VGG16 almost have same performance compared with VGG19
### 7.5 ResNet
- **Residual block**: `a^(l+2) = g(z^(l+2) + a^(l))`
- In extremely scenario with strong regularization, `z^(l+2)` equals `0`, and `a^(l+2) = g(0 + a^(l))`, it turns out that **the identity function is eary to learn for residual block**.
- Can conquer gradients vanishing problem, [why ResNet works ?]()
### 7.6 GoogLeNet
#### 7.6.1 Inception module
- **1 * 1 CONV** + **1 * 1 CONV -> 3 * 3 CONV** + **1 * 1 CONV -> 5 * 5 CONV** + **MAXPOOL 3 * 3, stride=1, same -> 1 * 1 CONV**
#### 7.6.2 1 * 1 convolution
- Work as a **bottleneck layer** for reducing computational cost

## 8. RNNs

### 8.1 LSTM
See colah's great post on [Understanding LSTM Networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/).
### 8.2 Transfering learning and word embeddings
- 1. Learn word embeddings from large text corpus (Or download pre-trained embeddings online).
- 2. Transfer embedding to new task with smaller training set.
- 3. Optional: Continue to finetune the word embeddings with new data.

## 9. Learning Types
### 9.1 Transfer learning
- If your data size is small, just retrain the last layer; if your data size is large, you can retrain last two or three or all layers
- Task A and task B share the same low level features, so transfer learning works
- You can preprocess the input images with frozen layer and save them to disk.
- **Data augmentation methods**
   - Mirroring
   - Random cropping
   - Color shifting: PCA
### 9.2 Multi-task learning
- A set of tasks share the same low level features
### 9.3 End-to-end learning
- Needs large amount of data

## 10. Auto-Encoder
- Data denoising
- Dimension reduction
- Usage: In fraud detection, use Auto-Encoder to compress all data to dense vector, then kNN is used to detect outliers

# Reinforcement Learning
## Definitions
- **Reinforcement learning (RL)** is an area of machine learning that focuses on how **agent** to **act** in an **environment** in order to maximize some given **reward**
- **[Markov Decision Processes (MDPs)](https://web.stanford.edu/class/cs224s/lectures/224s.17.lec11.pdf)**
    - Components
        - **Agent**: decision maker
        - **Environment**
        - **State**
        - **Action**
        - **Reward**
    - **Sequential process**
        - At each time step, given the environment’s state, the agent selects an action to take. Then the environment is transitioned into a new state, and the agent is given a reward as a consequence of the previous action
    - **Goal**
        - The goal of an agent in an MDP is to maximize its cumulative rewards (i.e., expected *discounted* (i.e., care more about the immediate reward over future rewards, discount rate γ) return of rewards)
- **Policy and Value function**
    - **Policy**
        - A function that maps a given state to probabilities of **selecting each possible action** from that state, let symbol **`π`** denotes the policy
    - **Value**
        - **State-value function v_π**: gives us the value of a state under `π`
        - **Action-value function q_π**: gives us the value of an action under `π`. `q_π` is referred to as the **Q-function**, and the output from the function for any given state-action pair is called a **Q-value**. The letter 'Q' is used to represent the **quality** of taking a given action in a given state
    - **RL Goal**
        - Reinforcement learning algorithms seek to **find a policy (i.e., optimal policy) that will yield more return** to the agent than all other policies
- **Bellman optimality equation**
    - ![](https://github.com/gaoisbest/NLP-Projects/blob/master/3_Dialog_system/materials_others/Bellman_optimality_equation.png)
    - For any state-action pair `(s,a)` at time `t`, the expected return is `R_(t+1)` (i.e. the expected reward we get from taking action `a` in state `s`) + the maximum expected discounted return that can be achieved from any possible next state-action pair.
    
- **Q-function**: input the state-atcion pair, output the **Q-value**. The letter **“Q”** is used to represent the **quality** of taking a given action in a given state.
            
## Q-learning
- It is used for learning the **optimal policy** by learning the optimal Q-values for each state-action pair in a Markov Decision Process
- **Q-table**: store the Q-values for each state-action pair, the dimension is **(#states * #actions)**
    - Steps
        - Initialize all Q-values in the Q-table to 0
        - For each time-step in each episode:
            - Choose an action (using the exploration-exploitation trade-off, i.e., **epsilon greedy** strategy)
                - `if random_num > epsilon:` choose action via **exploitation**: choose the action with the highest Q-value for its current state
                - `else:` choose action via **exploration**: randomly choosing action
            - Update the Q-value function
                - ![](https://github.com/gaoisbest/NLP-Projects/blob/master/3_Dialog_system/materials_others/Q-value_formula.png)
                - where α is the **learning rate**, γ is the **discount rate**
### DQN
- Use a neural network to approximate the Q-function
- **Input** the state, **output** the Q-values for each action that can be taken from that state, the **loss** is the gap between the output Q-values (by policy network) and the target Q-values (by target network) from Bellman equation
- **Experience replay**: store the agent’s experiences at each time step called the **replay memory** data set, which stores the last `N` experiences. At time `t`, the agent's experience `e_t` is defined as this tuple: `e_t=(s_t, a_t, r_t+1, s_t+1)`
- **Train** the network with **randomly choose** the samples in replay memory to **break the correlation between consecutive samples**
- **Target network**
    - Clone of the policy network, weights are frozen with policy network’s weights, and after `x` time steps, copy policy network's weights to target network
    - The goal of target network is find the value of the `max` term in Bellman euqation to calculate the target Q-value

## Policy gradient

## Materials
- [MoFan](https://morvanzhou.github.io/tutorials/machine-learning/reinforcement-learning/), [code](https://github.com/MorvanZhou/Reinforcement-learning-with-tensorflow)
- [Baidu RL](https://github.com/gaoisbest/Machine-Learning-and-Deep-Learning-basic-concepts-and-sample-codes/blob/master/reinforcement_learning/Baidu_Reinforcement_Learning_Innovations_and_Applications.pdf)
## References
- http://deeplizard.com/learn/video/nyjbcRQ-uQ8
