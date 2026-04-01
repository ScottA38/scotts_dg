A traditional scatter-plot, where a line is derived from the scatter algorithmically

Also known as OLS (Ordinary Least Squares),

Analogoousla linear regression compares **independent variables** (x-axis) to **dependent variables** (y-axis)

In an ML context, the relationship of the **x-axis** to the **y-axis** is termed as 'features' to 'label'


## Training Methodologies

### Loss

Calculating inefficiency/ loss is important to training processes. Loss can different forms, i.e:
$$
L_{1} - \text{The sum of the deltas between the actual and the predicted value}
$$
$$
\text{MAE (Mean Average Error) - the mean value of the sum of} L_{1}
$$
$$
L_{2} - \text{The sum of the square of the deltas (actual-predicted)}
$$
$$
\text{MSE (Mean Squared Error) - the average of the sum of the square of the deltas}
$$
### Gradient descent

Gradient descent is a model training technique (which help to devise model weights and biases), by continually adjusting the gradient of the model via input parameters

A typical way to do this is via Mean Squared Error (which inflicts heavier penalties to anomalies/outliers). In order to determine in which direction the gradient should go, a derivative for the bias and the weight (each individual input parameter), must be taken. If the result of the derivative is negative, the value must go up, and if it is positive, it must go down.

Gradient Descent proceeds until the rate of decrease of loss approaches 0 if it were to be plotted with attempts on the x and loss on the y. When the graph is approaching the x-axis in slope, it is known as 'convergence'