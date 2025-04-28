# Course Summary: Foundations of Neural Networks and Mathematical Preliminaries

## 1. Neural Network Fundamentals

### 1.1 Simulating a Neuron’s Activity
- Model a neuron as weighted inputs plus bias passed through an activation function.

### 1.2 Activation Condition
- A neuron activates when the weighted sum exceeds a threshold.

### 1.3 Bias
- Bias shifts the activation threshold.
- Provides flexibility in model fitting.

### 1.4 Activation Function
- Introduces non-linearity.
- Common activation functions:
  - Linear Function: $f(x) = ax + b$
  - Quadratic Function: $f(x) = ax^2 + bx + c$
  - Unit Step Function: Threshold-based
  - Exponential Function: $f(x) = e^x$
  - Sigmoid Function: $f(x) = \frac{1}{1 + e^{-x}}$

### 1.5 Hidden Layer: Feature Extraction
- Layers between input and output.
- Automatically extract features from raw data.

### 1.6 Role of Weights and Biases
- Weights control the strength of the input features.
- Biases allow shifting the activation thresholds.

### 1.7 Determining Weights and Biases
- Learned through optimization (minimizing loss functions).

---

## 2. Mathematical Preliminaries

### 2.1 Functions
- Linear Function
- Quadratic Function
- Unit Step Function
- Exponential Function
- Sigmoid Function
- Differentiation (concept and rules)
- PDF of Normal Distribution

### 2.2 Sequence and Recurrence Relation
- Definition of Sequence
- Definition of Recurrence Relation
- Sigma Notation (summation)

### 2.3 Vectors, Matrices, and Differentiation
- Vector
- Inner Product
- Cauchy-Schwarz Inequality
- Formal Definition of Vector Space
- Application of Inner Product to Neural Networks
- Maxima and Minima (extrema points)
- Partial Derivative
- Multivariable Function Minima
- Chain Rule for Multivariable Functions
- Matrix Concepts:
  - Equality
  - Addition
  - Multiplication
  - Hadamard Product
  - Transpose of a Matrix
  - Operations in Vector Spaces
- Differentiation:
  - Derivative of $f(x)$
  - Properties of Derivatives

---

## 3. Linear Approximation and Gradient Descent

### 3.1 Multivariable Functions
- Tangent Plane Approximation

### 3.2 Gradient Descent

#### Gradient Descent Algorithm
- Iteratively update parameters to minimize a loss function $J(\theta)$.
- Basic update rule:
  - $$
  \theta := \theta - \eta \nabla_{\theta} J(\theta)
  $$
- Where:
  - $\theta$ is the parameter vector,
  - $\eta$ is the learning rate,
  - $\nabla_{\theta} J(\theta)$ is the gradient of the loss with respect to $\theta$.

#### Finding the Steepest Descent Direction
- The direction of the steepest descent is the negative gradient.
- Formula:
  - $$
  \text{Steepest descent direction} = -\nabla_{\theta} J(\theta)
  $$

#### Small Step Update Rule
- Update for a small movement $\Delta x$ in the direction of the negative gradient.
- Formula:
  - $$
  \Delta x = -\eta \nabla_x z
  $$
- Interpretation:
  - Take a small step proportional to the negative of the gradient to decrease the value of $z$.

#### Application to Neural Networks
- Neural network training applies gradient descent by:
  - Computing the gradient of the **loss function** with respect to all **weights and biases**.
  - Updating weights and biases according to:
    - $$
    w := w - \eta \frac{\partial J}{\partial w}
    $$
    - $$
    b := b - \eta \frac{\partial J}{\partial b}
    $$
- This process is repeated over many iterations (epochs) to minimize the overall loss.

---

## 4. Stochastic Methods (SGD)

### 4.1 Mini-Batch vs Batch
- Batch: Full dataset used for each update.
- Mini-Batch: Small subsets used for each update.

### 4.2 Optimization Algorithms Using Stochastic Approaches

#### Momentum
- Accelerates SGD by adding a fraction of the previous update to the current one.
- Formula:
  - $$
  v_t = \gamma v_{t-1} + \eta \nabla_{\theta} J(\theta)
  $$
  - $$
  \theta = \theta - v_t
  $$
- Where $\gamma$ is the momentum coefficient.

#### Nesterov Accelerated Gradient (NAG)
- Improves momentum by looking ahead before computing the gradient.
- Formula:
  - $$
  v_t = \gamma v_{t-1} + \eta \nabla_{\theta} J(\theta - \gamma v_{t-1})
  $$
  - $$
  \theta = \theta - v_t
  $$

#### Learning Rate Concept
- Controls the step size at each iteration.
- Update rule:
  - $$
  \theta = \theta - \eta \nabla_{\theta} J(\theta)
  $$
- Where $\eta$ is the learning rate.

#### Adagrad
- Adapts the learning rate individually for each parameter.
- Formula:
  - $$
  r_t = r_{t-1} + (\nabla_{\theta} J(\theta))^2
  $$
  - $$
  \theta = \theta - \frac{\eta}{\sqrt{r_t} + \epsilon} \nabla_{\theta} J(\theta)
  $$
- Where $r_t$ accumulates the squared gradients.

#### RMSprop
- Modifies Adagrad by using a moving average of squared gradients.
- Formula:
  - $$
  r_t = \rho r_{t-1} + (1-\rho)(\nabla_{\theta} J(\theta))^2
  $$
  - $$
  \theta = \theta - \frac{\eta}{\sqrt{r_t} + \epsilon} \nabla_{\theta} J(\theta)
  $$
- Where $\rho$ is the decay rate.

#### Adam (Adaptive Moment Estimation)
- Combines Momentum and RMSprop.
- Formula:
  - $$
  m_t = \beta_1 m_{t-1} + (1-\beta_1) \nabla_{\theta} J(\theta)
  $$
  - $$
  v_t = \beta_2 v_{t-1} + (1-\beta_2)(\nabla_{\theta} J(\theta))^2
  $$
- Bias-corrected estimates:
  - $$
  \hat{m}_t = \frac{m_t}{1-\beta_1^t}, \quad \hat{v}_t = \frac{v_t}{1-\beta_2^t}
  $$
- Update rule:
  - $$
  \theta = \theta - \frac{\eta}{\sqrt{\hat{v}_t} + \epsilon} \hat{m}_t
  $$

---
