Project Overview:

  This project aims to predict the final year grades (G3) of students based on various socio-economic, personal, and 
  academic factors using machine learning models. The dataset used for this analysis includes student performance data in 
  both Math and Portuguese courses.

Data Sources

   The datasets used in this project are sourced from:
   student-mat.csv: Student performance in Math
   student-por.csv: Student performance in Portuguese

These datasets were originally used in the study by Cortez and Silva (2008) and contain various features related to student demographics, social and economic context, and academic performance.


Exploratory Data Analysis (EDA)


Key insights include:

    The Math dataset has 395 rows and 33 columns
    The Portuguese dataset has 649 rows and 33 columns
    Both datasets contain the same number of columns but different numbers of students
    No missing values
    Both datasets have similar distributions for most variables.
    The average age of students in both datasets is around 16.7 years.
    The median education levels of parents (Medu, Fedu) are quite similar.
    The G3 (final grade) variable has a slightly higher mean in the Portuguese dataset (11.9) compared to the Math dataset 
    (10.4).
    Absences are generally lower in the Portuguese dataset (mean of 3.66) compared to the Math dataset (mean of 5.71).
    These observations provide an initial understanding of the data distributions and central tendencies, which are 
    crucial for the regression analysis on G3.
    Academic performance is consistently negatively impacted by the number of failures across both subjects.
    Higher parental education levels are associated with better academic performance.
    There are weak correlations between absences and academic performance, suggesting that absences alone may not 
    significantly affect grades.
    Age has a slight negative correlation with performance, indicating that younger students tend to perform slightly better.
    Alcohol consumption is inversely related to study time, and higher consumption is generally associated with lower 
    academic performance.
    
    Categorical Features Analysis:
    School Distribution: GP student count is dominating MS student count in both dataset especially in the Math
    Sex: The gender distribution shows a relatively balanced split between male and female students in both subjects. With 
    slight advantage for females in both data sets
    Address: A larger proportion of students come from urban areas (U) compared to rural areas (R).
    Family Size: Most students come from medium-sized to big families (GT3).
    Parental Status: The majority of students’ parents live together (T).
    Parental Jobs: The most common jobs for mothers and fathers are teacher and services, respectively.
    Reason for Choosing the School: The primary reason for choosing the school is course preference.
    Guardian: Most students are under the guardianship of their mother.
    Support and Activities: School support (schoolsup) is generally lower and family support (famsup) is generally high, 
    while a significant proportion of students participate in extracurricular activities (activities) and plan to pursue 
    higher education (higher).
    Internet Access: Most students have access to the internet at home.
    Romantic Relationships: A notable proportion of students are in romantic relationships.
    
    Ordinal Features Analysis
    Parental Education: The education levels of mothers and fathers show a similar distribution, with many parents having 
    secondary education.
    Travel Time: Most students have a short travel time to school.
    Study Time: Students typically spend 2-5 hours per week on study, indicating a moderate study habit.
    Family Relationship: Family relationships are generally good, with most students rating them highly.
    Free Time: Students have a moderate amount of free time.
    Going Out: Students' frequency of going out is balanced, with no extreme tendencies.
    Alcohol Consumption: Both weekday (Dalc) and weekend (Walc) alcohol consumption are generally low, with an increase 
    over weekends.
    Health: Health ratings are fairly high, with most students reporting good health.
    
    Continuous Features Analysis
    Age: The age distribution of students is concentrated around 15-18 years.
    Failures: Most students have no past class failures, though a few have one or more.
    Absences: The number of absences varies widely, with many students having few or no absences
    Grades: The distributions of the grades (G1, G2, G3) show that most students perform moderately well, though there is 
    variability, with some students scoring very low or very high.
    
    Relationships Between Variables
    Age and Study Time: Older students tend to study less, potentially due to increasing responsibilities or workload.
    Study Time and Grades: A positive relationship is observed between study time and final grades (G3), suggesting that 
    more study time could lead to better performance.
    Failures and Grades: Students with more past failures tend to have lower final grades.
    Absences and Grades: A negative correlation exists between absences and grades, indicating that higher absenteeism 
    leads to lower performance.
    
Data Preprocessing

  The data preprocessing steps include:
  Handling categorical variables using OneHotEncoder.
  Scaling numerical features using StandardScaler.
  Splitting the dataset into training and testing sets.

