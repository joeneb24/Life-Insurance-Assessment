# Life Insurance Assessment

![image](https://user-images.githubusercontent.com/123125444/230565859-2c16638c-8324-46e6-90a7-8659fa70f0f9.png)


# Importance of Analyzing and Predicting Life Insurance Assessments
As a life insurance agent, I always wondered what kind of machine learning is used to quickly assess whether or not a client is qualified for that particular life insurance policy. As a quick overview of the life insurance process, as a field underwriter, I need to fill out a client's application with their personal information which includes but are not limited to the following: height, weight, health issues, tabacco use, career/job, family health history, and insurance policy they are looking to purchase. Each of these factors greatly effects their policy premium and what kind of policy they qualify to purchase. Having said this, we want to make sure we are insuring clients that are insurable, meaning that they are healthy enough and don't provide too much of a risk to provide insurance for AND we need to make sure that this process is done quickly enough to get an approval. From experience selling life insurance, many clients who are in the buying process want an answer quickly if not instantly, which does one of two things, it helps that person get coverage right away and also helps pay the insurance agent and the company quicker. Having said all of this, the question really becomes, how much are we willing to sacrifice in our ablitly to corecctly assess a person's qualification for a policy versus how quickly we want this process to be done.

### Disclaimer
The data set used came from a Kaggle competition 7 years ago that Prudential Life hosted. I took parts of the dataset to demonstrate my machine learning skills. A follow up analysis of the full data set will be posted on my GitHub in the future. 
Kaggle Competition: https://www.kaggle.com/competitions/prudential-life-insurance-assessment/data

# Data Dictionary
![download](https://user-images.githubusercontent.com/123125444/230571083-37d71153-5edd-4f12-b7a7-8bf34e15ab71.png)

# Quick Note on the data:
The data set provided, the variables that were continuous were given as normalized values, meaning that the largest value for that variable was set to 1 and the lowest value in that variable was 0.

# Data preparation and cleaning was done on the data before the following processes:

## Exploratory Visuals
- The figure below is a histogram that shows the distribution of the normalized age of the clients applying for life insurance. If the maximum age in assumed to be 100 and minimum age is 0, from the figure below we can infer that the median age of people looking for a life insurance are in their 40's. The median age is shown with the dashed line

![aa8f3b22-9c5e-4c4a-af52-2e2279dedd64](https://user-images.githubusercontent.com/123125444/230570440-e05ca8cf-4374-472f-b7a7-95b4c65c816e.png)

-  The figure below shows the distribution of how many people fall into the different categories of assessments, which are called responses. Responses is the target that we wish to predict for each client. The numbers are not continuous, they are nominal categorical. We see that most of our clients are under the "8" assessment aka Response. 

![646d3911-8d38-4c52-a80d-238826e8733c](https://user-images.githubusercontent.com/123125444/230572162-10aa6bb6-855e-4a0b-a86e-546efe595ffc.png)

- The figure below shows the correlations between all of the continuous variables. We see that there are strong correlations with Ins_Age and Family_Hist_2, Ins_age and Family_Hist_4, and Family_Hist_4 and Family_Hist_2. They are moderate correlations between Employment_Info_6 with Family_Hist2 and Family_Hist_4. We also see strong correlations beween the Ht/Wt and Wt/BMI, which all make sense because BMI changes greatly with Wt. 

![df8491f4-737f-4c7d-a81e-ce1bbf6e19b4](https://user-images.githubusercontent.com/123125444/230573361-8bfa4eeb-e2af-4602-9ff0-8c19719f1424.png)

## Explanatory Data Analysis
- From the figure above, we see that people at Response 5 have the highest average BMI. Generally the higher the BMI, the higher your risk is for health issues. Insurance companies need to collect client's BMI for health risk assessments. 

![f0bd9378-63e2-41db-87f0-d0c7d3627c24](https://user-images.githubusercontent.com/123125444/230573554-2843a0b8-229d-4458-81b7-65b0922272c8.png)

- Another key to determining someone's health risk or Response is Age. We see that older individuals are in Response 1, and we see that the average age for Response 5 individuals are younger. 

![ea416b1b-1eee-482c-b7c0-1f25971aad1f](https://user-images.githubusercontent.com/123125444/230573773-7fd30f7c-dfb2-4c01-92fb-475de3bbcc20.png)

- In the figure below, we see that weight when plotted against Response is in the same order as when being plotted with BMI. This tells us that weight is correlated with BMI, which makes sense since BMI is weight/height. We want to see if the Response lines up for both BMI and average weight.
- ![5aa4d987-f729-4be7-bd92-5f883afcdd8f](https://user-images.githubusercontent.com/123125444/230574085-75c6ece8-56bf-45ef-9321-f80fd2c9135b.png)
 
- From the figure above, we see that their is a strong correlation between BMI and Weight, which makes sense becuase you need weight to calculate BMI. The most interesting observation is that the response are in the same order of greatest to least when it comes to the Response.

- From the figures above, we see that Age, Weight and BMI do effect someone's risk assessment. This does make a lot of sense because people with higher BMI and weight present health risks, since higher BMI and weight are tied to a lot of health issues such as high blood pressure and heart disease. Also, age effects someone's risk assessment because in general, the older someone get, the higher the change they will develope health problems. 

## Machine Learning Using the Following Models:
- Random Forest Classification Model
- Decision Tree Classfiication Model
- 
## Machine Learning Techniques Used:
- Tuning
- Feature Engineering

## Models Evaluated & Results:
- Quick note: since this data set was meant for competition, not much information was given on what each variable or feature meant, I had to use my best judgement on how I evaluated the data. Since, we didn't have much context given, I was only looking for the most accuarate models.

Random Forest Models:
- Untuned, No Feature Engineering
  * Test Accuracy Score : 0.46084072294049955
  * Time to evaluate: 14.4 sec
- Untuned, with Feature Engineering
  * Test Accuracy Score : 0.46084072294049955
  * Time to evaluate: 15.5 sec
- Tuned, No Feature Engineering
  * Test Accuracy Score : 0.39010356731875717
  * Time to evaluate: 1 min 31.1 sec
- Tuned, with Feature Engineering
  * Test Accuracy Score : 0.39010356731875717
  * Time to evaluate: 1 min 31.3 sec
 
Decision Tree Models:
- Untuned, No Feature Engineering
  * Test Accuracy Score : 0.3389291274622622
  * Time to evaluate: 2.5 sec
- Untuned, with Feature Engineering
  * Test Accuracy Score : 0.3389291274622622
  * Time to evaluate: 2.5 sec
- Tuned, No Feature Engineering
  * Test Accuracy Score : 0.4546131456034658
  * Time to evaluate: 1 min 42.7 secs
- Tuned, with Feature Engineering
  * Test Accuracy Score : 0.4546131456034658
  * Time to evaluate: 1 min 39.2 seconds

## Key Insights
* We see that the tuned random forest model before and after feature engineering had a poor accuracy score of 0.39010356731875717. The only difference observed was that the tuned feature engineered random forest model took 1 min 31.3 sec seconds while the unengineered tuned model took 1 min 31.1 sec. 

* We see that the untuned random forest model before and after feature engineering had a poor accuracy score of 0.46084072294049955. The only difference observed was that the untuned feature engineered random forest model took 1 second longer to execute as compared to the tuned untuned unengineered untuned model, at 15.5 sec and 14.4 sec, respectively.

* In conclusion, the best model to use out of the four random forest models was the unengineered and untuned random forest model since it was the fastest to execute and had the highest accuracy score. 

* We see that the tuned decision tree model before and after feature engineering had a poor accuracy score of 0.4546131456034658. The only difference observed was that the tuned feature engineered decision tree model took 1 min 39.2 seconds while the unengineered tuned model took 1 min 42.7 secs. 

* We see that the untuned decision tree model before and after feature engineering had a poor accuracy score of 0.3389291274622622. They also performed similarily comparing time to execute, were we observed that the untuned feature engineered decision tree model took 2.5 seconds to execute as well as the untuned unengineered untuned model at the same 2.5 seconds.

* In conclusion, the best model to use out of the four decision trees was the feature engineered and tuned decision tree model since it was the fastest to execute and had the highest accuracy score. 

# Final Recommendation
- From the eight models I made, the best one was by far the random forest model that was untuned with no feature engineering. It had the highest accuracy score of all the models and it was the fastest performing random forest model. 
- For insurance companies to choose the right model, it has to be accurate and relatively fast if you need a decision to be made right away. Many insurance companies are gravitating towards instant application approvals, assuming their client qualifies. The clients I work with are ecstatic when I can deliver them good news that their application is approved. It makes them want to keep the policy in force, and for me most importantly I can get paid quicker if the policy is instantly approved. Machine learning is vital to making the process fast and accurate, since insurance companies must have a way to control and lower their risks as well. 

# Reflection: 
- The data cleaning and feature dropping may have caused my accurracy to go down considerably. I made these choices to speed up the machine learning process and also to made the data set more managable. Furthermore, upon reflection, the compeition data set may not have been a good choice to run these prediction models on. Also, this was just a project to show my machine learning skill set on a large data set. Finnaly, in the future I will use the full data set and will consider using PCA and other methods. I also have plans to revisit this project to include unsurpervised learning. 

