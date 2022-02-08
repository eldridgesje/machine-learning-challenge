# machine-learning-challenge
Repo for the Northwestern Data Science Bootcamp machine learning homework

# Model analysis

## Model 1

Model 1 employs a logistic regression classifier to make a prediction about the status of an object.

The process for designing this model was as follows:

1. Clean the data with dropna.
2. Select features:
    * The initial features I selected were the 19 columns in the CSV that were not the koi_disposition or any of the error columns for the main columns.
3. Split taining and testing sets
4. Scale the data
5. Establish the model
6. Train the model
7. Test the model:
    * The initial accuracy of the model was ~82.8%, below the target of 85%.
8. Estimate the importance of each feature.
9. Revise the model with the least-relevant features removed.
10. Repeat steps 3-7:
    * The accuracy of the new model was ~83.5%, still below the target of 85%.
11. Tune hyperparameters on the new model using GridSearch:
    * Test different C values and different solvers.
12. Find the best parameters.
13. Revise the model with the best parameters:
    * Final accuracy of this model was ~83.5%, little different than default parameters.
14. Model saved ("stephen_eldridge_1.sav") in case Model 2 fails to perform better.

## Model 2

Model 2 employs a deep learning classifier to make a prediction about the status of an object.

The process for designing this model was as follows:

1. Clean the data with dropna.
2. Select features:
    * Feature selection is more difficult with deep learning, as it's harder to determine which features are relevant to the final product. After some experimentation, I found the best results by including all the initial features.
3. Split taining and testing sets
4. Scale the data
5. Establish the model
6. Train the model
7. Test the model:
    * The initial accuracy of the model was ~88.8%, above the target of 85%.
11. Tune hyperparameters on the new model using GridSearch:
    * Test different optimizers and epoch values.
12. Find the best parameters.
13. Revise the model with the best parameters:
    * Final accuracy of this model was ~89.2%, and also saw improvements in Loss value.
14. Model saved using the Keras.save method, because joblib doesn't work well with Keras. Instructions for loading the saved folder ("stephen_eldridge_model") were included in the code.

## Winning Model: Model 2 (deep learning)

## Model comparison

Both models provided fairly high accuracy -- ~83.5% compared to ~89.2% -- but the deep learning model did perform above the benchmark of 85%, while the logistic regression did not.

The chosen model is accurate enough to identify objects for further study -- the great majority of exoplanet candidates classified should turn out to be genuine exoplanets. However, the level of accuracy could certainly improve. Possible improvements include:

* A larger training set
* Further testing to identify exactly which features are most relevant in deep learning
* Exploration of additional hyperparameters with more computing power turned to more iterative analysis