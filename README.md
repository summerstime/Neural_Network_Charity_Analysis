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

#### Six Questions Answered in the "Aspects of the Trial" of each trial
	* What variable(s) are considered the target(s) for your model?
	* What variable(s) are considered to be the features for your model?
	* What variable(s) are neither targets nor features, and should be removed from the input data? 
	* How many neurons, Layers, and activation functions did you select for your neural network model, and why? 
		* Tried verious combinations, not all shown here to see improvement in the overall accuracy. 
		* Different layers chosen and different activation functions were tried individually with little change. 
		* Utilized the automatic hyperparamter optimizer in hopes that it would find a satisfactory result. Improvement seen; but not to 75%.
	* Were you able to achieve the target model performance?  No, refere to screenshots
	* What steps did you take to try and increase model performance?  Changed dropped columns, binning, activation functions

### Original Output Without Optimization

* Aspects of the Trial
	* Dropped EIN and NAME
	* Binned APPLICATION_TYPE, CLASSIFICATION, and ASK_AMT
	* Hidden nodes layer1 = 80 and layer2 = 30
	* Total params: 6061
	* Epochs: 100
	* Activation functions: RELU and SIGMOID 
	* The compiler optimizer was ADAMAX.

![Original Output](https://github.com/summerstime/Neural_Network_Charity_Analysis/blob/main/images/Starting_Output.png)


### Optimization Trials

#### Optimizer0.1

* Aspects of the Trial
	* Dropped EIN, NAME, STATUS, and ORGANIZATION
	* Binned APPLICATION_TYPE, CLASSIFICATION, and ASK_AMT
	* Hidden nodes layer1 = 80 and layer2 = 40
	* Total params: 6481
	* Epochs: 100
	* Activation functions: TANH, RELU, and SIGMOID 
	* The compiler optimizer was ADAM.

![Optimizer Output0.1](https://github.com/summerstime/Neural_Network_Charity_Analysis/blob/main/images/Optimizer0.1.png)

#### Optimizer1

* Aspects of the Trial
	* Automatic Hyperparameter Optimizer was used.
	* Dropped EIN, NAME
	* Binned APPLICATION_TYPE, CLASSIFICATION, and ASK_AMT
	* Epochs: 20
	* Input_dim = 43
	* Activation functions tested: TANH, RELU, SIGMOID, ELU, PReLU 
	* Dense activation function is SIGMOID.
	* The compiler optimizer was ADAM.
	* Total params: 266

![Optimizer1 Output1](https://github.com/summerstime/Neural_Network_Charity_Analysis/blob/main/images/Opto_Copy1_Result1.png)

![Optimizer1 Output2](https://github.com/summerstime/Neural_Network_Charity_Analysis/blob/main/images/Opto_Copy1_Result2.png)


#### Optimizer2

* Aspects of the Trial
	* Automatic Hyperparameter Optimizer was used.
	* Dropped EIN, NAME, USE_CASE, SPECIAL_CONSIDERATIONS, STATUS, ORGANIZATION
	* Binned APPLICATION_TYPE, CLASSIFICATION
	* Epochs: 20
	* Input_dim = 31
	* Activation functions tested: TANH, RELU, SIGMOID, PReLU 
	* Dense activation function is SIGMOID.
	* The compiler optimizer was ADAM.
	* Total params: 298

![Optimizer2 Output1](https://github.com/summerstime/Neural_Network_Charity_Analysis/blob/main/images/Opto_Copy2_Result1.png)

![Optimizer2 Output2](https://github.com/summerstime/Neural_Network_Charity_Analysis/blob/main/images/Opto_Copy2_Result2.png)


#### Optimizer3

* Aspects of the Trial
	* Automatic Hyperparameter Optimizer was used.
	* Dropped EIN, NAME, USE_CASE, SPECIAL_CONSIDERATIONS, STATUS, ORGANIZATION
	* No Binning
	* Epochs: 20
	* Input_dim = 116
	* Activation functions tested: TANH, RELU, SIGMOID, PReLU 
	* Dense activation function is RELU.
	* The compiler optimizer was ADAM.
	* Total params: 1197

![Optimizer3 Output1](https://github.com/summerstime/Neural_Network_Charity_Analysis/blob/main/images/Opto_Copy3_Result1.png)

![Optimizer3 Output2](https://github.com/summerstime/Neural_Network_Charity_Analysis/blob/main/images/Opto_Copy3_Result2.png)


## Summary
* After multiple runs of various models, the best optimizing results captured was 73% accuracy. Which is not bad; but the goal was at least 75%.
* The Automatic Optimizer was utilized to improve the chances of determining the best model. Results were still approximately 73%.
* More trials and testing are needed to reach 75%. 