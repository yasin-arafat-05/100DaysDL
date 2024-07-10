
<br>
<br>
<br>


# Summary Table with Loss Functions And Activation Function:

| Activation Function | Range       | Properties                                           | Common Use Cases                                     | Associated Loss Functions                            |
|---------------------|-------------|------------------------------------------------------|------------------------------------------------------|-----------------------------------------------------|
| **Sigmoid**         | (0, 1)      | Non-linear, vanishing gradient problem, not zero-centered | Binary classification, output layer for binary classifiers | Binary Cross-Entropy Loss (BCE)                      |
| **Tanh**            | (-1, 1)     | Non-linear, zero-centered, vanishing gradient problem | RNNs, hidden layers for binary classification         | Mean Squared Error (MSE), Mean Absolute Error (MAE) |
| **ReLU**            | [0, ∞)      | Non-linear, mitigates vanishing gradient, can die    | CNNs, deep neural networks, image classification     | Mean Squared Error (MSE), Mean Absolute Error (MAE) |
| **Leaky ReLU**      | (-∞, ∞)     | Non-linear, small gradient for negative inputs       | Deep networks, speech and image processing           | Mean Squared Error (MSE), Mean Absolute Error (MAE) |
| **ELU**             | (-α, ∞)     | Non-linear, smooth gradient for negative values      | Deep neural networks, various applications           | Mean Squared Error (MSE), Mean Absolute Error (MAE) |
| **Softmax**         | (0, 1)      | Converts logits to probabilities, outputs sum to 1   | Output layer for multi-class classification, NMT     | Categorical Cross-Entropy Loss                      |
| **Swish**           | (-∞, ∞)     | Non-linear, smooth curve, self-gated                 | Deep learning architectures, state-of-the-art models | Mean Squared Error (MSE), Mean Absolute Error (MAE) |

### Details on Loss Functions

1. **Binary Cross-Entropy Loss (BCE):**
   - **Formula:** \(\text{BCE}(y, \hat{y}) = -\frac{1}{N} \sum_{i=1}^N [y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i)]\)
   - **Use Cases:** Used with sigmoid activation for binary classification problems.

2. **Categorical Cross-Entropy Loss:**
   - **Formula:** \(\text{CCE}(y, \hat{y}) = -\sum_{i=1}^N \sum_{j=1}^C y_{ij} \log(\hat{y}_{ij})\)
   - **Use Cases:** Used with softmax activation for multi-class classification problems.

3. **Mean Squared Error (MSE):**
   - **Formula:** \(\text{MSE}(y, \hat{y}) = \frac{1}{N} \sum_{i=1}^N (y_i - \hat{y}_i)^2\)
   - **Use Cases:** Regression problems, commonly used with ReLU, Leaky ReLU, ELU, tanh, and swish activations.

4. **Mean Absolute Error (MAE):**
   - **Formula:** \(\text{MAE}(y, \hat{y}) = \frac{1}{N} \sum_{i=1}^N |y_i - \hat{y}_i|\)
   - **Use Cases:** Regression problems, robust to outliers, used with activations like ReLU, Leaky ReLU, ELU, tanh, and swish.


<br>
<br>
<br>

