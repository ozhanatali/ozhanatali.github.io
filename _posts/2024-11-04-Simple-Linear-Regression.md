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

# Cost function / Squared error cost function / Mean Squared Error (MSE)

The cost function is the difference between our estimated value and the actual value on the line. The smaller this difference is, the closer our estimates will be to reality. The graph below will better understand what we mean.

$$J(w,b) = {1 \over 2m} {\sum_{i=1}^m } \left( ŷ^i-y^i  \right)^2$$

where:
- i =  index of sample
- ŷ =  predicted value
- y =  expected value
- m =  number of samples in the data set
- $$(ŷ-y)$$ is called error and 
- $$(ŷ^i-y^i)$$ error for a specific point.
- Above cost function sums the all differences starting from 1st input to the $$(m^th$$ input to calculate the **total** square error.
We calculate the **average** square error by dividing it to m (or more commanly 2m).

# Goal of linear regression

Our goal is to minimizing the cost function :

$$\underset{w,b}{\text{minimize }} J(w,b)$$

# Gradient descent

Gradient descent is used to minimize any function that have more than two parameters.

- Goal: We want to find the lowest point of a function, where errors are minimized.
- Going Downhill: Imagine standing on a hill and wanting to reach the bottom. Gradient descent helps us go down the hill in the fastest way.
- Finding the Slope: We calculate the slope of the hill where we are. The slope tells us which direction to move to go down.
- Small Steps: We take small steps downhill. These steps are called the "learning rate." If steps are too big, we might miss the goal; if too small, we go slowly.
- Repeat: We keep calculating the slope and moving down in steps until we reach close to the bottom.
- Result: Once we are near the lowest point, we stop. This is the best solution we were looking for.

repeat until convergence (local minimum where the parameters w and b no longer change much with each additional step):

$$ w=w-α \left(\frac{\partial}{\partial w} \quad J(w,b)\right)  $$

$$ b=b-α \left(\frac{\partial}{\partial b} \quad J(w,b)\right)  $$


where
- α = learning rate
- d/dw = derivative of..

above calculations for both w and b should be simultaneously (need to change them both together although they effect each other).
- DO NOT update b or w in the function and then update the next
- DO together by assigning some temproray variable
- α (learning rate) is always positive. Derivative is used to determine the descent direction:
    - if result of derivative is positive (positive slope) w decreases
    - if result of derivative is negative (negative slope) w increases

# Types of Gradient descent

**1. Batch gradient descent (BGD)**

The term batch gradient descent refers to the fact that on every step of gradient descent, we're looking at all of the training examples, instead of just a subset of the training data. (+)Stability (+)Accuracy (-)Performance

**2. Stochastic Gradient Descent (SGD)**

Stochastic Gradient Descent (SGD) is a simplified version of Gradient Descent (GD) that addresses some of its challenges. In SGD, the gradient is computed for only one randomly selected partition of the shuffled dataset during each iteration, instead of using the entire dataset. 

**3. Mini-Batch Gradient Descent**

Data is splitted into small batches and then compute loss for each. The weights are updated after each batch.



<br/>
## Choise of learning rate 

- if α is too small ===> slow to reach minimum
- if α is too large ===> overshoot, might never reach to minimum
- when the function reach to local mimimum ===> the slope (and therefore the derivative of the function) becomes zero
- multiplying the learning rate with zero ===> does nothing once reached to mimimum & keeps it on the local minimum level
- **As we approach the local minimum, the derivative automatically gets smaller. And that means the update steps also automatically gets smaller. Even if the learning rate alpha is kept at some fixed value.**

<br/>
## Choise of learning rate 
- a **squared error cost function with linear regression**, the cost function does not and will never have multiple local minima
- a **convex function** is of bowl-shaped function and it cannot have any local minima other than the single global minimum.
- When you implement gradient descent on a convex function, one nice property is that so long as you're learning rate is chosen appropriately, it will always converge to the global minimum.

# Refs
- https://builtin.com/machine-learning/cost-function
- https://www.kaggle.com/code/mwaseem75/cost-function-for-linear-regression
- https://medium.com/@yennhi95zz/3-understanding-the-cost-function-in-linear-regression-for-machine-learning-beginners-ec9edeecbdde
- [Gradient descent Wiki Page](https://en.wikipedia.org/wiki/Gradient_descent)
- https://medium.com/@jaleeladejumo/gradient-descent-from-scratch-batch-gradient-descent-stochastic-gradient-descent-and-mini-batch-def681187473
- https://deepgram.com/ai-glossary/batch-gradient-descent

# Out of the concept
Following page gives a great summary of MathJax library which is inherently supported by markdown lang of github:
[MathJax Tutorial and Quick Ref](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)
