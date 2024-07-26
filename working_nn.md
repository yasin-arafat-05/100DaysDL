
---
---

# Step: 01 

- Ask Some Basic Question
- Understand The Dataset
- Fill Missing Value
- Text Vectorization or OHE
- Feature Scaling 

`We all these cover in ml.See the CheatSheet of ML Step:01~03`

---
---
# Step: 02 
## Based on problem statement select activation function and loss function:
## Activation Function:

## Loss Function:
- Regression Problem
    - mse
    - mae
    - huber loss
- Classification Problem
    - BinaryCrossEntrophy
    - CategoricalCrossEntrophy
    - Hinge Loss
- Autoencoders
    - KL Divergence
- Gan
    - Discreminator Loss
    - MinMaxGan Loss
- Embedding
    - Tripled Loss
- ObjectDetection focal Loss

`keras আমাদের কে আমাদের নিজের loss function implement করার functionality provide করে । `

---
---

# Step: 03
## Improve The Performance Of A Neural Network:

- Fine Tuning Neural Network Hyperparameter
- By Solving Some Problem

#### 1) `fine tuning neural network hyperparameter: `
Neural Network  `hyperparameter` গুলো হলোঃ 
- epoch
- hidden layer
- neuron per layer/ nodes
- learning rate
- optimizer
- batch size
- activation function

#### 2) `By  Solving Some Problem: `

- Vanising And Exploding Gradients.
    - `Weight Initialization`
    - `Activation Function`
    - `Batch Normalization`
    - `Gradient Cliping`
- Not Enought Data.
    - `Transfer Learning`
    - `Unsupervised pretraning`
- Slow Traning.
    - `Optimizer`
    - `Learning rate scheduler`
- Overfitting.
    - `L1 and L2 Regularization`
    - `Dropout Layer`
