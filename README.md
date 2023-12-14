This analysis is part of the Udacity Data Analysis Nanodegree program and aims to explore a data set containing 100k medical appointments. The data set contains unique ID number for each patient. There are also 14 other associated variables that the patient would answer to if they were applicable to them. Those variables are Patient ID, Appointment ID, Gender, the day someone registered the appointment, the day the of the actual appointment, age, Neighborhood, scholarship: if said patient received government assistance, Hypertension, Diabetes, Alcoholism, Handicap, if patient received SMS message and the outcome of the appointment.
We identified the categorical columns in the data set as the ones with objects and utilized on-hot encoder, as it was the ideal encoder for this data set. This data set included nominal data in no inherent order. Utilizing one-hot encoder for this data set would drive interpretability.

Using the logistics regression based on the specific of the data set, we were able to initialize, train and evaluate the predictive model. Preprocessing techniques ensured the data was ready for training by removing false positives and encouraged precision. One limitation we noticed right away was the sensitivity the linear regression model had to outliers, leading to bias. The model we also used was neural networks. 

To clean the data, the first thing we did was remove duplicate data and outliers. Since each patient had a unique identifier, it was easy to remove duplicates as well as the appointment ID. Along with removing duplicate data, we wanted to remove rows that showed up as 'null' and renamed the columns that were important to our analysis. We then created a new column for number of days between when the appointment was scheduled and when the appointment occurred and mapped target outcomes to numeric values.

In the first neural net attempt we used all features from preprocessing including one-hot encoded categorical features. 80% was used for training and 20% was used for testing. This resulted in good accuracy, but poor precision and recall for No-Show predictions. Our target outcomes distribution was largely imbalanced, so we used an under-sampling technique, but this decreased out dataset from 100k row to 45k. In the second attempt we used a balanced target outcome using under sampling. This resulted in much more precision and recall scores but a decrease in accuracy.  In the third attempt we explored additional preprocessing. We added columns for every day of the week for the appointment and when the appointment was scheduled, mapped gender and neighborhoods to numeric values, and added a column to generate a score of comorbidities present. With increased data to 85%, added 3rd hidden layer and increased epochs to 100 we saw a small increase in accuracy. The best overall performance was the neural net with additional engineered features. 

There are several reasons for missing appointments, but we know that this comes at a monetary loss for hospitals and health professionals. If our model could be trained, optimized, and improved, this can help predict likelihood of patient attendance and decrease losses for the health industry. 







  
  
