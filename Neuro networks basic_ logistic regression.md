---
title: 'Neuro networks basic: logistic regression'
tags: Fansipan
---
# A simple neuro network, binary classification problem 
- An overview of a simple neuron network
![](https://i.imgur.com/1t4bg9b.png)


### Our goal: 
**Goal:** To minimize $L(\hat{y},y)$ function, which take shape of a convex function. In order to do that, we using a method called Gradient Decent.

How Gradient Descent look like:
![](https://cdn-images-1.medium.com/max/1000/0*w3NhX-qzxAeU6WAv.gif)
### Our input format: 
- X(n, m)
- Y(1, m)
### Forward propagation: 
1. z linear combination
    $z = w^{T}x + b$ 
    
    with $w$ is the weight and $b$ is a constant
2. a is an activate fuction. Here we use sigmoid function for binary classification.
    $a = \sigma(z)$ with $\sigma =\frac{1}{1+e^{-z}}$
    ![](https://i.imgur.com/6ifl3WI.png)

3. Loss function: 
    $L(\hat{y} ,y) = -(y.log(\hat{y}) + (1-y)log(1 - \hat{y}))$ with $\hat{y} = \sigma(w^{T}x + b)$
4. Coss function: 
    $J(w,b)=\frac{1}{m}\Sigma L$
    
### Backward propagation: 


1. $da = L'(a) = \frac{dL}{da} = \frac{y}{a} - \frac{1-y}{1-a}$

2. $dz= L'(z) = \frac{dL}{dz} = \frac{dL}{da}\frac{da}{dz} = (\frac{y}{a} - \frac{1-y}{1-a})a(1-a) = a - y$

3. $dw= L'(w) = \frac{dL}{dw} = \frac{dL}{dz} \frac{dz}{dw} = (a-y)x$

4. $db = L'(b) = \frac{dL}{db} = \frac{dl}{dz} \frac{dz}{db} = dz$

## Optimization: 



1. $w = w - \alpha dw$
2. $b = b - \alpha db$

with $\alpha$ is the learning rate. 
$\alpha$, $w$ and $b$ are hyperparameters 
