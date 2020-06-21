---
layout:     post
title:      Coursera_machine_learning_assignment1
subtitle:   
date:       2020-06-21
author:     Yan
header-img: 
catalog: true
tags:
    - Machine Learning
---

# Linear Regression
*m: number of samples*

*alpha: learning rate*

- Cost function: ()
![](/img/47437d1c.png)
  - where as:
  
  ![](/img/3fb63d4c.png)

- Gradient descent:
![](/img/75059e00.png)
  - In this case:
  ![](/img/b4ce8bb0.png)

- Code for Vectorisation:
  - Cost Function:
  ```J=sum((X*theta-y).^2)/(2*m);```
  - Gradient Descent:
  ```
  for iter = 1:num_iters
    h=X*theta;
    theta=theta-alpha/m*X'*(h-y);
  end
  ```
# Another solution for linear regression:
* Normal Equations
![](/img/ad76195c.png)

* Code:
```theta=pinv(X'*X)*X'*y; ```
