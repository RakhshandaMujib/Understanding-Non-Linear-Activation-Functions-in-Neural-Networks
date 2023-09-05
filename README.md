# Understanding Non-Linear Activation Functions in Neural Networks 

Activation functions are a crucial component of artificial neural networks. They introduce non-linearity into the models, allowing them to capture complex relationships in data. In this article, we'll explore various non-linear activation functions commonly used in neural networks, their properties, and when to use them. 

## 1. Logistic or Sigmoid Activation 
The sigmoid activation function is defined as: 

$$ \text{sigmoid}(z) = \frac{1}{1 + e^{-z}} $$ - **Range:** (0, 1) 

- **Common Use:** Often used in the last layer for binary classification, where it maps the linear activation to a probability range.


## 2. Hyperbolic Tangent (tanh) Activation 
The hyperbolic tangent activation function is defined as: 

$$ \text{tanh}(z) = \frac{e^{z} - e^{-z}}{e^{z} + e^{-z}} $$ 

- **Range:** (-1, 1)
- **Common Use:** Suitable for hidden layers, it performs better than sigmoid but still suffers from the vanishing gradient problem.


## 3. Rectified Linear Unit (ReLU) Activation 
The ReLU activation function is defined as: 

$$ \text{relu}(z) = \max(0, z) $$ 
- **Range:** [0, ∞) 
- **Common Use:** Highly popular for hidden layers due to simplicity and efficiency. However, it can suffer from the "dying ReLU" problem.


## 4. Leaky ReLU Activation 
The leaky ReLU activation function is defined as: 

$$ \text{leaky-relu}(z) = \max(Lz, z) $$ 

- **Range:** (-∞, ∞)
- **Common Use:** Helps solve the dying ReLU problem by introducing a small slope (\(L\)) (aka "leak") for negative inputs.


## 5. Parameterized ReLU (PReLU) Activation 
The parameterized ReLU activation function is similar to leaky ReLU but with the slope (\(L\)) learned during training. 

$$ \text{prelu}(z) = \max(Lz, z) $$ 

- **Range:** (-∞, ∞)


## 6. Exponential Linear Unit (ELU) Activation 
The ELU activation function is defined as: 

$$ \text{elu}(z) = \max(L(e^z - 1), z) $$ 

- **Range:** (-∞, ∞)
- **Advantage:** Smoother than ReLU for negative values.


## 7. Scaled Exponential Linear Unit (SELU) Activation 
The SELU activation function is similar to ELU but includes a scaling factor (\(S\)). 

$$ \text{selu}(z) = S \cdot \max(L(e^z - 1), z) $$ 

- **Range:** (-∞, ∞)
- **Advantage:** Addresses vanishing-exploding gradient problems, but requires specific conditions on network architecture.


## 8. Gaussian Error Linear Unit (GELU) Activation
The GELU activation function combines sigmoid and tanh functions to create a smooth non-linear activation. It is defined as:

$$ \text{GELU}(z) = 0.5z\left(1 + \tanh\left(\sqrt{\frac{2}{\pi}}(x + 0.044715z^3)\right)\right) $$

- **Range:** Approximately (-0.17, 0.17).
- **Advantage:** Suitable for deep learning models, particularly transformers like BERT and GPT-2.
- **Common Use:** Enables effective training of deep neural networks by providing smoothness and non-zero gradients.


## 9. Softmax Activation 
The softmax activation function is used in the output layer for multi-class classification: 
$$ \text{softmax}(x_{i}) = \frac{\exp(x_{i})}{\sum_{j} \exp(x_{j})} $$

- **Range:** [0, 1]
- **Common Use:** Converts raw scores (logits) into a probability distribution over multiple classes.
