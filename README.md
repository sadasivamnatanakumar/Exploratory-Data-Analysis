# Exploratory-Data-Analysis

## Summary:
One of the most important aspects of Data Analysis is Exploratory Data Analysis (EDA), an approach that involves summarizing the main characteristics of the data at hand with descriptive statistics and visualizations. This process allows for a better understanding of the data at hand, recognizing the features and the relationships between them, and potential gaps in the data.
The objective of this package is to encapsulate all the necessary functionalities for EDA into a singular, useful package. To this effect, our package conducts important steps such as Data Cleaning, Statistical Training and Testing, and the key final step of Data Visualization. This package allows users to obtain a summary of key descriptive statistics and visualizations of the dataset provided by them. We used the salient features of diverse external libraries such as pandas, numpy, matplotlib, seaborn and scipy creating a package capable of producing quality Exploratory Data Analysis. Existing libraries serving a similar function are sweetviz and pandas-profiling.

## Design:
The package consists of 4 classes, namely,
1. data: This class consists of methods data_cleanup(), drop_const() and data_engineering(). The purpose of this class is to clean, format and encode the input data file for further analysis. In specific, data_cleanup() formats the data file, calling drop_const() to remove constant and empty columns, and initializes a dataframe with the data. data_engineering() uses the 3 Sigma Rule to remove outliers.
2. stats: The methods in this class are split_train_test(), data_summary(), mean(), median() and calc_quartiles(). stats calls upon the functions of the data class when initialized, ensuring that all data passed is always formatted in a standardized manner. split_train_test() splits the cleaned and formatted dataframe into two (70/30 split) for machine learning purposes. The data_summary() method calls the mean(), median() and calc_quartiles() functions in order to provide a useful statistical summary to the end user.
3. viz: The aim of this class is to create meaningful visualizations using the outputs from the stats class, in order for the end user to have a holistic view of their data. select_options() allows the user to select features from the data in order to present histograms and 2D plots, calling the plots() method to display a variety of graphs and diagrams for the user based on the input data.
4. EDA: This class is the final one, calling the select_options() method from the viz class, allowing the user to interact with the package effectively.

## Usage:
Execute 'ProjectMain.py' which initializes the EDA class.
The user is prompted to provide three sets of inputs:
1. 2D Scatter Plot: Requires two features to plot against each other.
2. Histogram Plot: Requires one feature. This particular feature can be one of the same features selected for the 2D scatter plot.
3. Color Encoding the Plot: Requires one feature. It needs to be different from the ones used in both the plots above.

## Testing:
Execute 'test.py' which contains the unittest functions. Dataframe related functions have fail-case scenarios created for them, whereas the statistical functions have their respective equal-case scenarios. For the Visualization function, exception handling has been care of and users can use any set of combinations to test the same.
1. For example, for testing the 2-D scatter plot exception sequence, you may input 1 or 1 1 or 1 2 3 or a set with an out of bound option such as 1 8 for the test data. To continue execution, you may enter 1 2
2. For the Histogram exception sequence, you may input 1 2 or an out of bound option such as 8 for the test data. To continue execution, you may enter 3
3. For the Encoding label exception sequence, you may input an option that has already been used to continue the execution above or an out of bound option such as 8 To continue execution, you may enter 5

## Requirements:
This package requires Python 3.10 or greater to run and uses the following external packages for its implementation:
1. Pandas
2. Scipy
3. Numpy
4. Matplotlib
5. Seaborn

## Creators:
1. Sadasivam Natanakumar
2. Prerna Chander
3. Saurav Krishna
