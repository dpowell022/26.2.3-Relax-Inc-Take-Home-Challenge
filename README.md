# predicting-user-adoption

### Project Goal
The goal of this project was to predict what factors best influence whether a user will become an 'adopted user', meaning that they logged into the project 3 times within a 7 day period. 

---
### The Data
The data provided included two tables, one with information on unique users, and another with timestamped user logins. Data was clean, but it lacked the target feature of 'Adopted' for the Users table, so this had to be calculated before EDA could be performed.

![](/images/user_adoption.png)

---
### The Process
First I defined a function that, for any user_id provided, it would iterate through the login timestamps for that user and return True if it found any instance of 3 logins occurring within a timedelta of 7 days, otherwise it would return False. 

Then, I iterated through the users table, calling the defined function for each unique user ID and compiling the True/False results into a List, which List was then used to populate a new series in the Users table for 'Adopted'.

Once I knew the adopted users, I could perform EDA to examine the relationships between the dependent variables and the target variable. I used OneHot Encoding to break up categorical variables, while also dropping any variables irrelevant to the correlation analysis.

Running a correlation heatmap analysis, it was found that there were few variables correlated to Adopted, but some positive correlations were defintely found and reported on. 

![](/images/relax_inc.JPG)

---
The full project report can be found [here](https://github.com/dpowell022/predicting-user-adoption/blob/main/Exercise%20Report.docx)

The full notebook can be found [here](https://github.com/dpowell022/predicting-user-adoption/blob/main/relax%20inc%20takehome%20challenge.ipynb)
