# Coding Exercise 2: Handling Missing Data in a Dataset

1. Import the necessary Python libraries for data preprocessing, including the `SimpleImputer` class from the scikit-learn library.

2. Load the dataset into a pandas DataFrame using the `read_csv` function from the pandas library. The dataset name is `'pima-indians-diabetes.csv'`

3. Identify missing data in your dataset. Print out the number of missing entries in each column. Analyze its potential impact on machine learning model training. This step is crucial as missing data can lead to inaccurate and misleading results.

4. Implement a strategy for handling missing data, which is to replace it with the mean value, based on the nature of your dataset. Other strategies might include dropping the rows or columns with missing data, or replacing the missing data with a median or a constant value.

5. Configure an instance of the `SimpleImputer` class to replace missing values with the mean value of the column.

6. Apply the `fit` method of the `SimpleImputer` class on the numerical columns of your matrix of features.

7. Use the `transform` method of the `SimpleImputer` class to replace missing data in the specified numerical columns.

8. Update the matrix of features by assigning the result of the `transform` method to the correct columns.

9. Print your updated matrix of features to verify the success of the missing data replacement.