[Overview](./00_overview.md) |
[Models & Regression](./01_modelsregression.md) |
[Linear Models I](./02_linearmodelsA.md) |
[Linear Models II](./03_linearmodelsB.md) |
[Robust Regression](./04_robustregression.md)  |
[Closeout](./05_closeout.md)

# Models and Regression

| 120 min |
| ------- |

:heavy_exclamation_mark: Whenever you have an issue related to data analysis and machine learning, go check scikit-learn's website [scikit-learn.org](https://scikit-learn.org/), they put up a nice documentation:

[scikit-learn.org/stable/user_guide.html](https://scikit-learn.org/stable/user_guide.html)

With a lot of examples:

[scikit-learn.org/stable/auto_examples/index.html](https://scikit-learn.org/stable/auto_examples/index.html)

And a glossary:

[scikit-learn.org/stable/glossary.html](https://scikit-learn.org/stable/glossary.html)

## Regression as machine learning and the scikit learn framework

| 90 min |
| ------ |

### Short introduction to data analytics and machine learning

| *10 min*  |
| --------- |

| :question: What are the main steps of the data analysis workflow?   |
| ------------------------------------------------------------------- |

We had an overview of the data analysis workflow on day 3, which consists in going iteratively through the following steps:

1. Import
2. Tidy
3. Explore
4. Model
5. Report

Machine learning corresponds to step 4, and is fundamentally about “building models of data”. It has philosophical connections to artificial intelligence and human and animal learning, but these are mostly irrelevant in practice.

### Exercise: Explore a dataset using pandas and seaborn

| *20 min*  |
| --------- |

Open [am1-models-and-regression.ipynb](../notebooks/am1-models-and-regression.ipynb) and go through exercise 1.

### Categories of machine learning

| *15 min*  |
| --------- |

Machine learning methods turns inputs into outputs using a model, i.e., a formula with parameters inferred from the data. The inputs and outputs are variables representing numerical or categorical quantities, and inputs are often called "features". Training a model means finding its parameters based on the available data. Once a model is trained, it can be used to make prediction using new inputs.

The outputs define the main classification of machine learning methods:

* Supervised learning requires to have data whose samples contain both inputs and outputs. In this case, the outputs are often called labels and correspond to the ground truth.
* Unsupervised learning requires to have data whose samples contain inputs only. In this case, there is no ground truth to refer to, and the algorithm tries to understand the patterns within the data to group or organize them in a sensible way.

Supervised and unsupervised learning can be subdivided depending on the type of output variable, i.e., continuous or discrete (also called categorical). Supervised learning encompasses:

* Regression, which predicts continuous values based on the inputs.
* Classification, which predicts categorical values based on the inputs.

Similarly, unsupervised learning encompasses:

* Dimensionality reduction, which reduces the number of inputs while preserving as much information as possible.
* Clustering, which groups samples with similar characteristics.

Today, we'll talk about linear and logistic regression.

| :question: In which of the previous categories do they fit?   |
| ------------------------------------------------------------- |

| :question: How industry problems fit into these categories?   |
| ------------------------------------------------------------- |

Scikit-learn has a nice flowchart to help find the right method for the right problem and dataset: 

[scikit-learn.org/stable/tutorial/machine_learning_map/index.html](https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html)

### Scikit-learn basics and API

| *10 min*  |
| --------- |

Scikit-learn is a machine learning package in Python built on NumPy, SciPy, and matplotlib to provide "simple and effective tools for predictive data analysis". It includes many models and functions to pre-process the data and train those models.

Before using scikit-learn, you need to make sure that your data are in a tidy table format, with each row corresponding to a sample (i.e., an observation) and each column to a feature (i.e., a variable). Many methods output a single feature (i.e., one dimension), though there are exceptions.

The API is consistent across methods, based on three main steps:

1. Define the model:
   ```
   model = LinearRegression()
   ```
2. Train the model:
   ```
   model.fit(x_train, y_train)
   ```
   Where *x_train* is a table of shape (n_samples, n_features) and *y_train* is a table of shape (n_samples). *y_train* is the target array, and is only used in supervised learning.
3. Predict using the model:
   ```
   y_pred = model(x_pred)
   ```

### Exercise: Linear regression with scikit-learn

| *20 min*  |
| --------- |

Open [am1-models-and-regression.ipynb](../notebooks/am1-models-and-regression.ipynb) and go through exercise 2.

| :triangular_flag_on_post: Use GitHub to save your notebook   |
| ------------------------------------------------------------ |

| Short break: 15 min |
| ------------------- |

## Statistical assumptions in linear regression problems

| 30 min |
| ------ |

### Overview of least-squares linear regression

| *5 min* |
| ------- |

The linear regression model is one of the most basic statistical models used in predictive analysis: it proceeds by fitting a linear equation to observed paired data to attempt to model the relationship between two variables:

y = ax + b

Where *y* is the output, or dependent variable, *a* is the coefficient, corresponding to the slope of the line, *b* is the intercept, and *x* is the input feature, or explanatory variable.

*a* and *b* are the two parameters that are determined during training. 

### Statistical assumptions behind a linear regression

| *5 min* |
| ------- |

Technically, several assumptions has to be met to use a linear regression based on the idea of a random term on top of the linear model:

1. The average random error is equal to 0 (i.e., the model has no bias).
2. The variance of the random error is constant (aka the homoscedasticity assumption).
3. The error term is independent of the explanatory and dependent variable.
4. The distribution of the random error is Gaussian.

lotting residuals can help to check that those assumptions are met.

### Exercise: Perturbing perfect linear data

| *10 min* |
| -------- |

Open [am1-models-and-regression.ipynb](../notebooks/am1-models-and-regression.ipynb) and go through exercise 3.

### R<sup>2</sup>, the coefficient of determination

| *5 min* |
| ------- |

R<sup>2</sup>, called R squared or coefficient of determination, is used as a goodness of fit measure for linear regression models, i.e. to determine how well the regression model fits the data. It actually measures the proportion of the variance in the dependent variable that the explanatory variable explains.

R<sup>2</sup> has some limitations: 
* It does not account for the number of paired data used.
* It does not indicate if the explanatory variable used is appropriate.
* It does not indicate if the regression used is appropriate.
* It does not indicate if the model is biased.

Therefore it should not be the only criteria used to assess the goodness of the linear regression model. It’s important to check whether a linear model is appropriate and whether transformations lead to better results.

### Correlation and independence

| *5 min* |
| ------- |

:heavy_exclamation_mark: If two variables are independent, the correlation coefficient is equal to 0, but the inverse isn't true: this coefficient measures the linear dependencies between two variable, and misses any non-linear dependency.
