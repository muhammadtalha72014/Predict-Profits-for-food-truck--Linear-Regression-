# Predict-Profits-for-food-truck
## Introduction

In this exercise, I implemented linear regression and get to see it work on data. Before starting on this programming exercise, I strongly recommend clearing concepts of linear regression, gradient descent and feature normalization. To get started with the exercise, I will need to download the starter code and unzip its contents to the folder. Files incuded are:

 - part1.ipynb: Google Colab Notebook (gradient descent) script that steps you through the exercise
 - part2.ipynb: Google Colab Notebook (Optimization Function) script that steps you through the exercise
 - Data.txt: Dataset Text file for linear regression with one variable and multi-variable

# Part 1: Linear Regression In One variable-

## Task1: Simple Python Function

The first task in part1.ipynb gives you practice with function syntax. In the the warmUpExercise, I find a predefined function in given space to return a 5x5 or any other value identity matrix I should see output similar to the following:

```
print("Matrix a : \n", iden(5))
```

![Screenshot 2024-07-02 114033](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/94e026fc-ea5b-4a61-adef-1c5a8149dc21)

## Task2: Plotting Data

In this part of this exercise, I implemented linear regression with one variable to predict profits for a food truck. Suppose you are the CEO of a restaurant franchise and are considering different cities for opening a new outlet. The chain already has trucks in various cities, you have data for profits and populations from the cities. You would like to use this data to help you select which city to expand to next. The file Data.txt contains the dataset for our linear regression problem. The first column is the population of a city and the second column is the profit of a food truck in that city. A negative value for profit indicates a loss.

Before starting on any task, it is often useful to understand the data by visualizing it. For this dataset, I used a scatter plot to visualize the data, since it has only two properties to plot (profit and population). 

 In part1.ipynb, the dataset is loaded from the Data.txt into the variables X and Y:

```
# Read comma separated data
data = np.loadtxt(os.path.join('Data', path ), delimiter=',')
X, Y = data[:, 0], data[:, 1]
```

Now, when I run the plotdata, our end result should look like 

![download](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/29f15708-6c10-4f9e-bf42-b67d80ee0cb6)

## Task3: Computing Cost

 As I perform gradient descent to learn minimize the cost function J, it is helpful to monitor the convergence by computing the cost. My next task is to complete the code in the computeCost function, which is a function that computes J. As you are doing this, remember that the variables X and y are not scalar values, but matrices whose rows represent the examples from the training set. Once I completed this task, I got a cost of 32.07.

 ![Screenshot 2024-07-02 131436](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/534b9d7a-bac1-409a-b0f9-ecbd43e06c76)

## Task4: Gradient Descent

Next, I completed a function which implements gradient descent. A good way to verify that gradient descent is working correctly is to look at the value of J and check that it is decreasing with each step. 

 ![Screenshot 2024-07-02 131854](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/6af22c71-908a-4c3e-bf92-8c8eb7b56910)

To understand the cost function J better, I plotted the cost over a 2-dimensional grid of theta(0) and theta(1) values. The cost values are used to produce surface and contour plots of J using the matplotlib plot surface and contour functions. The plots should look something like

![Screenshot 2024-07-02 132325](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/b95c5c20-4281-43c9-bc8b-e402ad00e843)

## Task5: Feature Normalization
Sometime in the data set, we have features with mighty difference in magnitudes for example house sizes are about 1000 times the number of bedrooms. When features differ by orders of magnitude, first performing feature scaling can make gradient descent converge much more quickly. In featureNormalize function:

- Subtract the mean value of each feature from the dataset.
- After subtracting the mean, additionally scale (divide) the feature values by their respective standard deviations.

I also get to try out different learning rates for the dataset and find a learning rate that converges quickly as shown below.

![Screenshot 2024-07-02 133228](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/5c559166-a4d6-4444-8c20-92020faca8ac)


# Part 2: Optimization Functions
## Task1
I used the fmin and fmincg function of SciPy in part2.ipynb. DATA initialization will be same as above. 

![Screenshot 2024-07-02 134108](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/ea9e0332-5a1e-4b35-b4f4-63e63316d52b)

## Task2: Learning Rate

Since these function do not require alpha, single learning will be plotted 

![Screenshot 2024-07-02 134302](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/3e4a35e8-bac0-44f0-99cf-98230d3d5ccc)

## Task3: Fitting Second Order Polynomial

Now, I fit the 2nd order polynomial through the data. Previously, I implemented cost function computeCost and gradientDescent on a uni-variate regression problem. The only difference now is that there is one more feature in the matrix X. The batch gradient descent update rule remain unchanged.Now matrix X has n number of features.

![Screenshot 2024-07-02 134550](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/0accea2a-c9b7-4660-9c08-4584c0ad4e6c)

## Task4: Fitting Third Order Polynomial

![Screenshot 2024-07-02 134728](https://github.com/muhammadtalha72014/Predict-Profits-for-food-truck-Linear-Regression-/assets/173653061/9279fdee-1cc2-4e27-88c6-5befe7a3a57d)
