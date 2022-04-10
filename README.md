# Neural_Network_Charity_Analysis
 
## Overview of the analysis: Explain the purpose of this analysis.
The purpose of the analysis was to create a deep learning model that could determine whether an applicant would be successful if funded.

## Results: Using bulleted lists and images to support your answers, address the following questions.

### Data Preprocessing
What variable(s) are considered the target(s) for your model?
- The target variable was the "IS_SUCCESSFUL" column, as it determined whether the applicant was successful after being funded.
What variable(s) are considered to be the features for your model?
- The variables considered to be features were originally the APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT columns.               

What variable(s) are neither targets nor features, and should be removed from the input data?
- The variables that were initially removed were the EIN and NAME columns.

### Compiling, Training, and Evaluating the Model
How many neurons, layers, and activation functions did you select for your neural network model, and why?
- I initially used two hidden node layers and one output layer. The first hidden node had 8 units and the second had 5. The hidden layers had the "relu" activation function, and the output layer has the "sigmoid" activation. These initial choices were made simply because they are what were used in the module chapter, so it was a good starting point.
Were you able to achieve the target model performance?
- I was unable to achieve the target model performance.
What steps did you take to try and increase model performance?
- I removed the STATUS column, as only 5 out of 34299 were status 0, while the rest were status 1. About half from each binary were a part of the successful applicants, so the status did not seem to matter.
- I turned the ASK_AMT column into three unique bins, as only one ask amount appeared more than 3 times.
- For the second attempt, I added another hidden layer with 3 units. It also had the "relu" activation. This lowered the loss a bit and raised the accuracy a tiny bit.
- For the third attempt, I added another hidden layer. The layers had 8, 7, 4, and 3 units, respectively. I chose that many units because they worked relatively well compared to other amounts I tested. I also used the "sgd" optimizer instead of the "adam" one. The model had quite a bit less loss and a bit more accuracy.

## Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

Overall the results of the deep learning model were only about 18% better than a coin flip. I was unable to get the model to the target of 75% or above accuracy. An SVM model may work better if the data contains many outliers, which I believe this data set to have. Over half of the "ASK_AMT" column values were "5,000", while the max was 8.5 billion. While the scaling likely helped, I believe a model such as the Random Forests model might react better to the outliers.
