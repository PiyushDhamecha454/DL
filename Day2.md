# Gradient **DESCENT**

* In Stats, ML and other Data Science field, We optimize a lot of stuff.

* In Linear Regression, we optimize intercept and slope.
  Eq. : $\text(y = mx + c)$
* In Logistic one, we optimize a squiggle.
  ![image](https://github.com/user-attachments/assets/81fa790a-983a-4976-8f61-695ef53caa3b)
  ![image](https://github.com/user-attachments/assets/2a615fd4-6187-49c3-a41a-c3838c0defc1)
* Gradient Descent can optimize all this stuff and much more.

* Suppose, you have 3 points in a graph for which you have to find optimized intercept and slope.
* First, You assume intercept so that you have something to improve upon. (Also, slope as least square estimate)
  ![image](https://github.com/user-attachments/assets/808dc1c7-1cf2-4fdd-8920-b26d119413f7)
* Find residual between observed and predicted and using that → Sum of Squared Residuals.
  $\sum_{i=1}^{n} (\text{observed}_i - \text{predicted}_i)$
* Then plot a graph of Intercept(X) - Sum of Squared Residuals(Y)
  ![image](https://github.com/user-attachments/assets/10171b94-da6d-4546-9e0b-46aca826a813)
![image](https://github.com/user-attachments/assets/370a9644-699d-41de-aaea-280ed5a836d7)
![image](https://github.com/user-attachments/assets/60747229-8a49-4fad-a546-97d881555721)
![image](https://github.com/user-attachments/assets/d9c7b939-6257-47bd-85be-f5724a612492)
![image](https://github.com/user-attachments/assets/9e97b800-a93e-4c6e-85fb-f753af19d237)

* ![image](https://github.com/user-attachments/assets/b514d12e-739e-4be8-910e-a674f1132a64)
![image](https://github.com/user-attachments/assets/87dfad08-3d92-4d98-bd17-8c0dd65391f3)

* For large datasets, this approach could be in-efficient.
  So there is a thing,
  * ![image](https://github.com/user-attachments/assets/3bbd5dae-ae52-4e2b-8183-feb1aefb6d09)
