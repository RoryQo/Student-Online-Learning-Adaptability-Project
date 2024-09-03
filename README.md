# Student-Adaptability to Online Learning Research

 This project does an indepth analysis of student adaptability level of students to online classes/education, and aims to predict the adaptability level of the students (high, moderate, or low) given feature data for the student.  Part one focuses on encoding and preparing the data (data wrangling).  Part two focuses data visualization, displaying the data to view realtionships between the features themselves and the target.  Part three and four implements and compares supervised and unsupervised learning techniques (neural networks, random forests, KNN, etc.) to predict the adaptability level. Part four contains conclusion for best model, and model applications.

#### Results
Given future feature data we can predict a students online learning adaptability level, using our non
linear svm or Random Forest model. This model could be used to adjust the teaching style, or budget allocation of learning materials to best accomodate the predicted adaptability level of students.  According to the testing data our non linear svm model and random forest model were accurate in predictig student adaptability level approximately 93% of the time.  It appears the top four most important factors (from the random forest model) being age, class duration, gender, and education level (in order from most to least importance).  The least four import factors (least important to more important) being device type, LMS availability, internet type, load-shedding.

+ More basic models like Naive bayes,and regularized/linear regression were not sufficiently accurate (less than 70%), so we continued to fit more advanced models for improved accuracy
+ Non linear SVM model and Random forest models were the best (93% Accurate)
+ Neural networks and other unsupervised learning models were all fairly accurate (valid models)



#### Data Description
##### Features
* Gender: Gender type of student
* Age: Age range of the student
* Education Level: Education institution level
* Institution Type: Education institution type
* IT Student: Studying as IT student or not
* Location: whether student is located in town or not
* Load-shedding: Level of load shedding
* Financial Condition: Financial condition of family
* Internet Type: Internet type used mostly in device
* Network Type: Network connectivity type
* Class Duration: Daily class duration
* Self LMS: Institution’s own LMS availability
* Device: Device used mostly in class

##### Target
* Adaptability Level: Adaptability level of the students
