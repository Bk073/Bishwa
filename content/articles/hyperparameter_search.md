Title: Hyperparameter search
Date: 2020-07-22 06:42
Category: Deep Learning
Slug: hyperparameter-search
Summary: Finding best hypeparameter
Tags: pelican, markdown
Authors: Bishwa Karki
Status: published


Hyperparameters are setting on which model finds best parameters during training. The model parameters directly uses the input data to get the desired output but hyperparameters determine how the parameters are learned.
During optimization, the optimization function finds the parameters that minimizes the cost functions. But this can be particularly important how set up the hyperparameters for the model. So we need to find the hyperparameters that helps finding the best parameters.

There are following approaches to hyperparameter optimization in my knowledge:
1. Manual Search
2. Grid Search
3. Random Search
4. Automated Hyperparameter Tuning(Bayesian Optimization, Genetic Algorithms)

## Grid Search

In grid search, the hyperparameters are searched from a grid of combination of range of possible values.

    |     | 100|200|300|
    |0.01 | 1  | 2 |3|
    |0.001| 4  | 5 |6|

Suppose if we take number of neurons and learning rate as example, depicted in the above table. Then here we can see 6 combinations of parameters that can we used from the above grid.

But this can be problemmatic or may be matter of luck to find the best combination that best describes the model architecture. So it can take longer time if the hyperparameter grows.

## Random Search:

As we saw from above that grid search takes longer time to search best possible combination. So in random search approach we randomly sample hyperparameters from prespecified distribution such as uniform or gaussian distribution.
What exactly we do here is, we pick a random hyperparameter and focus more the region where it is more likely to be best. Now we will focus sampling more densely into the smaller region.

Although this method in beneficial to find best among the various randomly sampled hyperparameters, we cannot find the best possible hyperparameters. To find the best hyperparameter, we need to sample the hyperparameters a large number of times. This takes longer time but still it is better than grid search.

