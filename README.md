# vehicle-Insurance-Classification-
# Table of Content
1. [Introduction](#my_first_title)
2. [Method](#my-second-title)
3. [Result](#my-third-title)
4. [Usage](#my-fourth-title)


## **Introduction**

Cross-selling is a common selling practice in which addittional products or services are offered to current
customers. In this assignment you will use Machine Learning techniques on client of an insurance company
that has suscribed a health insurance in order to predict if they could be interested in a vehicle insurance
provided by the same company. 


### **DataSet Description**

### **Target Class**

The target attribute is binary: 1 – the customer is interested , 0 – the customer is not interested.



### **Attribute Information**



![Capture](https://user-images.githubusercontent.com/75788150/178162083-dfc23eeb-d826-4a79-a91e-a38197475d72.PNG)




## **Method**


### **Preprocessing and Data Preparation**


As the first step in the data processing and preparation, the column of the attribute license type was removed as a first attempt, as it has an already balanced distribution. Then, all rows containing missing data 
re removed from the set to avoid any noise. They weren’t replaced by for example the mean or median value to contain the accuracy of the data.
To visualize the categorical data (Gender, license type, previously insured, vehicle age and vehicle damage), they were represented in histograms showing the different records vs the frequency. Then all categorical attributes were represented as dummies.
Then the visualization of numerical data (Age, annual premium, driving licence, policy sales channel, region code, seniority, target and the log of the annual premium) was also represented in histograms and the log of the annual premium was taken to better understand it at a lower scale. Then all numerical attributes were standardized and presented in a boxplot.
From the numerical data I decided to keep the following attributes for our analysis: age, regional code, the log of the annual premium, the policy sales challenge and the seniority. The driving license attribute was treated as a dummy as it’s true for the majority, because it
varies only between 0 and 1 and the Standard Scaling of such attribute as Numerical will be
not very efficient during the calibration process . Hence, not indicating anything.


### **Training-Test Set**

The data was split then into a training and test set to apply the different classification methods
and test their accuracy. By default the test set was set to be 30% of the total data. For each
model, I defined the Model Structure itself and Parameterization space by which the greedy
search(gs) approach can iteratively examine through the defined space of parameters and pick
up the best parameter which can give us the minimum amount of
error(Objective_Function(J)). By defining the cross-validation (cv) equal to 3 in greedy
search, probability of over-fitting will decrease significantly.






## **Result**
![Capture](https://user-images.githubusercontent.com/75788150/178162009-e67c2612-4a2f-4c72-b651-431f6a8db8ec.PNG)


At first the roc curve was set in order to test the usefulness of each model applied. From
applying the six different models, I can see that all of them have very similar accuracies (f1
scores). They’re all around 67.8% , with the decision tree model being the highest with an
accuracy of 69.25%. This can be justified with the fact that the different attributes can be
easily split in different clusters. The similar f1 scores of the data and the fact that it’s always
around 67.8% can tell us that the behavior of the data is not easily predictable, resulting in a
higher uncertainty. This could be a result of inaccurate or biased data. Applying the SVM
model took a lot of time to run as it's based on a recursive optimization model. On the
contrary the Naive Bayes model that relies on probabilistic methods was able to run in a
shorter time. Finally, the logistic regression model is a mix between the two methods,
combining probabilistic and recursive optimization approaches.


## Usage
You use Google Colab or jupiter for running the algorithm.