Models

  The following models were built and evaluated:
  Linear Regression,
  Decision Tree Regressor,
  Random Forest Regressor,
  XGBoost Regressor,
  
  Model Performance
  Math Results (Initial Model Including G1 and G2):
  
    Model	RMSE	R2 (Train)	Adj. R2 (Train)	R2 (Test)	Adj. R2 (Test)	5-Fold CV Mean R2
    Linear Regression	2.38	0.87	0.85	0.72	0.42	0.79
    Decision Tree	2.37	1.00	0.99	0.73	0.42	0.81
    Random Forest	2.13	0.97	0.97	0.78	0.54	0.78
    XGBoost	1.95	0.97	0.97	0.81	0.61	0.87

  Best Model: XGBoost
  
    RMSE: XGBoost has the lowest RMSE (1.949), indicating the smallest average prediction error.
    R2 (Test): It has the highest R2 (Test) value (0.814), meaning it explains the most variance in the test data compared to other models.
    Adjusted R2 (Test): It has the highest Adjusted R2 (Test) (0.609), reflecting its performance adjusted for the number of predictors.
    5-Fold CV Mean R2: The highest mean R2 (0.865) in cross-validation, demonstrating consistent performance.
    
Educational advice based on top features for math education

    G2 Grade: Since G2 has the highest importance, educators should focus on continuous assessment and improvement strategies 
    throughout the term, not just before final exams. Regular feedback and targeted support can help improve final grades.
 
    Absences: High absenteeism negatively impacts performance. Schools should implement attendance tracking systems and 
    intervention strategies to identify and support frequently absent students.
 
    Age: Age shows some influence, possibly reflecting maturity and readiness. Differentiated instruction strategies that 
    cater to varying maturity levels could be beneficial.
 
    Family Relationships (Famrel): Good family relationships are linked to better performance. Schools could involve families 
    in educational activities and provide resources to improve home environments.
 
    School Type (School_MS): The type of school can impact performance. Understanding and addressing specific challenges faced by students in different school types is crucial.

Portuguese Results (Initial Model Including G1 and G2):

    Model	RMSE	R2 (Train)	Adj. R2 (Train)	R2 (Test)	Adj. R2 (Test)	5-Fold CV Mean R2
    Linear Regression	1.21	0.86	0.85	0.85	0.78	0.84
    Decision Tree	1.48	0.89	0.88	0.78	0.67	0.77
    Random Forest	1.44	0.97	0.97	0.79	0.69	0.78
    XGBoost	1.23	0.93	0.92	0.84	0.77	0.85

Best Model: Linear Regression

    RMSE: Linear Regression has the lowest RMSE (1.214), indicating the smallest average prediction error.
    R2 (Test): It has the highest R2 (Test) value (0.849), meaning it explains the most variance in the test data compared to other models.
    Adjusted R2 (Test): It has the highest Adjusted R2 (Test) (0.778), reflecting its performance adjusted for the number of predictors.
    5-Fold CV Mean R2: The second-highest mean R2 (0.836) in cross-validation, demonstrating consistent performance, with XGBoost having slightly higher cross-validation mean R2 but performing slightly worse on test data RMSE.

Educational advice based on top features for portuguese education

    G2 and G1 Grades: Both G2 and G1 grades are highly important, suggesting that performance across all terms significantly impacts final outcomes. Continuous assessment and reinforcement of learning throughout the academic year are vital.
    
    Mother's Job in Health Sector (Mjob_health) and Teacher (Mjob_teacher): These features indicate a correlation with better student performance. This might be due to better educational support at home. Schools should ensure that students without such support 
    receive additional resources and guidance.
    
    Guardian Other than Parent (Guardian_other): Students with guardians other than parents might face unique challenges. Schools should provide additional counseling and support services for these students.
    
    Higher Education Aspirations (higher_yes): Encouraging students to aim for higher education can positively impact their performance. Schools should promote the benefits of higher education and provide information and support to pursue it.
    Travel Time (traveltime): Longer travel times can negatively impact student performance. Schools should consider solutions to minimize travel time or provide additional support for students with long commutes.


Math Results Model (Excluding G1 and G2):

    Model	RMSE	R2 (Train)	Adj. R2 (Train)	R2 (Test)	Adj. R2 (Test)	5-Fold CV Mean R2
    Linear Regression	4.20	0.29	0.19	0.14	-0.72	0.03
    Decision Tree	4.31	0.69	0.65	0.09	-0.82	0.02
    Random Forest	4.07	0.89	0.88	0.19	-0.62	0.21
    XGBoost	4.16	0.46	0.38	0.16	-0.69	0.24

Best Model: Random Forest

    RMSE: Random Forest has the lowest RMSE (4.067), indicating the smallest average prediction error.
    R2 (Test): It has the highest R2 (Test) value (0.193), meaning it explains the most variance in the test data compared to other models.
    Adjusted R2 (Test): Despite being negative (-0.613), it is the least negative among the models, reflecting its relatively better performance adjusted for the number of predictors.
    5-Fold CV Mean R2: The highest mean R2 (0.214) in cross-validation, demonstrating consistent performance.

