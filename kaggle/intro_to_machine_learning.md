<h3 align="center"><a href="https://github.com/HexxKing/hexxs_study_notes#-1">👈 Back to Table of Contents</a></h3>

---

# ✍️ Notes from the Intro to Machine Learning Course on Kaggle

- [How Models Work](https://www.youtube.com/watch?v=qsH2ItlSqnU&list=PLqFaTIg4myu9-T-fat2zjC5HmTpSybNfa&index=2&ab_channel=Kaggle)
  - Key Points :
    - Define a model : What model would I like to use?
      - `my_model = ModelName()`
    - Fit a model : "training" a model - taking a model we have defined and applying it to our dataset and asking it start pulling out underlying patterns in the data
      - `my_model.fit(features, target)`
    - Make predictions : is what happens once we've built a model and we want to generalize it, or extend it or apply it to data it's never seen before. 
      - `my_model.predict(data)`
    - Validate our model : not covered in this lesson
  - Recap : 
    - Decision Trees are a type of model
    - The data used to fit the model is called the training data
    - Capturing patterns from data is called fitting or training the model
    - After the model has been fit, you can apply it to new data to make predictions
    - The point at the bottom where we make a prediction is called a leaf

- [Basic Data Exploration](https://www.youtube.com/watch?v=T64Pjykib9M&list=PLqFaTIg4myu9-T-fat2zjC5HmTpSybNfa&index=3&ab_channel=Kaggle)
  - Key Points : 
    - How many rows and columns in our dataframe?
      - `import pandas as pd`
      - `name = pd.read_csv(file_path)`
      - `name.shape`
        - output = (rows(int), columns(int))
    - What are the names of my variables (columns)?
      - `name.columns`
    - What do the first few rows of my dataframe contain?
      - `name.head()`
    - Are there missing values in my dataframe?
      - `name.isnull().sum()`
    - What are the summary statistics for my dataframe?
      - `name.describe()`
      - The first number, the `count`, shows how many rows have non-missing values.
  - Recap : 
    - Pandas is the primary tool we use for exploring and manipulating data, abbreviated in code as `pd`
    - DataFrames hold the type of data we think of as a table
    - We can load data using the `pd.read_csv()` function
    - We can view a summary of our data using the `describe()` function

- [Your First Machine Learning Model](https://www.youtube.com/watch?v=Lzz0oeR34XU&list=PLqFaTIg4myu9-T-fat2zjC5HmTpSybNfa&index=4&ab_channel=Kaggle)
  - Key Points : 
    - prediction target (y) = the output - the thing we are trying to use our model to predict
      - `y = name.Potato`
    - features (X) = all of the variables that we believe are contributing to our prediction
      - `name_features = ['names', 'of', 'columns']` 
      - `X = name[name_features]`
      - `X.describe()`
    - `DecisionTreeRegressor()` creates a new, untrained model
      - `name_model = DecisionTreeRegressor(random_state=1)`
      -  `name_model.fit(X,y)`
  - Recap : 
    - We can use dot notation to select the prediction target
    - The single column we select using dot notation is stored as a **Series**
    - We can select our features using a column list
    - We can view the first five rows of our data using the `head()` function

- [Model Validation](https://www.youtube.com/watch?v=ZiKrbm-haoA&list=PLqFaTIg4myu9-T-fat2zjC5HmTpSybNfa&index=5&ab_channel=Kaggle)
  - Key Points : 
    - Model validation asks the question, "Is our model any good? Does it predict what we are trying to accurately predict?"
    - Validation data is a small subset of data from the training data that is set aside to test the model on.
    - In order to create a validation set, seperate prediction target and the features into 2 additional catagories so we end up with 4 subsets. Each subset is determined randomly.
      - `train_X, val_X, train_y, val_y = train_test_split(X, y, random_state = 0)`
        - random_state = supplying a number to random_state guarantees that we get the same split every time we run this script. If you change this number from lesson to lesson, you will get different answers. 
      - prediction target training set
      - prediction target validation set
      - feature training set
      - feature validation set
    - MAE or Mean Absolute Error = in order to evaluate how well the model predicts
  - Recap : 
    - There are mnay metrics for summarizing model quality
    - We learned how to use the Mean Absolute Error, or MAE, to evaluate model quality
    - We can calculate the MAE using the `mean_absolute_error()` function from the scikit-learn.metrics module
    - We can withold data from our model and use it to test our model's accuracy -  this is referred to as validation data.

- [Underfitting and Overfitting](https://www.youtube.com/watch?v=MDiZg88mg9c&list=PLqFaTIg4myu9-T-fat2zjC5HmTpSybNfa&index=6&ab_channel=Kaggle)
  - Key Points : 
    - the goal is to find a balance between underfitting and overfitting
    - modify your model's parameters to help this
    - overfitting - the model would fit your data almost perfectly, making it challenging to generalize to another dataset. When we overfit, the model doesn't perform very well because the validation data doesn't always look like the training data. As the tree gets more complex, we see the validation error rise and what's happened is the tree has just memorized the specifics in the training set instead of actually learning the general rule.
    - underfitting - not giving it enough information will cause underfitting and any predictions we try to make will be useless
    ```
    # function for calculating the Mean Absolute Error

    def get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y):
      model = DecisionTreeRegressor(max_leaf_nodes=max_leaf_nodes, random_state=0)
      model.fit(train_X, train_y)
      preds_val = model.predict(val_X)
      mae = mean_absolute_error(val_y, preds_val)
      return(mae)
    ```
    ```
    # finding the optimal number of leaf nodes

    for max_leaf_nodes in [5, 50, 500, 5000]:
    my_mae = get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y)
    print("Max leaf nodes: %d \t\t Mean Absolute Error: %d" %(max_leaf_nodes, my_mae))
    ```
  - Recap :
    - Overfitting is where a model matches the training data almost perfectly, but does poorly with validation or other new data.
    - Underfitting occurs when a model fails to capture important distinctions and patterns in the data, so it performs poorly - even with training data
    - We can use the `max_leaf_nodes` argument to control overfitting vs underfitting

- [Random Forests](https://www.youtube.com/watch?v=EE2QmzFI5XM&list=PLqFaTIg4myu9-T-fat2zjC5HmTpSybNfa&index=7&ab_channel=Kaggle)
  - Key Points : 
    - If you want to increase the predicition accuracy of your model, we can use Random Forests. Instead of taking all of our features and combining them into one tree, Random Forests is going to use thousands of trees. It's going to randomly select features or variables it's going to pull into a given tree, and it's going to take of these trees with all of their random variable selection and it's going to average it out together in order to give us our final model and give us a higher prediction accuracy. 
    - There is often a trade off between prediction accuracy and model interpretability.
    - 
  - Recap : 

---
## 📚 Resources Used in Researching These Notes
- [Learn With Me: Intro to Machine Learning Playlist](https://www.youtube.com/playlist?list=PLqFaTIg4myu9-T-fat2zjC5HmTpSybNfa)