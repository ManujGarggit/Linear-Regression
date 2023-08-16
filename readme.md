# MDL

# Assignment 2

> Name - Manuj Garg

### DEFINITIONS

- Bias refers to error due to incorrect assumptions in learning algorithm
- Variance measures error due to small fluctations in training set
- Irreducible error represents the inherent noise or variability in the data that is not intended to be present in the first place but was introduced due to a faulty capturing process.

### IMPLEMENTATIONS

- Calculated the values of bias , variance , mean squared error and irreducible error for the given training data and test data sets upto degree 15 polynomials.
- To calculate these values the training set is divided into 20 random pieces and for each point the parameters are calculated by taking the avg of the results obtained in each piece (k-fold validation).
- Graph bw bias,variance and mse is also plotted to signify the trend if bias and variance and how they change with degree.

### WALKTHROUGH

- First the test and training data is loaded using `pickle.load()` function and this data is separated into X and Y components.
- Then the training data is divided into 20 random parts using `numpy.split(numpy.random.permutation(data_name),20)`.
- Then for each part the model is fitted using `LinearRegression.fit()` and the predicted values from the test data set is calculated.
- Then we can calculate the parameters for each 20 part to get the parameters value for a single point.
- These values are then averaged over all points to get bias,variance,mse and error for the whole degree.
- These values will be differnet if we execute the code once again due to splitting of train data into random parts.
- Then values are tabulated and the graph is plotted

### OBSERVATIONS

- We can see that as the degree of the polynomial is increasing the bias is decreasing steadily while the variance is increasing.
- This is happening as our model is memorizing the training set values too well that gives us a low bias but it performs bad on general points (our model is becoming a overfit model).
- The underfit models has high bias and low variance while the overfit models have low bias and high variance (this can be seen from the graph where the degree ~5 is the optimal degree where the plots of bias and variance intersect)
  
![GRAPH](https://github.com/ManujGarggit/Linear-Regression/blob/master/img.png)
