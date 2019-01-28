# adaboost-exp3
Fast boosting with AdaBoost and Bandit

In this repository I use the AdaBoostClassifier algorithm from sklearn to implement a version of AdaBoost described in `BuKe10.pdf`.
In this article they split the space of estimators and implement a bandit algorithm which choose in which subspace will be trained the
next estimator. The estimators used are decision stumps and the estimators space is split by feature. Concretly, the action chosen by the
bandit consist in choosing on which feature will be trained the next decision stump.

This algorithm improve the computational complexity of AdaBoost. Below, the error vs the computational time on 6 datasets.

![alt text](https://raw.githubusercontent.com/amarion35/adaboost-exp3/master/results.png)

***

Files:
- `BuKe10.pdf` The Article (Fast Boosting Using Adversarial Bandits)
- `weight_boosting.py` Python module containing the AdaBoostEXP3 class
- `adaboost.ipynb` Notebook with a test

The new class named `AdaBoostClassifierEXP3` take 2 more parameters compared to the original AdaBoostClassifier:
- `mu` : float, optional (default=`None`)
    <br/>This parameter quantify the bandit learning rate. If ``None``, then is set to a value as described in the Theorem 1 of the article 
  with delta=0.05.
- `lamb` : float, optional (default=`None`)
    <br/>This parameter quantify the bandit exploration rate. If ``None``, then is set to a value as described in the Theorem 1 of the article 
  with delta=0.05.
