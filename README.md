# Full-Project: Students' Adaptability to Online Learning

## Overview
This project investigates students' adaptability to online learning through data wrangling, visualization, and machine learning techniques. The goal is to understand key factors influencing adaptability levels and predict these levels based on various features.

## Table of Contents
- [Data Description](#data-description)
- [Results](#results)
- [Data Wrangling](#data-wrangling)
- [Visualization](#visualization)
- [Model Implementation](#model-implementation)
- [Requirments](#requirements)
- [Usage](#usage)

## Data Description
The dataset comprises various features related to students' demographics and learning environments, as well as a target variable indicating adaptability levels. Here’s a breakdown of the features:

- **Gender**: Gender type of the student (e.g., Male, Female).
- **Age**: Age range of the student (e.g., 1-5, 6-10, 11-15, 16-20, 21-25, 26-30).
- **Education Level**: Level of education institution (e.g., School, College, University).
- **Institution Type**: Type of education institution (e.g., Government, Non-Government).
- **IT Student**: Indicates if the student is studying in an IT-related field (e.g., Yes, No).
- **Location**: Indicates whether the student is located in a town (e.g., Yes, No).
- **Load-shedding**: Level of load shedding experienced by the student (e.g., Low, High).
- **Financial Condition**: Financial condition of the student's family (e.g., Poor, Mid, Rich).
- **Internet Type**: Type of internet primarily used (e.g., Wifi, Mobile Data).
- **Network Type**: Type of network connectivity (e.g., 2G, 3G, 4G).
- **Class Duration**: Daily duration of classes (e.g., 0, 1-3, 3-6 hours).
- **Self LMS**: Availability of the institution’s own Learning Management System (e.g., Yes, No).
- **Device**: Device primarily used for classes (e.g., Mobile, Computer, Tablet).

### Target Variable
- **Adaptability Level**: Indicates the adaptability level of the students (e.g., Low, Moderate, High).

## Results
This project demonstrates the potential to predict students' online learning adaptability levels using advanced machine learning models, specifically a non-linear Support Vector Machine (SVM) and a Random Forest model. With an impressive accuracy of approximately 93% on testing data, these models provide valuable insights for educators and institutions.

The analysis reveals that the most significant factors influencing adaptability are age, class duration, gender, and education level, ranked from most to least important. Conversely, the least influential factors include device type, LMS availability, internet type, and load-shedding.

While basic models like Naive Bayes and regularized regression yielded accuracies below 70%, the exploration of more sophisticated models proved beneficial. Both the non-linear SVM and Random Forest models emerged as the most effective, outperforming simpler methods. Neural networks and other unsupervised learning techniques also demonstrated promising accuracy, indicating their potential applicability in similar contexts.

Utilizing these predictive models can help educators tailor teaching strategies and allocate resources more effectively, ensuring that learning materials align with the predicted adaptability levels of students.

## Data Wrangling

### Frequency Tables
Created frequency tables for the response variable, "Adaptivity Level," and for "Education Level" to understand the distribution of students across different categories.

### Encoding Categorical Variables
Categorical variables such as Age, Network Type, and Class Duration were encoded into numerical values for analysis.

### One-Hot Encoding
The remaining categorical variables (excluding the response variable) were one-hot encoded to prepare the data for modeling.
```
# Create dummy variables for other categorical variables

data1 = pd.get_dummies(data, columns = ['Education Level', 
                                               'Gender', 'Location', 'Institution Type', 
                                               'IT Student', 'Load-shedding', 'Financial Condition'
                                               , 'Internet Type', 'Device', 'Self Lms' ], dtype=int)
```
### Scaling Variables
Various scaling techniques (MinMaxScaler, StandardScaler, RobustScaler, Normalizer) were applied to ensure that all features contributed equally to model performance.
```
# Create a loop to apply the MinMaxScaler to all columns in df

datac= data1.copy()
for col in datac:
    scaler = MinMaxScaler()
    datac[[col]]= scaler.fit_transform(datac[[col]])
```

### Handling Missing Data
Although the dataset contains no missing values, the process of imputing missing values using the most frequent value strategy was demonstrated.

## Visualization
Utilized Python libraries to create insightful visualizations:
- **Pie Chart**: Displayed the distribution of students by adaptability levels.
- **Count Plots**: Analyzed distributions and relationships among demographic factors like age and gender.
- **Facet Grid and Pairplot**: Provided multi-dimensional views and interactions among encoded variables.
- **Bin Plots**: Illustrated relationships between age and class duration.

## Model Implementation
### Data Preparation
Categorical variables were encoded, and the dataset was split into training and testing sets.

### Model Training
Implemented various classification algorithms, including Logistic Regression, KNN, Decision Tree, and Random Forest. Each model was evaluated based on accuracy, precision, and recall.

### Hyperparameter Tuning
Applied techniques like grid search to optimize model parameters.
```
# consider 10 different values of K
search_space = [{"knn__n_neighbors": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]}]

# Create search with parameters and set 5 fold cross validation
classifier = GridSearchCV(
    pipe, search_space, cv=5, verbose=0).fit(X_train, y_train)

# Calculate best estimator
classifier.best_estimator_.get_params()["knn__n_neighbors"]
```
### Model Evaluation
Compared model performances and analyzed their robustness.

## Requirements
- Python 3.x
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

## Usage
Clone the repository and run the Jupyter Notebook or Python script to execute the analysis.

Feel free to contribute to the project or suggest improvements!
