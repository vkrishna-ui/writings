+++
date = '2026-05-25T00:55:26-04:00'
draft = true
title = 'Stochastic gradient descent and Diffusion models'
mathjax: true
+++
### SGD as an early diffusion model
Generative diffusion models aim to reconstruct an underlying probability distribution from a given 
set of samples/observations (this is a bit crude in description, as diffusion models actually 
approximate a score function, partly because estimating partition functions is hard). They 
have been very successful in methods that predict protein structures from a given sequence. 

Why do generative diffusion models work so well to predict protein structures from sequences, 
and do they capture attributes of protein dynamics that could be used to approximate the biophysical 
properties of proteins? Furthermore can they be adapted to help approximate free energies and 
thermodynamic properties of proteins? These are very desirable goals for a variety of practical 
applications in protein design.

Interestingly enough, stochastic gradient descent (SGD) that is widely used to train deep learning models 
has ideas in common to those used in diffusion models. For starters, what is SGD? Typically in order to 
train a machine learning model, one estimates an empirical mean loss by comparing the predicted output 
of the machine learning model to the observed output for each of a set of training samples and averaging 
this over the training set. One then estimates the gradient of this mean loss upon changing the parameters 
of the ML model and moves “downwards” in the direction of the greatest change, and this is iterated until 
a minimum is reached. This approach can be computationally expensive when the number of training samples is 
very large, as is often the case with modern deep learning methods. 
Robbins and Monro (Annals of Statistics 1951) first introduced SGD, wherein instead of evaluating the 
gradient for a loss estimated over the entire training set, one estimates gradients for a randomly 
chosen subset of training samples.

In mathematical terms, let $$ \theta $$ be a set of parameters of a ML model that we want to optimize, 
by minimizing an expected loss $$ \( E[L(X,\theta)] \) $$ with the expectation taken over the distribution of 
(training) samples. In traditional gradient descent we update the parameters using the rule:

$$ 
\theta(t+1) = \theta(t) − \eta_{t}\nabla_{\theta}E[L(X,\theta)]
$$


Here the expectation value of the loss is approximated by the empirical mean loss over the set of training 
samples. In SGD, the expectation value is replaced by a mean over a small, randomly chosen subset of samples, 
or even a single sample.

The fundamental equation of quantum mechanics is Schrodinger's equation, represented inline as $i\hbar \frac{\partial}{\partial t}\Psi(\mathbf{r},t) = \hat{H}\Psi(\mathbf{r},t)$ inside text.

### Block Equations
To show standard standalone mathematical proofs, break them into a multi-line equation display block:

$$
W(x) = \int_{-\infty}^{\infty} \psi^*(p) e^{ipx/\hbar} \, dp
$$

