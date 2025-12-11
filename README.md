# Machine-Learning-Engineering-Final-Project---Caleb-Malinowski
Code submission for final project in Machine Learning Engineering.

Using Machine Learning to Predict Local Heat Transfer Coefficients
Caleb Malinowski

This project develops and evaluates a Random Forest model to predict the local heat transfer coefficient using a dataset compiled from CFD simulations.

The main objective is to use machine learning to improve prediction accuracy compared to traditional empirical correlations for two geometrical cases: cylinders in crossflow, and flow over a flat plate.

The dataset for the code is "master_data.csv" and contains all raw CFD results.

The workflow is implemented in python using scikit-learn and has the following steps:

1. Preprocessing and loading data
   - Import data from master_data.csv
   - Remove invalid or zero-valued entries
   - Split features target
   - Perform a log transform on the target

2. Feature scaling
   - Standardization using StandardScaler

3. Model training
   - Random Forest Regressor trained on 70% of the data  
   - 100 estimators

4. Model evaluation
   - Metrics:  
     - Mean Squared Error 
     - Mean Absolute Error 
     - Coefficient of Determination 
   - 10-fold cross-validation for performance robustness

5. Visualization
   - Predicted vs. Actual plots  
   - Feature importance ranking  

Additional code blocks compare code against correlations and save predictions to a new csv file.

To run the code, attach all given excel files to the folder where the code is located and run all.

The model achieved R² values of 0.98 (log scale) and 0.91 (linear scale) with K-fold cross validation scores similar to the log scale results, with a near identical R² and MSE. A feature importance analysis showed a strong dependence on pressure as a feature for the model. The results were further compared to classical correlations for both geometries and yielded percent errors of 3.99% and 0.89% against 28.10% and 47.02% from the correlations. 
