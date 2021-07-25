# Neural_Network_Charity_Analysis

## Objective
* The data analyzed for this project is from the non-profit AlphabetSoup Charity. They donate money to various groups to improve the well-being of people and planet.
* This project is to help Beks, and her manager, determine which groups will utilize the funds granted to them most efficiently. To do this, a machine learning neural network will be created.
* The analysis will provide a more scientific way of analyzing the history of their prior donations and determine which organizations should receive donations from AlphabetSoup.

## Results

#### Consistent aspects of the trials.
* IS_SUCCESSFUL is the result column that is removed from the main table. This is now the Y value or the results array.
* OneHotEncoder was used to create a dataframe of the transformed data.
* StandardScaler was used to scale/transform the X training and testing data.

### Original Output Without Optimization
* Aspects of the trial
	* Dropped EIN and NAME
	* Binned APPLICATION_TYPE, CLASSIFICATION, and ASK_AMT
	* Hidden nodes layer1 = 80 and layer2 = 30
	* Total params: 6061
	* Epochs: 100
	* Activation functions: RELU and SIGMOID 
	* The compiler optimizer was ADAMAX.

![Original Output](                 Starting_Output.png)

### Optimization Trials

#### Optimizer0.1

* Aspects of the trial
	* Dropped EIN, NAME, STATUS, and ORGANIZATION
	* Binned APPLICATION_TYPE, CLASSIFICATION, and ASK_AMT
	* Hidden nodes layer1 = 80 and layer2 = 40
	* Total params: 6481
	* Epochs: 100
	* Activation functions: TANH, RELU, and SIGMOID 
	* The compiler optimizer was ADAM.

![First Optimizer Output](                 Optimizer0.1.png)

#### Optimizer1

* Aspects of the trial
	* Automatic Hyperparameter Optimizer was used.
	* Dropped EIN, NAME
	* Binned APPLICATION_TYPE, CLASSIFICATION, and ASK_AMT
	* Epochs: 20
	* Input_dim = 43
	* Activation functions tested: TANH, RELU, SIGMOID, ELU, PReLU 
	* Dense activation function is SIGMOID.
	* The compiler optimizer was ADAM.
	* Total params: 266

![Opto1 Output1](                 Optimizer1Results1.png)
![Opto1 Output2](                 Optimizer1Results2.png)


#### Optimizer2

* Aspects of the trial
	* Automatic Hyperparameter Optimizer was used.
	* Dropped EIN, NAME, USE_CASE, SPECIAL_CONSIDERATIONS, STATUS, ORGANIZATION
	* Binned APPLICATION_TYPE, CLASSIFICATION
	* Epochs: 20
	* Input_dim = 31
	* Activation functions tested: TANH, RELU, SIGMOID, PReLU 
	* Dense activation function is SIGMOID.
	* The compiler optimizer was ADAM.
	* Total params: 298

![Opto2 Output1](                 Optimizer2Results1.png)
![Opto2 Output2](                 Optimizer2Results2.png)


#### Optimizer3

* Aspects of the trial
	* Automatic Hyperparameter Optimizer was used.
	* Dropped EIN, NAME, USE_CASE, SPECIAL_CONSIDERATIONS, STATUS, ORGANIZATION
	* No Binning
	* Epochs: 20
	* Input_dim = 116
	* Activation functions tested: TANH, RELU, SIGMOID, PReLU 
	* Dense activation function is RELU.
	* The compiler optimizer was ADAM.
	* Total params: 1197

![Opto3 Output1](                 Optimizer3Results1.png)
![Opto3 Output2](                 Optimizer3Results2.png)



## Summary
* After multiple runs of various models, the best optimizing results captured was 73% accuracy. Which is not bad; but the goal was at least 75%.
* The Automatic Optimizer utilized to determine the best model. Several different types that were not covered in the course