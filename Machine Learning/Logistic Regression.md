Logistic regression refers to the statistical modelling of categorical outcomes. Outcomes are defined based upon the dependent variables within the model.

Logicstic Regression concerns itself with determining probabilities, rather than direct values

Categorical outcomes could be:

1) Binary outcomes => `yes/no`, `true/false`
2) Multinomial => _i.e:_ types of degree subject: `[ 'Art & Design', 'Psychology', 'Mechanical Engineering' ]`
3) Ordinal => Categories which imply a continuous sequence, such as: `[ 'slow', 'average', 'fast' ]` or `[ 'cold', 'lukewarm', 'hot', 'boiling' ]`

## Algorithms involved

A logistic regression depends upon a function called a [sigmoid function](https://developers.google.com/machine-learning/crash-course/logistic-regression/sigmoid-function#sigmoid_function), which can be written like this:
![[Sigmoid-derivation.png]]

Breakdown:
- `e` is euler's number (a constant) = 2.71828 (approx.)
-  `x` is the input (position on the x-axis)
- `f(x)` is the output (position on the y-axis)

This function has the following characteristics:
- The result of the calculation will always be a number within the range of  `0 <= z <= 1`
- The resultant curve will be 'S' shaped, which is where the 'Sigmoid' function gets it's name from
- 
