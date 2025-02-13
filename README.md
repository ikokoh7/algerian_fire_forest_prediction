# algerian_fire_forest_prediction
This analysis uses regression to predict the Fire Weather Index (FWI) of the Algerian Fire Forest dataset. The Machine Learning models used were Linear Regression, Lasso Regression, Ridge Regression, ElasticNet Regression and Cross validation for Lasso, Ridge and ElasticNet. The FWI ranges from 0 to 31.1 and usually below the 6.1 mark, no fire was observed.

# Features
Out of the 9 independent features excluding the date, 7 of them were selected to predict the FWI. Some of the columns were highly correlated and needed to be removed the dataset. Although the it is the job of a domain expert to set the threshold, this analysis assumed a threshold cut off to accomodate the model training.

#End-to-End Deployment
This model can be deployed to AWS ElasticBeanstalk directly from github using AWS Codepline as the CD tool and a Flask application to predict new data. 

# Folder structure
- **`.ebextension`**: Stores elasticbeanstalk configuaration
- **`datasets`**: Contains the datasets for the analysis
- **`notebooks`**: Contains the notebook for the Exploratory Data Analysis and Feature Engineering, and model training
- **`regressor_models`**: Contains both standard scaler and selected regression model in a pickle format for prediction
- **`templates`**: Contains the index.html and home.html file for the frontend of the website
- **`application.py`**: Flask application to be deployed on the Amazon ElasticBeanstalk

# Challenges
FWI as the dependent feature proved a little difficulty to predict whether a fire will occur when the prediction is between 2.7 and 6.1. In this regard, in future analyis, Logictic regression will be used to predict based on the category, _not fire and fire_. This will really improve the model's prediction.

## 🛠 How to run
1. Run the application.py
  ```bash
  python application.py
  ```
2. Copy your local address with default port as 5000 for Flask application
3. Paste the link and enter new data for each field.
4. Finally, click on predict and the prediction will be displayed