Educational advice based on top features for math education

    Absences: High absenteeism is strongly linked to poor performance. Schools should:
    Implement robust attendance monitoring systems.
    Provide interventions and support for students with high absenteeism.
    Engage with parents to emphasize the importance of regular attendance.
    
    Failures: The number of past failures is a critical predictor of future performance. Schools should:
    Offer remedial classes and tutoring for students who have previously failed subjects.
    Provide personalized learning plans to address gaps in knowledge.
    Use early warning systems to identify and support at-risk students before they fail.
    
    Go Out (Socializing): Frequent socializing can negatively impact performance. Schools should:
    Educate students on time management and the importance of balancing social activities with academic responsibilities.
    Promote extracurricular activities that combine social interaction with academic enrichment.
    
    Health: Good health is associated with better academic outcomes. Schools should:
    Implement health education programs focusing on nutrition, exercise, and mental well-being.
    Provide access to health services and counseling for students in need.
    
    Free Time: How students use their free time can impact their academic performance. Schools should:
    Encourage productive use of free time through extracurricular activities, clubs, and study groups.
    Provide resources and spaces for students to engage in academic and personal development activities outside of class hours.

Portuguese Results Model (Excluding G1 and G2):

    Model	RMSE	R2 (Train)	Adj. R2 (Train)	R2 (Test)	Adj. R2 (Test)	5-Fold CV Mean R2
    Linear Regression	2.86	0.39	0.34	0.16	-0.20	0.25
    Decision Tree	3.48	0.60	0.57	-0.24	-0.78	-0.03
    Random Forest	2.73	0.83	0.82	0.23	-0.10	0.31
    XGBoost	2.81	0.59	0.56	0.19	-0.16	0.25

Best Model: Random Forest

    RMSE: Random Forest has the lowest RMSE (2.712), indicating the smallest average prediction error.
    R2 (Test): It has the highest R2 (Test) value (0.246), meaning it explains the most variance in the test data compared to other models.
    Adjusted R2 (Test): Despite being negative (-0.081), it is the least negative among the models, reflecting its relatively better performance adjusted for the number of predictors.
    5-Fold CV Mean R2: The highest mean R2 (0.316) in cross-validation, demonstrating consistent performance.

Educational advice based on top features for portuguese education

    Failures: Similar to Math, the number of past failures is a significant predictor. Schools should:
    Implement targeted interventions for students with a history of academic struggles.
    Use diagnostic assessments to tailor instruction to individual student needs.
    
    Absences: Attendance remains a crucial factor. Schools should:
    Develop programs to improve student engagement and attendance.
    Work with families to address barriers to regular attendance.
    
    Weekend Alcohol Consumption (Walc): High weekend alcohol consumption negatively affects performance. Schools should:
    Educate students on the effects of alcohol on academic performance and health.
    Promote alcohol-free social events and activities.
    
    Age: Age can reflect maturity and readiness for academic challenges. Schools should:
    Use differentiated instruction strategies to cater to varying maturity levels.
    Provide age-appropriate support and resources.
    
    Go Out (Socializing): Similar to Math, socializing habits impact performance. Schools should:
    Teach students about the importance of balancing social activities with academic responsibilities.
    Create a school environment that promotes academic and social balance.

Conclusional Advice for Educators based on current research

    Based on the analysis, the following strategies are recommended to improve student performance in both Math and Portuguese:

    Continuous Monitoring and Support:

    Including G1 and G2: Use the 1st and 2nd period grades as early indicators to identify and support struggling students. Implement continuous assessment practices to monitor progress and adjust teaching strategies accordingly.
    Excluding G1 and G2: Focus on other predictors like absences and past failures to identify at-risk students early and provide necessary interventions.
    Enhancing Attendance:

    Develop comprehensive attendance monitoring systems.
    Engage parents and communities to emphasize the importance of regular school attendance.
    Address underlying issues causing absenteeism, such as health problems or lack of engagement.
    Targeted Interventions for Struggling Students:

    Offer remedial classes, tutoring, and personalized learning plans for students with a history of failures.
    Use data-driven approaches to identify at-risk students and provide tailored support to meet their individual needs.
    Promoting Health and Wellness:

    Implement health education programs focusing on nutrition, physical activity, and mental well-being.
    Provide access to school-based health services and counseling to address physical and mental health issues.
    Balancing Academics and Social Life:

    Educate students on the importance of time management and balancing social activities with academic responsibilities.
    Promote extracurricular activities that provide a balanced mix of social interaction and academic enrichment.
    Parental Involvement and Support:

    Encourage parental involvement in their children's education through regular communication and engagement initiatives.
    Provide resources and support for parents to help them understand how they can support their children's academic success.
    Holistic Education Approach:

    Adopt a holistic approach to education that considers academic performance, physical health, mental well-being, and social factors.
    Foster a supportive school environment that addresses the diverse needs of students and promotes overall development.

Acknowledgments
Cortez, P., & Silva, A. (2008). Using Data Mining to Predict Secondary School Student Performance.
