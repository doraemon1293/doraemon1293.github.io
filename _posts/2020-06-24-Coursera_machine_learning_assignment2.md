---
layout:     post
title:      Coursera_machine_learning_assignment1
subtitle:   
date:       2020-06-24
author:     Yan
header-img: 
catalog: true
tags:
    - Machine Learning
---

# Logistic Regression
*m: number of samples*
*lambda: Regularisation factor*

* Sigmoid function
![](/img/dc6b8274.png)
```
g=1./(1+exp(-z));
```

* hypothesis function
![](/img/7408d8aa.png)
```
h=sigmoid(X*theta);
```

* Cost function
![](/img/09b6148c.png)


* Regularised cost function
![](/img/9af5210c.png)
```
J=1/m*sum(-y.*log(h)-(1-y).*log(1-h))+lambda/(2*m)*sum(theta(2:size(theta)).^2);
```

* Gradient Descent
![](/img/a295cc24.png)

* Regularised gradient descent
![](/img/2a58e1e6.png)
```
grad=(X'*(h-y))/m;
grad(2:end)=grad(2:end)-lambda/m*(theta(2:end));
```

* Use fminuc to learn parameters
```
% Set options for fminunc
options = optimset('GradObj', 'on', 'MaxIter', 400);
% Run fminunc to obtain the optimal theta
% This function will return theta and the cost
[theta, cost] = fminunc(@(t)(costFunction(t, X, y)), initial_theta, options);
```

