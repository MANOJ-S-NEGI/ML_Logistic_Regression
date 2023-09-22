# ML_Logistic_Regression
---
---

## To understand the workings of the Logistic Regression we need to start with hypothetical data.
```
study_hours = 1, 2, 3, 4, 5, 6, 7, 8, 9

result [pass_fail] = fail, fail, fail, fail, fail, pass, pass, pass, fail

```
**Graph represents data point without any outlier**

![download (1)](https://github.com/MANOJ-S-NEGI/ML_Logistic_Regression/assets/99602627/1f8c317a-7a9c-4792-a036-cab77eeec028)



in the above-mentioned dataset, we can see that the result depended on the number of hours but due to the outlier "study_hour = 9" getting "failed" here lies the problem the clear separation of the data is not possible in this scenario. 

even if tries to do so algorithm will consider another data point as a failure and will shift the best-fit line to construct the separation which leads to a mismatch in the prediction and actual data. This is when logistic Regression comes into the picture.

To prevent it we need to flatten the slope (slice the slope) through the sigmoid activation function to the mean_square_error (mse)

**Graph represents Data point with outlier and sigmoid**


![download](https://github.com/MANOJ-S-NEGI/ML_Logistic_Regression/assets/99602627/e2f67f49-c7cd-4a29-a79e-ad0d4daf30e8)


## sigmoid function
- The sigmoid function, also known as the logistic function, is a mathematical function that maps any real-valued number to a value between 0 and 1.

Mathematically, the sigmoid function is defined as:  1 / (1+e<sup>(-x))

 - sigmoid function always ranges between 0 and 1 and its derivative ranges between 0 - 0.25.

 - The sigmoid function is used in logistic regression to model the probability of a binary event occurring. It transforms a linear combination of features into a probability value.

- Probabilistic Interpretation: The output of the sigmoid function can be interpreted as the probability of an event happening. For example, in logistic regression, if f(x) > 0.5, it suggests that the model predicts a higher likelihood of the positive class.



Let's see how see it mathematically:

mse , J(θ<sub>0</sub>θ<sub>1</sub>) = <sup>n</sup>∑<sub>i=1</sub> (h<sub>0</sub>(x<sub>i</sub>) - y<sub>i</sub>)<sup>2</sup> / n 

represents the cost function for a linear regression model, 

   |Where:|
   |:-|
   |J(θ<sub>0</sub>θ<sub>1</sub>) is the cost function|
   |θ<sub>0</sub>θ<sub>1</sub> are the parameters (intercept and slope) of the linear regression model|
   |n is the number of data points|
   |h<sub>0</sub>(x<sub>i</sub>) is the predicted value for the i-th data point|
   |y<sub>i</sub> is the actual target value for the i-th data point|

h<sub>0</sub>(x<sub>i</sub>) = θ<sub>0</sub> + θ<sub>1</sub>x

applying sigmoid (σ) 

1 / (1+e<sup>-(θ<sub>0</sub> + θ<sub>1</sub>x))  
- if  ≤ 0.5 then the output will be "Fail"
- if  > 0.5 then the output will be "Pass"
 
in a similar way the logistic regression works.
The issue that arises by applying the cost function is that it will lead to the local minima problem which will impact the preferred result.
