# Deep-Learning-Basics

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#binary-classification">Binary-Classification</a></li>
    <li><a href="#logistic-regression">Logistic-Regression</a></li>
    <li><a href="#gradient-descent">Gradient-Descent</a></li>
  </ol>
</details>

# Binary-Classification
In a binary classification problem, the result is a discrete value output.The goal is to train a classifier that the input is represented by a feature vector, π₯, and predicts whether the corresponding label π¦ is 1 or 0.

#### Example: Cat vs Non-Cat
------------------------------------------------------------
In this case, An image is store in the computer in three separate matrices corresponding to the Red, Green, and Blue color channels of the image. The three matrices have the same size as the image, for example, the resolution of the cat image is 64 pixels X 64 pixels, the three matrices (RGB) are 64 X 64 each.

![image](https://user-images.githubusercontent.com/77977624/171976086-f14f55f2-a5bf-4212-afec-046b640a572b.png)

The value in a cell represents the pixel intensity which will be used to create a feature vector of n-dimension. In pattern recognition and machine learning, a feature vector represents an object, in this case, a cat or no cat.The pixel intensity values will be βunrollβ or βreshapeβ for each color in order to create a feature vector, π₯. 

![image](https://user-images.githubusercontent.com/77977624/171976604-fedf236a-b4d9-4537-8416-bdf92b121a24.png)

# Logistic-Regression
Logistic regression is a learning algorithm used in a supervised learning problem when the output π¦ are all either zero or one. The goal of logistic regression is to minimize the error between its predictions and training data.
#### Loss(error) Function
-----------------------------------------
The loss function measures the discrepancy between the prediction (π¦Μ(π)) and the desired output (π¦(π)).In other words, the loss function computes the error for a single training example. Generally, there are two formulas to compute the loss:

πΏ(π¦Μ(π), π¦(π)) = 1/2(π¦Μ(π) β π¦(π))^2 ----------------------------------(1)

πΏ(π¦Μ(π), π¦(π)) = β[ π¦(π)log(π¦Μ(π)) + (1 β π¦(π))log(1 β π¦Μ(π))] ----------- (2)

In practice, we are more likely to use the second formula rather than the first one as the first one may have local optimums, which would affact the outcomes of prediction. 
#### Cost Funtion
----------------------------------------------------
The cost function is the average of the loss function of the entire training set. We are going to find the parameters π€ πππ π that minimize the overall cost function.

![image](https://user-images.githubusercontent.com/77977624/171987201-33ba35eb-bf12-47b5-8810-65708241257f.png)
#### Example:Cat vs Non-Cat
-------------------------------------------
Given an image represented by a feature vector π₯, the algorithm will evaluate the probability of a cat being in that image.

                               πΊππ£ππ π₯ , π¦Μ = π(π¦ = 1|π₯), where 0 β€ π¦Μ β€ 1

The parameters used in Logistic regression are:

β’ The input features vector: π₯ β βππ₯, where ππ₯ is the number of features

β’ The training label: π¦ β 0,1

β’ The weights: π€ β βππ₯, where ππ₯ is the number of features

β’ The threshold: π β β

β’ The output: π¦Μ = π(π€ππ₯ + π)

β’ Sigmoid function: s = π(π€ππ₯ + π) = π(π§)= 1/1+ π^-z

![image](https://user-images.githubusercontent.com/77977624/171987400-48e99873-a058-4b80-803e-b2eb6ff6ea38.png)

(π€ππ₯ + π) is a linear function (ππ₯ + π), but since we are looking for a probability constraint between [0,1], the sigmoid function is used. The function is bounded between [0,1] as shown in the graph above.

# Gradient Descent
In order to find the parameters π€ πππ π that minimize cost function J(π€, π) so that implementing logistic regression, we introduce a mathematical strategy called Gradient Descent. The figure below illustrates how Gradient Descent works in finding global optimum of J(π€, π). In the case of Gradient Descent, gradient also as known as derivative which means we are about to take derivative of J respect to π€ and π.

![image](https://user-images.githubusercontent.com/77977624/174477597-5678616d-11b1-49f3-8eac-8c285133344d.png)

To have a better insight into Gradient Descent, we make mathematical analysis along π€ axis and π axis respectively. The next figure represents the correlation of cost function J with π€. From which, it is noted that we can find π€ that corresponding to the optimum of J by updating π€ iteratively. We follow the formula below to update π€: π€ := π€ - Ξ± * d(J(π€))/dπ€, where Ξ± is learning rate. As we can see, the derivative of J respect to π€ is smaller than zero on the right side of the optimum, while it is greater than zero on the left side of the optimum. Thus, π€ is getting closer and closer to the optimum after every iteration.

![image](https://user-images.githubusercontent.com/77977624/174477991-db237ec3-7150-4091-b0e6-994d19471590.png)


