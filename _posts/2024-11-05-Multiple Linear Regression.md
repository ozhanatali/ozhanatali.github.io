---
layout: post
title: Multiple Linear Regression (MLR)
categories: AI
tags: AI Artificial+Intelligence
konum: İstanbul
---

# Multiple Linear Regression (MLR)

A model with two or more explanatory variables is a multiple linear regression.
This term is distinct from multivariate linear regression, which predicts multiple correlated dependent variables rather than a single dependent variable.

$$ \mathit f_{w,b}(x) = w_{1} x_{1} + w_{2} x_{2} + ... +  w_{n} x_{n} + b_{0} $$

vectors:

$$ \vec{w} = [w_{1} w_{2} w_{3} ... w_{n} ] $$
  
$$ \vec{x} = [x_{1} x_{2} x_{3} ... x_{n} ] $$

$$ \mathit f_{\vec{w},b}(\vec{x}) = \vec{w} . \vec{x}  + b =  w_{1} x_{1} + w_{2} x_{2} + ... +  w_{n} x_{n} + b_{0} $$ 

# Notation

$\vec{x}_{1} ^ 4$  refers to the first feature (first column in the table) of the fourth training example (fourth row in the table)

# Vectorization

Mathematical representation **without vectorisation** 

$$ \mathit f_{\vec{w},b}(\vec{x}) = \left( \sum_{j=1}^n \quad w_{j} x_{j} \right) + b $$

Pyhton code **without vectorisation** :
<code>
f = 0
for j in range (n):
    f = f +w[j] * x[j]
f= f+b
</code></br>

**vectorisation** :

$$ \mathit f_{\vec{w},b}(\vec{x}) = \vec{w} . \vec{x}  + b $$

Pyhton code usign **Numpy DOT functioın**: 
<code>
f=np.dot(w,x)+b
</code></br>
Numpy DOT functioın uses parallel calculation to accelarate the procedures both on CPU or GPU.

# Feature scaling

Feature scaling is a method used to normalize the range of independent variables or features of data. In data processing, it is also known as data normalization and is generally performed during the data preprocessing step.

when you have different features that take on very different ranges of values, it can cause gradient descent to run slowly but re scaling the different features so they all take on comparable range of values. because speed, upgrade and dissent significantly. 

How to:
1. Max scaling (dividing to max value)
2. Mean normalization (dividing to mean value)
3. Z-score normalization (dividing to standard deviation)


- https://www.kaggle.com/code/aimack/complete-guide-to-feature-scaling
- https://medium.com/@punya8147_26846/understanding-feature-scaling-in-machine-learning-fe2ea8933b66
- https://www.geeksforgeeks.org/ml-feature-scaling-part-1/
- https://en.wikipedia.org/wiki/Feature_scaling


# Checking gradient descent for convergence

Assuma a grapgh with J(w,b) on Y axis and #iterations on X axis.
On each iteration the J(w,b)=total cost is expected to decrease materially.
After a many trial/iterations if the decrease becomes immaterial or flat... then it means you need to change the learning rate.

**Automatic convergence test:**

Let Ɛ (epsilon) be 0.001.
If J(w,b) decreases by <=Ɛ in one iteration, declare convergence. (get closer to global minimum)

