---
layout: post
title: Linear-Regression
categories: AI
tags: AI Artificial+Intelligence
konum: İstanbul
---


# Linear regression

Linear regression model is a particular type of supervised learning model.
Linear regression is one example of a regression model. But there are other models for addressing regression problems too.
In contrast with the regression model, the other most common type of supervised learning model is called a classification model.
In classification, there are only a small number of possible outputs, whereas in regression, there are infinitely many possible numbers that the model could output.

# Terminology

- **Training set** : Data used to train the model
- **x** : input variable / features
- **y** : output/target variable
- **m** : number of training examples
- **(x,y)** : single training example
- **𝑥(𝑖),𝑦(𝑖)** : 𝑖𝑡ℎ Training Example (not an exponentiation/ refers to the index)


x (feature) --> learning algorithm / function (model) --> y (prediction)

Linear function / Linear regression with one variable / Univariate linear regression
f(X)=wx+b

# Cost function / Squared error cost function

The cost function is the difference between our estimated value and the actual value on the line. The smaller this difference is, the closer our estimates will be to reality. The graph below will better understand what we mean.

$$J(w,b) = {1 \over 2m} {\sum\_{i=1}^m } \left( ŷ^i-y^i  \right)^2$$



# Out of the concept
Following page gives a great summary of MathJax library which is inherently supported by markdown lang of github:
https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference
