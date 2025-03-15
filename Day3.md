# Backpropagation Main Ideas

* It optimizes the **Weights** and **Biases** in Neural Networks.
* ![alt text](image.png)
* ![alt text](image-1.png)
* ![alt text](image-2.png)
* Let's name weights ($w_1$, $w_2$, $w_3$ and $w_4$) and biases ($b_1$, $b_2$ and $b_3$).
* Backpropagation works with the last parameter and works its way backwards to estimate all of the other parameters.
* However, we can discuss main idea by estimating last parameter , bias $b_3$.
* ![alt text](image-4.png)
> Note : <span style="color: red;">Unoptimized Doses</span> and <span style="color: green;">Optimized Doses</span>
* Now if we run Dosages from 0 to 1 through the connection to the top Node in the Hidden Layer, then we get the x-axis coordinates for the Activation Function ![alt text](image-5.png) and when we plug the x-axis coordinates into the Activation Function (in this case is Softplus Activation Function i.e., ${f(x) = log(1 + e^x)}$) ![alt text](image-6.png) ![alt text](image-7.png)
* Then we multiply the y-axis coordinates on the blue curve by -1.22 ![alt text](image-8.png) and then we get the final blue curve. ![alt text](image-9.png)
* Now if we run Dosages from 0 to 1 through the connection to the bottom Node in the Hidden Layer, ... and then we get the final orange curve. ![alt text](image-10.png)
* Adding those blue and orange curves will get us a green squiggle ![alt text](image-11.png)
* Since we don't have optimal value of $b_3$, we gotta give it some initial value like $0$.
* $0$ means green squiggle doesn't move and it is far from observed values. ![alt text](image-12.png)
* It can be quantified how good it fits the data by calculating $Sum$ $of$  $Squared$ $Residuals$ $=$ $\sum_{i=1}^{n} {(Observed_i - Predicted_i)^2}$.

> Note : Changing Bias means Squiggle translates

| Bias | Sum of Squared Residuals |
|------|--------------------------|
|  0   |           20.4           |
|  1   |            7.8           |
|  2   |           1.11           |
|  3   |           0.46           |

![alt text](image-13.png)
![alt text](image-14.png)
![alt text](image-15.png)
![alt text](image-16.png)

* Now, since $Sum$ $of$ $Squared$ $Residuals$ $=$ $\sum_{i=1}^{n} {(Observed_i - Predicted_i)^2}$, and each $$Predicted$$ value comes from <span style="color: green;">$green$ $squiggle_i$</span>, which comes from last part of neural network.
* Therefore, <span style="color: green;">$green$ $squiggle_i$</span> $=$ <span style="color: blue;">$blue$</span> $+$ <span style="color: orange;">$orange$</span> $+$ $b_3$ .
* For Gradient Descent to optimize $b_3$, we need to take SSR's derivative $w.r.t$ $b_3$.
> > > # $\frac{d \, SSR}{d \, b_3}$
* Therefore by **The Chain Rule**,
* # $\frac{d \, SSR}{d \, b_3}$  $=$ $\frac{d \, SSR}{d \, Predicted}$ $\times$ $\frac{d \, Predicted}{d \, b_3}$
    1. # $\frac{d \, SSR}{d \, Predicted} = -2 \times \sum_{i=1}^{n} {(Observed_i - Predicted_i)}$
    2. # $\frac{d \, Predicted}{d \, b_3} = 1$
    3. # $\frac{d \, SSR}{d \, b_3} = -2 \times \sum_{i=1}^{n} {(Observed_i - Predicted_i)}$

> > Note : Let Learning Rate be $0.1$
 
| Bias |$\frac{d \, SSR}{d \, b_3}$|Step Size = $\frac{d \, SSR}{d \, b_3} \times \text{Learning Rate}$|$ \text{New } b_3 = \text{Old } b_3 - \text{Step Size}$|
|------|---------------------------|-------------------------------------------------------------------|-----------------------------------------------------|
|  0   |           -15.7           |                   $-15.7 \times 0.1 = -1.57$                      |                1.57                                 |
|  1.57   |           -6.26           |                   $-6.26 \times 0.1 = -0.626$                      |                2.19                                 |

Do it till Step Size close to 0.

* Most optimized $b_3 = 2.61.$