Project Overview
This project aims to predict the final year grades (G3) of students based on various socio-economic, personal, and academic factors using machine learning models. The dataset used for this analysis includes student performance data in both Math and Portuguese courses.

Data Sources
The datasets used in this project are sourced from:

student-mat.csv: Student performance in Math
student-por.csv: Student performance in Portuguese
These datasets were originally used in the study by Cortez and Silva (2008) and contain various features related to student demographics, social and economic context, and academic performance.

Exploratory Data Analysis (EDA)
The EDA was performed to understand the distribution of data, handle missing values, and visualize relationships between features. Key insights include:

Strong correlation between G1, G2, and G3 grades.
The impact of absences, failures, and socio-economic factors on final grades.
Visualizations to understand distributions and relationships between different features.
Data Preprocessing
The data preprocessing steps include:

Handling categorical variables using OneHotEncoder.
Scaling numerical features using StandardScaler.
Splitting the dataset into training and testing sets.
Models
The following models were built and evaluated:

Linear Regression
Decision Tree Regressor
Random Forest Regressor
XGBoost Regressor
Model Performance
Initial Model (Including G1 and G2)
Math Results:

Model	RMSE	R2 (Train)	Adj. R2 (Train)	R2 (Test)	Adj. R2 (Test)	5-Fold CV Mean R2
Linear Regression	2.38	0.87	0.85	0.72	0.42	0.79
Decision Tree	2.37	1.00	0.99	0.73	0.42	0.81
Random Forest	2.13	0.97	0.97	0.78	0.54	0.78
XGBoost	1.95	0.97	0.97	0.81	0.61	0.87
Portuguese Results:

Model	RMSE	R2 (Train)	Adj. R2 (Train)	R2 (Test)	Adj. R2 (Test)	5-Fold CV Mean R2
Linear Regression	1.21	0.86	0.85	0.85	0.78	0.84
Decision Tree	1.48	0.89	0.88	0.78	0.67	0.77
Random Forest	1.44	0.97	0.97	0.79	0.69	0.78
XGBoost	1.23	0.93	0.92	0.84	0.77	0.85
Model (Excluding G1 and G2)
Math Results:

Model	RMSE	R2 (Train)	Adj. R2 (Train)	R2 (Test)	Adj. R2 (Test)	5-Fold CV Mean R2
Linear Regression	4.20	0.29	0.19	0.14	-0.72	0.03
Decision Tree	4.31	0.69	0.65	0.09	-0.82	0.02
Random Forest	4.07	0.89	0.88	0.19	-0.62	0.21
XGBoost	4.16	0.46	0.38	0.16	-0.69	0.24
Portuguese Results:

Model	RMSE	R2 (Train)	Adj. R2 (Train)	R2 (Test)	Adj. R2 (Test)	5-Fold CV Mean R2
Linear Regression	2.86	0.39	0.34	0.16	-0.20	0.25
Decision Tree	3.48	0.60	0.57	-0.24	-0.78	-0.03
Random Forest	2.73	0.83	0.82	0.23	-0.10	0.31
XGBoost	2.81	0.59	0.56	0.19	-0.16	0.25
Feature Importance
Math (Random Forest):

Most important features: absences, failures, goout, health, freetime
Portuguese (Random Forest):

Most important features: absences, failures, health, freetime, studytime
Conclusions
Strong Predictors: G1 and G2 are strong predictors of G3. Without them, the model's performance drops significantly.
Influence of Behavioral and Socio-economic Factors: Absences, failures, and social behaviors are crucial predictors when G1 and G2 are not available.
Recommendations for Educators
Holistic Student Support: Address not only academic needs but also personal and social challenges.
Interventions for Absenteeism and Failures: Monitor and intervene early for absenteeism and provide remedial support for students with academic failures.
Parental and Guardian Engagement: Involve parents and guardians in the educational process.
Behavioral and Health Interventions: Promote healthy lifestyles and provide resources for mental health and wellness.
Flexible and Inclusive Learning Environment: Create an inclusive learning environment that accommodates diverse needs and learning styles.
Focus on Study Habits: Teach effective study habits and time management skills.

Acknowledgments
Cortez, P., & Silva, A. (2008). Using Data Mining to Predict Secondary School Student Performance.
