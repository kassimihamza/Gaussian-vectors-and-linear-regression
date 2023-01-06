#  Gaussian vectors and linear regression

The linear regression of random variables $Y$ knowing the value $x$ taken by a variable $X$ is given by the line with equation
$$
y = \mathbb{E}[Y] + \dfrac{\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y]}{\mathbb{E}[X^2]-(\mathbb{E}[X])^2}(x-\mathbb{E}[X])=ax+b
$$
In practice, the coefficients $a$ and $b$ are often unknow and are estimated from observations. If we observe $(x_i,y_i)_{i=1:N}$, we estimate the parameters of interest as follows:
$$
\begin{array}{l}
\mathbb{E}[X] &\rightarrow m_X = \frac 1 N\sum x_i \\
\mathbb{E}[Y] &\rightarrow m_Y = \frac 1 N\sum y_i \\
\mathbb{E}[X^2] &\rightarrow m_{XX} = \frac 1 N\sum x_i^2 \\
\mathbb{E}[XY] &\rightarrow m_{XY} = \frac 1 N\sum x_iy_i, \\
\end{array}
$$
that is, $a\rightarrow a_{est}=\frac{m_{XY}-m_Xm_Y}{m_{XX}-m_X^2}$ and $b\rightarrow b_{est}=m_Y-a_{est}m_X$.

>- 1 - Generate randomly the parameters of a line of the plane $y=\alpha x+\beta $ with $\alpha=\tan(\theta)$ and $\theta\sim U_{[0,\pi/2]}$ and $\beta\sim U_{[0,2]}$, where $U_A$ denotes the uniform distribution over the set $A$. 
>- 2- We observe data pairs $(x_i,y_i)$ so that $x_i\sim \mathcal{N}(0,5)$ and conditional to $x_i$ the distribution of $y_i$ is $\mathcal{N}(\alpha x_i+\beta,2)$, where $\mathcal{N}(\mu,\sigma^2)$ denotes the Gaussian distribution with mean $\mu$ and variance $\sigma^2$.
Generate $N=100$ relizations $(x_i,y_i)_{i=0,\ldots, N-1}$ and plot the data pairs. 
>- 3 -Implement a function **linear_regression** that returns the estimated linear regression function from a set of observed pairs $(x_i,y_i)_{i=0,\ldots, N-1}$. 
>- 4- Calculate the estimated linear regression line $y=a_{est}x+b_{est}$ and plot it. Compare it to line $y=\alpha x+\beta$ that was used to generate data. What happens when the number $N$ of observed pairs increases or decreases ?