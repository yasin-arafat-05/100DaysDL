
# uses of activation function: 

<br>

Activation functions are a crucial part of neural networks, determining the output of a model's node given an input or set of inputs. The choice of activation function can significantly impact the performance and convergence of a model. Here are common activation functions and the types of problems where they are typically used:

### 1. **Sigmoid Activation Function**
- **Formula:** $\sigma(x)$ = $\frac{1}{1 + e^{-x}}$
- **Range:** (0, 1)
- **Properties:** Non-linear, causes vanishing gradient problem, not zero-centered.
- **Use Cases:** 
  - **Binary Classification:** Outputs probabilities in logistic regression and binary classifiers.
  - **Output Layer of Binary Classifiers:** Commonly used in the output layer to produce a probability value.

### 2. **Tanh (Hyperbolic Tangent) Activation Function**
- **Formula:** $\tanh(x)$ = $\frac{e^x - e^{-x}}{e^x + e^{-x}}$
- **Range:** (-1, 1)
- **Properties:** Non-linear, zero-centered, also suffers from the vanishing gradient problem.
- **Use Cases:**
  - **Binary Classification:** Can be used in hidden layers for binary classification problems.
  - **Recurrent Neural Networks (RNNs):** Commonly used in the hidden layers of RNNs.

### 3. **ReLU (Rectified Linear Unit) Activation Function**
- **Formula:** $\text{ReLU}(x)$ = $\max(0, x)$
- **Range:** [0, ∞)
- **Properties:** Non-linear, helps mitigate the vanishing gradient problem, can suffer from dying ReLUs.
- **Use Cases:**
  - **Hidden Layers of Deep Neural Networks:** Most commonly used in the hidden layers of CNNs and feedforward networks.
  - **Image Classification and Object Detection:** Due to its simplicity and effectiveness in deep networks.

### 4. **Leaky ReLU Activation Function**
- **Formula:** $\text{Leaky ReLU}(x)$ = $\begin{cases} x & \text{if } x \geq 0 \\ \alpha x & \text{if } x < 0 \end{cases}$
- **Range:** (-∞, ∞)
- **Properties:** Non-linear, allows a small gradient when the unit is not active (α is a small constant, e.g., 0.01).
- **Use Cases:**
  - **Hidden Layers of Deep Networks:** Helps in scenarios where ReLU suffers from dying neurons.
  - **Speech and Image Processing:** Applied in networks requiring non-zero gradient for negative inputs.

### 5. **ELU (Exponential Linear Unit) Activation Function**
- **Formula:** $\text{ELU}(x)$ = $\begin{cases} x & \text{if } x \geq 0 \\ \alpha (e^x - 1) & \text{if } x < 0 \end{cases}$
- **Range:** (-α, ∞)
- **Properties:** Non-linear, helps mitigate the vanishing gradient problem, smooth gradient for negative values.
- **Use Cases:**
  - **Deep Neural Networks:** When robustness to noise and smoother learning is needed.
  - **Various Applications:** Used in different types of neural networks.

### 6. **Softmax Activation Function**
- **Formula:** $\text{Softmax}(x_i)$ = $\frac{e^{x_i}}{\sum_{j} e^{x_j}}$
- **Range:** (0, 1) with outputs summing to 1
- **Properties:** Converts logits to probabilities, used in multi-class classification.
- **Use Cases:**
  - **Output Layer of Multi-Class Classifiers:** Produces a probability distribution over multiple classes.
  - **Neural Machine Translation (NMT):** In the output layer to predict the next word.

### 7. **Swish Activation Function**
- **Formula:** $\text{Swish}(x)$ = $x \cdot \sigma(x)$
- **Range:** (-∞, ∞)
- **Properties:** Non-linear, smooth curve, mitigates vanishing gradient problem, self-gated.
- **Use Cases:**
  - **Deep Learning Architectures:** Effective in deep networks for image classification and NLP tasks.
  - **State-of-the-Art Models:** Used in advanced architectures like EfficientNet.

### Summary Table

| Activation Function | Range       | Properties                                           | Common Use Cases                                     |
|---------------------|-------------|------------------------------------------------------|------------------------------------------------------|
| Sigmoid             | (0, 1)      | Non-linear, vanishing gradient problem, not zero-centered | Binary classification, output layer for binary classifiers |
| Tanh                | (-1, 1)     | Non-linear, zero-centered, vanishing gradient problem | RNNs, hidden layers for binary classification         |
| ReLU                | [0, ∞)      | Non-linear, mitigates vanishing gradient, can die    | CNNs, deep neural networks, image classification     |
| Leaky ReLU          | (-∞, ∞)     | Non-linear, small gradient for negative inputs       | Deep networks, speech and image processing           |
| ELU                 | (-α, ∞)     | Non-linear, smooth gradient for negative values      | Deep neural networks, various applications           |
| Softmax             | (0, 1)      | Converts logits to probabilities, outputs sum to 1   | Output layer for multi-class classification, NMT     |
| Swish               | (-∞, ∞)     | Non-linear, smooth curve, self-gated                 | Deep learning architectures, state-of-the-art models |

Choosing the right activation function depends on the specific problem and the architecture of the neural network. Experimenting with different activation functions and evaluating their performance on validation data is often necessary to determine the best choice for a given application.


