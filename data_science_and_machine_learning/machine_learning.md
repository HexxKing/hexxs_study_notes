<h3 align="center"><a href="../table_of_contents.md">👈 Back to Table of Contents</a></h3>

---

# ✍️ Notes on Machine Learning

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



---
## 📚 Resources Used in Researching Machine Learning
- [Learn With Me: Intro to Machine Learning](https://www.youtube.com/playlist?list=PLqFaTIg4myu9-T-fat2zjC5HmTpSybNfa)