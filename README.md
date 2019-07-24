# Personalized-Cancer-Diagnosis
![image](https://user-images.githubusercontent.com/40149802/61819031-d2a2d380-ae6f-11e9-847a-b363a8bd58fc.png)

A lot has been said during the past several years about how precision medicine and, more concretely, how genetic testing is going to disrupt the way diseases like cancer are treated.  But this is only partially happening due to the huge amount of manual work still required. Memorial Sloan Kettering Cancer Center (MSKCC) launched this competition, accepted by the NIPS 2017 Competition Track,  because we need your help to take personalized medicine to its full potential.
![image](https://user-images.githubusercontent.com/40149802/61819100-f108cf00-ae6f-11e9-8862-8f07bfcdb3be.png)
Once sequenced, a cancer tumor can have thousands of genetic mutations. But the challenge is distinguishing the mutations that contribute to tumor growth (drivers) from the neutral mutations (passengers). 

Currently this interpretation of genetic mutations is being done manually. This is a very time-consuming task where a clinical pathologist has to manually review and classify every single genetic mutation based on evidence from text-based clinical literature.

For this competition MSKCC is making available an expert-annotated knowledge base where world-class researchers and oncologists have manually annotated thousands of mutations.

## Step step by step procedure that followed to solve this case study

###  Mounting Google Drive locally

###  Reading Gene and Variation Data

###  Reading Text Data
###  Splitting data into train, test and cross validation (64:20:16)
i.e

      Number of data points in train data: 2124
  
      Number of data points in test data: 665
      
      Number of data points in cross validation data: 532
###  Prediction using a 'Random' Model

In a 'Random' Model, we generate the NINE class probabilites randomly such that they sum to 1
Got a Log loss on Test Data using Random Model 2.47
###  Univariate Analysis

	Featurize this Gene, Variation and Text feature with One hot Encoding and Response coding.
###  Applying all the models with tf-idf features and Instead of using all the words in the dataset, using only the top 1000 words based of tf-idf values
 
![got1](https://user-images.githubusercontent.com/40149802/61819427-ac316800-ae70-11e9-8bd5-f8eaff7eb5e1.PNG)

After applying all the models with tf-idf features and Instead of using all the words in the dataset, using only the top 1000 words based of tf-idf values, Logistic Regression using One Hot Encoding with class balance has given 1.04 test logloss. Which is the lowest, as compaire to other models.

###  Apply Logistic regression with CountVectorizer Features, including unigrams, bigrams , tri_gram, 4_gram
 
 ![image](https://user-images.githubusercontent.com/40149802/61819588-f581b780-ae70-11e9-922e-162d12b28ebe.png)

 After using Bi_gram, Tri_gram and 4_gram, our LR model by using TFIDF using 4_gram with Top 6000 feature has given us a test log loss of 0.951.

###  Tried feature engineering techniques to reduce the CV and test log-loss to a value less than 1.0
Added Gean Feature Variation Featureto improve the performance. And after some feature engineering, I manage to decrease the log loss below < 1
![2](https://user-images.githubusercontent.com/40149802/61819349-7db38d00-ae70-11e9-92db-9c8cfb6d4986.PNG)

 I used TFIDF by 4_gram with top 6000 features, and got a test loss of 0.95 and CV loss of 0.98 which is < 1. And I got what I was expecting.


