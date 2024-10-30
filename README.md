# neural-network-challenge-2
# Module 19 Challenge, create neural network to:
  - predict whether employees are likely to leave the company and
  - predict if some employees may be better suited to other departments

# Assignment was divided into 3 sections:
1. Preprocessing:
- Investigated the attrition_df dataFrame using shape, info()
- Checked to see what (object) features need to be encoded; and which objects were multi class vs. binary classification to determine the right encoder and which activation functions to use.
- Checked for null values and unique values by feature
- Net is that data was pretty clean; most features did not need to be encoded as they were of type int64.  And no null values.
- I checked the unique counts for Attrition and found the data to be imbalanced, which could impact results.
- Created y_df with Attrition and Department features.
- Created X_df with 10 features I chose.  All were int64 so I did not need to convert to numeric data type.  And values were close in range so I did not scale.
- Next was to split the data in to training and testiong sets
- - Used OneHotEncoder to encode Attrition and Department
- Used StandardScaler for my X data

2.  Create, Compile, and Train the Model:
- Created input layer, hidden layer and two shared layers for X_train_scaled
- Created Branches for Attrition and Department with hidden layer and output layer
- Created and compiled the model, summarized as follows.


  <img width="560" alt="image" src="https://github.com/user-attachments/assets/e561be2b-e515-4e5b-8dcf-9c8e6ea95b38">


- Next was to fit the model, using 100 epochs, 32 batch_size, and .2 validation_split
- Evaluated the moded with test data
- Printed the accuracy for both department and attrition:
  
    Test Loss: 323.200439453125
    Department Output Accuracy: 0.8695651888847351
    Attrition Output Accuracy: 0.7010869383811951

- While the accuracy results are reasonably good, the results are suspsect given how imbalanced the model was.  More needs to be done to improve performance.

3.  Summary:
   1. Is accuracy the best metric to use on this data? Why or why not?
      Answer: No. Accuracy is not the best metric for this data set. Because the data is imbalanced the accuracy results could be misleading. And good at predicting the data set, but not future predictions. For attrition, 83%+ of the data in the set is 'no.'

  2. What activation functions did you choose for your output layers, and why?
     Answer: I used sigmoid for attrition because the responses are binary. I used softmax for department because it had multiple classes.

  3. Can you name a few ways that this model might be improved?
     Answer: Hyperparameter tuning can help balance the data and lead to better performance. Data augmentation could also help by improving generalization. And feature engineering can help isolate the most relevant features.

___
Assignment copmpleted by Louis Canjar with assistance from Xpert Learning Assistant.
