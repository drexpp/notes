December 2018
==========

Tech
----

### Adversarial examples [Ian Goodfellow lecture](https://www.youtube.com/watch?v=CIfsB_EYsVI)

  -  (**Note**) Multiple linear layers can be equivalent to a single linear layer. As the other answers have said, a nonlinear activation function allows nonlinear classification. Saying that a classifier is nonlinear means that it has a nonlinear decision boundary. The decision boundary is a surface that separates the classes; the classifier will predict one class for all points on one side of the decision boundary, and another class for all points on the other side. [Second reply](https://stats.stackexchange.com/questions/222639/what-makes-neural-networks-a-nonlinear-classification-model)
  
  - A different variety of linear models can be attacked by adversarial examples, such as:
    - Neural networks
    - Linear models:
      - Logistic regression
      - Softmax regression
      - SVMs
    - Decision trees
    - Nearest neighbors
    
### [Deep feedforward networks](http://www.deeplearningbook.org/contents/mlp.html)

Deep feedforward networks are also called Multilayer perceptrons (MLPs). The goal of a feedforward network is to approximate some function f*, for example in classification problems, y = f*(x), where x is the input and y is the category y selected by the network. It defines mapping y = f(x,θ), and it will learn θ, as the parameters that result in the best approximation [Page 164 - first paragraph](http://www.deeplearningbook.org/contents/mlp.html)
  
A feedforward network does not support the outputs, y, of the model to be fed again to the network. It can be extended to support the feedback connections, they are called recurrent neural networks.

We can think of φ (layers, can be thought as a mapping function, which are normally non-linear) as providing a set of features describing **x**, or as providing a new representation for **x**.

We now have parameters θ that we use to learn φ (layers) from a broad class of functions, and parameters **w** that map from φ(x) to the desired output.

  - **XOR example**
  
    The XOR function (“exclusive or”) is an operation on two binary values,x1andx2. When exactly one of these binary values is equal to 1, the XOR functionreturns 1. Otherwise, it returns 0. The XOR function provides the target functiony=f∗(x) that we want to learn. Our model provides a functiony=f(x;θ), andour learning algorithm will adapt the parametersθto makefas similar as possibleto f*.
    
    We want our network to perform correctly on the four points X={[0,0], [0,1], [1,0], and [1,1]}. We will train the network on all four of these points. The only challenge is to ﬁt the training set.
    
      - We can treat this problem as a regression problem and use a mean squared error (MSE) loss function.
      
      - We define our cost function 
        ```
        J(θ) =1/4*sum((f∗(x) − f(x; θ))^2) 
        ```
      - Our model has the form
        ```
        f(x; w, b) = x' .* w + b
        ```
       We won't be able to solve the problem this way because we can't find by normal equations a values for the parameters such as they learn to represent the XOR function since it is not possible to do so with a linear model.  
       
       ![](https://i.imgur.com/Z3hucYc.png)
          
      - We will introduce a simple feedforward network with one hidden layer containing two hidden units. [Go to p.168-172](http://www.deeplearningbook.org/contents/mlp.html#pf6)
      
      - **(Good Note)**  We must use a nonlinear function to describe the features. Most neural networks do so using an aﬃne transformation controlled by learned parameters, followed by a ﬁxed non-linear function called an activation function.
      
      - On rectiﬁed linear activation function, since they apply a non-linear function to a scalar, they can modify the space in which the values of x activate that specific layer, if we imagine that with the same problem of XOR and a linear model we can't separate with a straight line the output points zeros or ones, we use this non-linear transformation of the space, then the non-linear features have mapped both x = [1,0] and x= [0,1] to a single point in feature space, h= [1,0]. The linear model can now describe the function as increasing in h1 and decreasing in h2.
      
      ![](https://i.imgur.com/x0MSqjh.png)
      
      - The graphical idea is this, simply **mind blowing** ([Must have a look, On the Number of Linear Regions of
Deep Neural Networks, Montufar et al., 2014](https://arxiv.org/pdf/1402.1869.pdf))
      
![](https://i.imgur.com/dqcO54M.png)
      
       
