# Conditional Random Tree
Charles Sutton et al., _An Introduction to Conditional Random Field_, 2010
## Introduction

> - predict multiple random variable $\textbf{y}=(y_0,...,y_T)$ that depend on each other given vectors $(\textbf{x}_0,...,\textbf{x}_T)$
> - However learining an independant per position classifier $\forall s ,~x \to y_s$ is difficlebecause of high dependency

>_generative_ model attempt to model a joint probability distrib $p(\textbf{x,y})$
> -  x dimention can be very large
> - features have comple dependencies
difficult to construct proba distribution

>CRF tries to model $p(\textbf{y}|\textbf{x})$

## Modelling
### Notation
- $X$ set of input variable
- $Y$ set of output variables
- sets of random variables $V=X\cup Y$
- $\textbf{x}$ is an arbitrary assigment of $X$
- $\textbf{1}_{x=x'}=\left\lbrace\begin{array}{cc}1 &\text{if~} x=x'\\ 0 &\text{otherwise}\end{array}\right.$

### Graph Markov
> **Couverture de markov** = parents + enfants + parents des enfants
>![Couverture de Markov](https://upload.wikimedia.org/wikipedia/commons/e/ea/MarkovBlanket.png)
 
### Directed Models
it describes how  a distribution factorises into lacal conditional probability distribution

$$p(\textbf{y,x})=\prod_{v\in\mathcal{V}}p(y_v|\textbf{y}_{\pi(v)})$$
- $\pi(v)$ : parents of v

For directed graphs $Z=1$

## Generative Vs Discriminative Models

### Naive Bayes Classifier
$$ p(x,y)=p(y)\prod_{k=1}^K p(x_{k}|y)$$ 

## Logistic Regression
logistic Regression = Maximum entropy Classifier  
 $$p(y|x)=\frac{1}{Z(x)}exp\left(\theta_y+\sum_{j=1..K}\theta_{y,j}x_j\right)$$
 
 $$Z(x)=\sum_y exp\left(\theta_y+\sum_{j=1..K}\theta_{y,j}x_j\right)$$
 
 Introducing *feature function* $f_{y,j'}$
 
 $$Z(x)=\sum_y exp\left(\theta_y+\sum_{j=1..K}\theta_{k}f_{k}(y,\textbf{x})\right)$$
 
