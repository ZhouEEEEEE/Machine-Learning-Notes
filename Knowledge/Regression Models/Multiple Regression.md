Multiple linear regression (MLR), also known simply as multiple regression, is a statistical technique that uses several explanatory variables to predict the outcome of a response variable
Multiple linear regression is an extension of linear regression that uses just one explanatory variable
Multiple linear regression is used extensively in econometrics and financial inference.

## Data
`y` is the response variable and `X` is the data matrix
$$ y = \begin{vmatrix} y_1 \\ ... \\ y_n \end{vmatrix}，  X = \begin{vmatrix} x_1^T \\ ... \\ x_n^T \end{vmatrix}$$

## Model 
The formula for the linear regression model is:
$$y = Xw + \epsilon, \text{where} \  y \in \mathbb{R}^n, X \in \mathbb{R}^{n \cdot d}, \epsilon \in \mathbb{R}^n$$
where `d` is the number of features of the input, `n` is the number of datapoints. Compared to linear regression, each data point contains `d` observations instead of 1 observation.

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

## The Difference between Linear and Multiple Regression
Linear regression compares the response of a dependent variable given a change in some explanatory variables. However, a dependent variable is rarely explained by only one variable. In this case, an analyst uses multiple regression, which attempts to explain a dependent variable using more than one independent variable. Multiple regressions can be linear and nonlinear.
Multiple regressions are based on the assumption that there is a linear relationship between both the dependent and independent variables. It also assumes no major correlation between the independent variables.

## What Makes a Multiple Regression Multiple?
A multiple regression considers the effect of more than one explanatory variable on some outcome of interest. It evaluates the relative effect of these explanatory, or independent, variables on the dependent variable when holding all the other variables in the model constant.

## Why Would One Use a Multiple Regression Over a Simple OLS Regression?
A dependent variable is rarely explained by only one variable. In such cases, an analyst uses multiple regression, which attempts to explain a dependent variable using more than one independent variable. The model, however, assumes that there are no major correlations between the independent variables.

## Can I Do a Multiple Regression by Hand?
It's unlikely as multiple regression models are complex and become even more so when there are more variables included in the model or when the amount of data to analyze grows. To run a multiple regression you will likely need to use specialized statistical software or functions within programs like Excel.