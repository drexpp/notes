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

  - **Gradient-Based Learning**
    
    - **(Note)** The largest diﬀerence between the linear models we have seen so far and neuralnetworks is that the nonlinearity of a neural network causes most interesting lossfunctions to become nonconvex. For feedforward neural networks, it is important to initialize all weights to small random values. The biases may be initialized to zero or to small positive values.
    - Cost Functions
      
      In most cases, our parametric model deﬁnes a distribution *p(y | x;θ)* and we simply use the principle of maximum likelihood. This means we use the cross-entropy between the training data and the model’s predictions as the cost function, it is normally followed by a regularization term to avoid over-fitting.
      
      - Learning Conditional Distributions with Maximum Likelihood
        
        Most modern neural networks are trained using maximum likelihood, the cost function is simply the negative log-likelihood, equivalently described as the **[cross-entropy](https://en.wikipedia.org/wiki/Cross_entropy) between the training data and the model distribution**
        
        ![](https://i.imgur.com/FI7DpsV.png)
        
        
      
### Autoencoders [Ali Ghodsi Waterloo university](https://www.youtube.com/watch?v=uaaqyVS9-rM)

  - **An autoencoder learns to compress data from the input layer into a short code, and then uncompress that code into something that closely matches the original data**. This forces the autoencoder to engage in dimensionality reduction, for example by learning how to ignore noise. Some architectures use stacked sparse autoencoder layers for image recognition. The first encoding layer might learn to encode easy features like corners, the second to analyze the first layer's output and then encode less local features like the tip of a nose, the third might encode a whole nose, etc., until the final encoding layer encodes the whole image into a code that matches (for example) the concept of "cat". The decoding layers will learn to decode the learnt code representation back into its original form as close as possible.
  
  ![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/28/Autoencoder_structure.png/350px-Autoencoder_structure.png)
  
  - How to train
    - For each input x, do a feed-forward pass to compute activations at all hidden layers, then at the output layer to obtain an output x'.
    - Measure the deviation of x' from the input x (typically using squared error).
    - Backpropagate the error through the net and perform weight updates.
    
  - More information
  
    - Variational AutoEncoders (VAE) Paper - [Auto-Encoding Variational Bayes](https://arxiv.org/pdf/1312.6114v10.pdf). They basically learn a distribution function with parameters (mean and variance) which you can use to sample new data. On the other hand, autoencoders learns a function to map each input to a number and decoder learns the reverse mapping.
    
    ![](https://qph.fs.quoracdn.net/main-qimg-62c793e38456b093cd83fd5476aed596.webp)
    
    
