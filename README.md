# Student-Adaptability to Online Learning Research

 This project does an indepth analysis of student adaptability level of students to online classes/education.  Part one focuses on understanding the data (data wrangling).  Part two focuses data visualization, displaying the data in a useful way to share information.  Part three and four implement supervised and unsupervised learning techniques (neural networks, random forests, KNN, etc.). Part four contains conclusion for best model, and model applications.

#### Results
+ Naive bayes and guassian models were the worst (less than 70%)
+ Non linear SVM model is the best (93% Accurate)
+ Nueral networks were fairly accurate
+ Regularized with aplha as 0.001 or 0.005 was 2nd best (92.7% accuracy)
+ 2 layer neural network was worse than single layer
+ Given future feature data we could predict a students online learning adaptability level, using our non linear svm model. This model could be used to adjust the teaching style, or budget allocation of learning materials to best accomodate the predicted adaptability level of students.


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
