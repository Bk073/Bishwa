Title: Batch Normalization
Date: 2020-07-15 06:42
Category: Deep Learning
Slug: batch-normalization
Summary: Importance of batch normalization
Tags: pelican, markdown
Authors: Bishwa Karki
Status: published

** Why do we need batch norm ? **

Before going into batch norm, lets understand why do we really need it. 
During training deep neural networks the distribution of each layer's input changes, as the parameters changes in the previous layers. So this slow downs the learning by requiring lower learning rate and we have to be careful during parameter initializations. And makes the model harder to train with saturating non linearities. This condition is called ** covariance shift **.
This problem is solved by batch normalization and allows us to use larger learning rate which makes training faster and can be less careful about parameter initialization. Batch normalization limits the covariate shift by normalizing the activation of each layer.

Batch normalization is similar to normalization technique we use in classic machine learning to decrease the variance between features. In deep learning, batch normalization normalizes output of each neuron in each hidden layer according to samples in the mini-batch.

x_normalized = (x - mean) / (standard deviation)

Here, mean and standard deviation are computed for particular mini-batch.

** What about normalization during inference ? **

So the process mentioned above is used during training, i.e we calculate the mean and standard deviation for each batch and process accordingly. So during inference we can't assume mini-batch. But we need to use all the techniques used to process input during training i.e we need the mean and standard deviation.

Once the network has been trained, we use the normalization:

x_normalized = (x - E[x])/ Sqrt(Var[x] + e)

Instead of using the expectation and variance over the population we use it over the mini-batchesto make the performance better.

We calculate on mini-batch of size m:

E[x] <-- E_batch[mean_batch]
Var[x] <-- (m/(m-1)) * E_batch[standard_deviation_batch]

Another way of estimating E[x] and Var[x] is exponentially weighted moving avergae over the mini-batch during training.

- References 

- https://arxiv.org/pdf/1502.03167.pdf