[Overview](./00_overview.md) |
[Models & Regression](./01_modelsregression.md) |
[Linear Models I](./02_linearmodelsA.md) |
[Linear Models II](./03_linearmodelsB.md) |
[Robust Regression](./04_robustregression.md)  |
[Closeout](./05_closeout.md)

# Linear Models I

| 60 min |
| ------ |

## Recap statistics and regression

| 10 min |
| ------ |

| :triangular_flag_on_post: Questions on content discussed this morning? |
| ---------------------------------------------------------------------- |


## Data transformations

| 50 min |
| ------ |

In some cases, it may not be obvious that a linear relatonship exists between the observaton and explanatory variable(s). Data transformations can be used to pre-process data so that linear regression may be used.

Data transformations can be useful in order to help ensure that the [statistical assumptions behind a linear regression](./01_modelsregression.md) are met. In particular, transformations ensuring error variance (heteroscedasticity) and normality assumptions hold.

### Quantile-Quantile plot

| 5 min |
| ------ |

 To get an idea of whether or not a transformation may be needed in order to make the residuals or data meet the criteria of being normal, we can look at histogram or use a quantile-quantile plot.

[Understanding qq plots](https://data.library.virginia.edu/understanding-q-q-plots/)

### Power Transforms

| 15 min |
| ------ |

[How to Use Power Transforms for Time Series Forecast Data with Python](https://machinelearningmastery.com/power-transform-time-series-forecast-data-python/)
#### Reciprocal

y<sup>*</sup> = 1/y = y<sup>-1</sup>

Reciprocal transforms can be useful to make data values more manageable, for example with values that represent ratios. A reciprocal transform does not help in ensuring data and residuals meet assumptions.

#### Logarithm

y<sup>*</sup> = ln(y)

The log transform is a change of base transform. The natural logarithm (base-e) and other logarithms (e.g. base-10, base-2) both fall under this category.

In nature, various phenomena have been shown to exhibit exponential relationships. In many applications, the exponential function shows up often enough that when we think about transformations the natural logrithm transform should come to mind.

[The meaning of exponential](https://www.theguardian.com/science/life-and-physics/2014/jul/20/the-meaning-of-exponential)

[The logarithm transform](https://people.duke.edu/~rnau/411log.htm)

[What are logarithms?](https://www.livescience.com/50940-logarithms.html)

#### Square-root
y<sup>*</sup>  = y<sup>&half;</sup>

Power transforms can take on various forms, and the square-root is another example that may be useful with time-series data. 

#### Box-Cox
y<sup>*</sup>  = y<sup>&#955;</sup>

The Box-Cox is the generalized transformation where the exponent (lambda) defines the power. 

[Box-Cox Transformation](https://www.statisticshowto.datasciencecentral.com/box-cox-transformation/)

#### ...
[scikit-learn demo](https://scikit-learn.org/stable/auto_examples/compose/plot_transformed_target.html#sphx-glr-auto-examples-compose-plot-transformed-target-py)

[scikit-learn scaling with outliers comparison](https://scikit-learn.org/stable/auto_examples/preprocessing/plot_all_scaling.html#sphx-glr-auto-examples-preprocessing-plot-all-scaling-py)

### Polynomial regression

| 10 min |
| ------ |

y = b<sub>0</sub> + b<sub>1</sub>x + b<sub>2</sub>x<sup>2</sup> + ... + b<sub>h</sub>x<sup>h</sup>

In some cases, power transformations are not sufficient to address the complexity exhibited in data. The complexity may be due to a non-linear relationship between the observations and predictors.

An alternative option is to reformulate the linear model we are trying to fit by introducing higher-order terms and solving a polynomial regression. Inclusion of the higher- order terms can be included to increase the complexity of the model while still maintaining a linear model.

y = b + ax + cx<sup>2</sup>

[Polynomial regression](https://towardsdatascience.com/polynomial-regression-bbe8b9d97491)

[scikit-learn polynomial](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PolynomialFeatures.html)

### Resampling

| 10 min |
| ------ |

http://benalexkeen.com/resampling-time-series-data-with-pandas/


## Checkpoint and Wrap-up

| 10 min |
| ------ |

| :triangular_flag_on_post: Is everyone up to speed? How are people going? |
| ------------------------------------------------------------------------ |

[Overview](./00_overview.md) |
[Models & Regression](./01_modelsregression.md) |
[Linear Models I](./02_linearmodelsA.md) |
[Linear Models II](./03_linearmodelsB.md) |
[Robust Regression](./04_robustregression.md)  |
[Closeout](./05_closeout.md)
