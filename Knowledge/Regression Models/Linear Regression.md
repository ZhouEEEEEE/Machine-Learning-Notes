This is the simplest form of regression, where the relationship between the independent and dependent variables is assumed to be linear. The goal is to find the best-fitting line (or hyperplane in higher dimensions) that minimizes the difference between predicted and actual values.

# Formula
## Data
`y` is the response variable and `X` is the data matrix
$$ y = \begin{vmatrix} y_1 \\ ... \\ y_n \end{vmatrix}，  X = \begin{vmatrix} x_1^T \\ ... \\ x_n^T \end{vmatrix}$$

## Model 
The formula for the linear regression model is:
$$y = Xw + \epsilon, \text{where} \  y \in \mathbb{R}^n, X \in \mathbb{R}^{n \cdot d}, \epsilon \in \mathbb{R}^n$$
where `d` is the number of features of the input, `n` is the number of datapoints

## Loss Function
The loss function:
$$ L(w) = \frac{1}{n} \sum_{i=1}^{n} (y_i - X_i w)^2 $$
The matrix format is:
$$L(w) = (y - Xw)^T(y - Xw)$$
## Optimization
The optimization procedure is to using [[gradient descent]] to set derivative to zero to obtain the parameters `w`. The derivation of closed form `w` obtained from gradient descent is:
$$w = \underset{w \in \mathbb{R}^d}{\text{argmin}} L(w)$$
$$w = \underset{w \in \mathbb{R}^d}{\text{argmin}} (y - Xw)^T(y - Xw)$$
Derivation:
$$\begin{align*} 
\nabla_w L(w) &= -2X^T(y - Xw)\\
&= -2X^Ty + 2X^TXw \\
&= 0\end{align*}$$
Thus, the closed form solution is:
$$\begin{align*} 
\nabla_w L(w) &= 0\\
-2X^Ty + 2X^TXw &= 0 \\
w &= (X^TX)^{-1}X^Ty\end{align*}$$

## Advantages & Disadvantages:
- Advantages:
	- Explainable method
	- Interpretable results by its output coefficient
	- Faster to train than other machine learning models
- Disadvantages:
	- Assumes linearity between inputs and output
	- Sensitive to outliers
	- Can underfit with small, high-dimensional data
