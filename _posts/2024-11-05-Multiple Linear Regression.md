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

