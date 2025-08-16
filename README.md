Gaussian Proces based optimization
===================================================

Overview
--------

This project employs the GPR-UCB algorithm to perform few-shot reinforced optimization on the mechanical properties dataset of IN625/WC composite coatings.

This README file contains instructions for project running. To run this
project, you need to install the python runtime, jupyter notebook, scikit-learn
and other relative dependencies.

Modeling Process
---------------------------------

### Data preprocessing

First, data points with large errors were excluded. Subsequently, the dataset was standardized using a normalization approach, ensuring that all data points exhibit a mean approximately equal to 0 and a variance close to 1, thereby eliminating the scale effects among different physical quantities.


### GPR modeling

Gaussian Process Regression (GPR) was selected as the primary modeling approach due to its strong generalization capability and interpretability in small-sample, nonlinear regression problems, making it particularly suitable for the limited experimental data in this study. In addition, GPR provides an evaluation of prediction uncertainty, which facilitates its integration with the Upper Confidence Bound (UCB) strategy for process parameter optimization. 

### Ten-fold cross validation

The dataset was randomly divided into ten equal subsets. In each iteration, one subset was selected as the test set, while the remaining nine subsets were used for training.  This process was repeated ten times to ensure that each subset served as the test set for evaluation, ultimately yielding the model's overall performance across all subsets. This approach not only enables efficient utilization of the limited dataset but also enhances the robustness of model evaluation, reducing the bias introduced by a single data split.

### UCB algorithm

The Upper Confidence Bound (UCB) algorithm is a strategy widely employed for optimization and exploration, aiming to strike a balance between exploration (i.e., testing regions with high uncertainty) and exploitation (i.e., prioritizing regions currently predicted to yield better outcomes). Within the UCB theoretical framework, μ(X) represents the predicted reward of the current model at a given point, while σ(X)denotes the predictive uncertainty at that point. The magnitude of β determines the trade-off between exploration and exploitation.


Project Runtime Installation
------------------------------

| tool/dependency  | Version |
|------------------|---------|
| python           | 3.11.5  |
| jupyter notebook | 6.5.4   |
| scikit-learn     | 1.3.0   |
| matplotlib       | 3.7.2   |
| pandas           | 2.0.3   |


Documentation
-----------

Please refer to the references in the paper for details.