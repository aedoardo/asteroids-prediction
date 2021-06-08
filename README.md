# Potentially Hazardous Asteroids Classification and Diameter prediction

This is the repository for the project of <a href="https://github.com/gtolomei/big-data-computing">Big Data course</a> at La Sapienza.

The project consists of two tasks: the first one is a <i>binary classification</i> to decide if an asteroid is potentially hazardous or not while the second one is a <i>regression problem</i> that tries to predict the asteroids' diameter.
For the classification problem, I used two different datasets: the first one contains all the asteroids while the second contains only the asteroids that are <i>Near Earth Objects</i>.

## Dataset
The dataset that I used is available on Kaggle at this <a href="https://www.kaggle.com/sakhawat18/asteroid-dataset">link</a>. You can also query the dataset on the <a href="https://ssd.jpl.nasa.gov/sbdb_query.cgi">JPL Website</a>.

## Potentially Hazardous Asteroids Classification
For this task I used three different models: 
<ul>
  <li>the logistic regression;</li>
  <li>the decision tree;</li>
  <li>the random forest.</li>
</ul>

### Results
I report only the best result for each model. However, you can find all the results in <a href="https://github.com/aedoardo/asteroids-prediction/tree/main/results/classification">this folder</a>.

#### Dataset with all asteroids
| Model | Best model name | Accuracy | Precision | Recall | F1-Score |
|-------|-----------------|----------|-----------|--------|----------|
| Logistic Regression | logistic_regression_no_std_all | 0.99 | 0.70 | 0.58 | 0.64 |
| Decision Tree | decision_tree_oversampled_no_std_all | 0.99 | 0.61 | 0.99 | 0.75 |
| Random forest | random_forest_oversampled_no_std_all | 0.97 | 0.54 | 0.98 | 0.70 |

#### Dataset with only Near Earth Objects
| Model | Best model name | Accuracy | Precision | Recall | F1-Score |
|-------|-----------------|----------|-----------|--------|----------|
| Logistic Regression | logistic_regression_std_nea_nea | 0.95 | 0.85 | 0.86 | 0.86 |
| Decision Tree | dec_tree_no_std_nea_nea | 0.99 | 0.98 | 0.98 | 0.98 |
| Random forest | random_forest_oversampled_std_nea_nea | 0.91 | 0.74 | 0.90 | 0.81 |


## Diameter prediction
Also in this case I used three different approaches:
<ul>
  <li>the linear regression;</li>
  <li>the random forest regressor;</li>
  <li>the gradient-boosted tree.</li>
</ul>

In this case, I've created a dataset with all the asteroids that have the diameter field not null. 

| Model | Training RMSE | Training R2 | Training R2 Adj. | Test RMSE | Test R2 | Test R2 Adj. |
|-------|-----------------|----------|-----------|--------|----------|----------|
| Linear Regression | 5.832 | 0.614 | 0.613 | 6.589 | 0.559 | 0.556 |
| Random Forest regressor | 3.329 | 0.874 | 0.874 | 6.303 | 0.597 | 0.593 |
| Gradient boosted tree | 3.198 | 0.884 | 0.884 | 7.006 | 0.502 | 0.497 |

## Environment
All the tasks were implemented with <a href="https://spark.apache.org/docs/latest/api/python/">PySpark</a> on <a href="https://databricks.com">DataBricks</a> (I used the community
plan).
