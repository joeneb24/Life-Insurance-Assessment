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




