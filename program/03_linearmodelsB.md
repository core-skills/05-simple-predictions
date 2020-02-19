[Overview](./00_overview.md) |
[Models & Regression](./01_modelsregression.md) |
[Linear Models I](./02_linearmodelsA.md) |
[Linear Models II](./03_linearmodelsB.md) |
[Robust Regression](./04_robustregression.md)  |
[Closeout](./05_closeout.md)

# Linear Models II

| 90 min |
| ------ |

We'll now have a look at regression for categorical data, and then we'll have a closer look at the training process.

## Categorical Data

| 40 min |
| ------ |

A categorical variable can take a limited, often fixed, number of values assigning each sample to a particular group or category.

| :question: Do you know some examples of categorical data?   |
| ----------------------------------------------------------- |

### Representing categorical data as tidy data

| *10 min* |
| -------- |

| :question: What problems can you encounter with categorical data?   |
| ------------------------------------------------------------------- |

Categorical data can often have unique and meaningless labels, which are had to interpret for QA/QC. And the labels are often misused as variables.

### Logistic regression

| *10 min* |
| -------- |

Logistic regression can be seen as the equivalent of linear regression for categorical data. It is based on a sigmoid function that takes a real number as input and returns a value between 0 and 1:

g(z) = 1/(1 + e<sup>-z</sup>)

This returned value corresponds to the probability that a sample belongs to a given category. Instead of using a real value as input for *z*, we can use a linear model:

z = f(x) = ax + b

Where *a* is the coefficient, *b* is the intercept, and *x* is the input feature. Training a logistic regression means finding *a* and *b* using the data. We can then get label predictions using:

label = g(f(x)) > threshold

### Exercise: Using logistic regression

| *20 min* |
| -------- |

Open [pm1-linear-models-II.ipynb](../notebooks/pm1-linear-models-II.ipynb) and go through exercise 1.

| Short break: 10 min |
| ------------------- |

## Training, validation and test sets

| 40 min |
| ------ |

Fitting a model to data is a subtle process that aims at finding the right balance between under- and overfitting.

### Occam’s Razor: A general overview of validation

| *5 min* |
| ------- |

Occam’s (or Ockham’s) Razor relates to the law of parsimony, and is attributed to Franciscan friar William of Ockham (c. 1287–1347). [It states](http://www.irishphilosophy.com/2014/05/27/who-sharpened-occams-razor/): 

    Entities should not be multiplied without necessity.

Another way to put it for machine learning:
    
    Models should be as simple as possible, but not simpler.

This refers to how to select a model for a particular problem:

* A too simple model will make useless predictions (= under-fitting).
* A too complex model will predict the training data perfectly, but not new data (i.e., it generalizes poorly) (= over-fitting).

### Exercise: Importance of validation

| *20 min* |
| -------- |

Open [pm1-linear-models-II.ipynb](../notebooks/pm1-linear-models-II.ipynb) and go through exercise 2.

[ii. Exercise: Create a model and apply poor validation. Then re-run with a holdout set and measure performance more realistically (10 mins)]

### Bias-variance trade-off

| *15 min* |
| -------- |

The bias-variance trade-off results from minimizing two sources of error at the same time:

* Bias error comes from poor assumptions in the model, i.e., the model can't capture the patterns in the data.
* Variance error comes from a high sensitivity of the model to small fluctuations in the data, i.e., the model captures other patterns than the intended ones, for instance some random noise.

This is where validation on a test set **independent** from the training set is fundamental: it helps to check that the model generalizes well. On some models, it is necessary to check this during training, because predictions on the test set don't always keep improving as training goes on.

Another critical aspect is to get a clear understanding of the data and their relationships during exploratory analysis. This can be related back to transforms and is often a make or break for all machine learning methods. It is perfectly fine to miss some aspects, remember that the workflow is iterative, and that going back to exploratory analysis is always a good idea. 

Beside careful feature engineering, regularization is a common approach to deal with over-fitting. It consists in adding a term in the objective function during training to penalize the more complex models.
