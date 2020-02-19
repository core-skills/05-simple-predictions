[Overview](./00_overview.md) |
[Models & Regression](./01_modelsregression.md) |
[Linear Models I](./02_linearmodelsA.md) |
[Linear Models II](./03_linearmodelsB.md) |
[Robust Regression](./04_robustregression.md)  |
[Closeout](./05_closeout.md)

# Robust Regression

| 20 min |
| ------ |

Alternatives to the ordinary least-squares (OLS) regression are sometimes needed when there are outliers present or when errors are not normally distributed.

## RANSAC

RANSAC stands for RANdom SAmple Consensus. The approach seeks to identify outliers in the data by iteratively sampling the data points, fitting a linear model, and using the model to divde the data into *outliers* and *inliers*. 

[RANSAC Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.RANSACRegressor.html#sklearn.linear_model.RANSACRegressor)

## Theil-Sen 

The Theil-Sen regressor fits a line to pairs of points in the data and selects the median slope as the line of best fit.

[Theil-Sen Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.TheilSenRegressor.html#sklearn.linear_model.TheilSenRegressor)

## Huber

 Using an alternative definition of the *loss function* to measure how well the model fits our data in addition to the *mean squared error* is the basis of the [Huber Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.HuberRegressor.html#sklearn.linear_model.HuberRegressor) in scikit-learn.

[Introduction to Loss Functions](https://algorithmia.com/blog/introduction-to-loss-functions)

[Huber regression](https://towardsdatascience.com/generalized-huber-regression-505afaff24c)

## Comparison of robust regression to linear regression

[Robust linear estimator fitting](https://scikit-learn.org/stable/auto_examples/linear_model/plot_robust_fit.html)


[Overview](./00_overview.md) |
[Models & Regression](./01_modelsregression.md) |
[Linear Models I](./02_linearmodelsA.md) |
[Linear Models II](./03_linearmodelsB.md) |
[Robust Regression](./04_robustregression.md)  |
[Closeout](./05_closeout.md)
