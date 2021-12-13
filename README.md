# Module 19 Challenge - Charity Analysis - Neural Network

## Overview

The purpose of this analysis is to create a Binary Classifier
that is capable of predicting whether applicants will be successful
if funded by Alphabet Soup.

## Deliverables

### Deliverable 1

Preprocessing Data for a Neural Network Model- `AlphabetSoupCharity.ipynb`

### Deliverable 2

Compile, Train, and Evaluate the Model- `AlphabetSoupCharity.ipynb` and `AlphabetSoupCharity.h5`

### Deliverable 3

Optimize the Model - `AlphabetSoupCharity_Optimization.ipynb` and `AlphabetSoupCharity_Optimization.h5`

### Deliverable 4

A Written Report on the Neural Network Model - This 'README.md'


## Results

### Data Preprocessing

- What variable(s) are considered the target(s) for your model?
	- The target for this model is the `IS_SUCCESSFUL` column. The qualification metric is unknown, but this Boolean
	metric shows whether the Funding was used Effectively or Not.
- What variable(s) are considered to be the features for your model?
	- The features originally to complete Deliverable 2 is `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`,
	 `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, and `ASK_AMT`
	- During Model Optimization in Deliverable 3, `NAME` was added as a feature.
- What variable(s) are neither targets nor features, and should be removed from the input data?
	- Originally to complete Deliverables 1-2, `EIN` and `NAME` were dropped.
	- During Model Optimization in Deliverable 3, `NAME` was re-incorporated as a feature.

### Compiling, Training, and Evaluating the Model

- How many neurons, layers, and activation functions did you select for your neural network model, and why?
	- Originally, to complete Deliverable 2, two hidden layers were added. The first with 90 neurons, and the second with 45 neurons.
	The original number of inputs was 43, so 90 neurons were chosen as approximately 2x+ the number of inputs. For the second hidden layer,
	the number of neurons was the number of neurons for the first hidden layer divided by two.
	- To complete Deliverable 3, a third hidden layer was added with 10 nodes, and the number of nodes for the first hidden layer
	was increased to 100 to improve mode performance. The number of neurons for the third hidden layer is approximately the number of neurons
	for the second hidden layer divided by 2^2 (4).
- Were you able to achieve the target model performance?
	- In Deliverable 2, the model performance achieved was 72.6%, which was below the target of 75%.
	- In Deliverable 3, optimizations were applied, and model performance was increased to 78.9%, above the target of 75%.
- What steps did you take to try and increase model performance?
	1. Increased the number of nodes in Hidden Layer 1 to 100
	2. Added a third hidden layer with 10 nodes
	3. Changed the activation function for Hidden Layers 2 and 3 to "sigmoid"
	4. Reincorporated `NAME` as a feature input for the model. To reduce the number of inputs, only 'NAMES' appearing 5 or more times were considered. Names appearing less than 5 times were categorized as 'Other'.


## Summary

Prior to optimization, the model correctly predicted good use of funds roughly 70% of the time. Following optimization, model accuracy was boosted to nearly 80%.

A different model that could be used to solve this classification problem is a Random Forest, which are good in cases of classification.


-- END --
