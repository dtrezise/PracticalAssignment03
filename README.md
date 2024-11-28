# BH-PCMLAI Practical Assignment03 - Dan Trezise

# Jupiter Notebook


# Overview
Compare the performance of the classifiers 
    k-nearest neighbors 
    logistic regression 
    decision trees  
    support vector machines 

# Business Problem
    - The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls.
    - The classification goal is to predict if the client will subscribe (yes/no) a term deposit (variable y).

https://archive.ics.uci.edu/dataset/222/bank+marketing

# DATA REVIEW
Looking at the the dataframe to identify any issues with the data using

# DATA CLEANING
### Data issues:

     - This Data was very organized and cleaned to start with.
     - four columns: job, education, contact, and poutcome had nulls - dropped all these
     - Replaced "yes & no" values with " 1 & 0" values
     - converted object types to int where possible
     - final cleaned shape is 45211 by 12

# Scaling
    The following columns were scaled with four different 
    scalers then merged back with the rest of the features:

        balance, duration, campaign, and pdays

    Scalers: standardization, minmax, robust and normalizations

    Each model was tried without scaled data and then with each variation of scaler to get the best model.

# 4 classification Models were tested with the data:

# Logistic Regression Model
    A standard logistic model as well as polynomials of degrees of 2 and 5 were fit to the data.

    The best result was using a standardization scaler and polynomial degree of 5:
        Results:
            Score = 0.9025500047397857       R2 Score = 0.05569185440350799  

# Decision Tree Model 
    Decision Tree models with max depth of 0 to 32 were fit to the data.

    The best result was using a normalization scaler and max depth of 20:
        Results:
           Score = 0.9921951527790944       R2 Score = 0.9243696135011888 

    (increasing max depth to 24 scored better but risked overfitting)

# K-Nearest Neighbors 
    KNN models with n of 1 to 6 were fit to the data.

    The best result was using a robust scaler and n = 3:
        Results:
           KNN 3 Score = 0.9281764464246216       KNN 3 R2 Score = 0.3040167266728838 

# Support Vector Machine (SVM)
    A SVM model was fit to the data.

    The best result was using a minmax scaler:
        Results:
           Score = 0.8889942174613708       R2 Score = -0.07566618530495339 


# Conclusion:
    From the variations of the 4 different classification model fit to the data,
    The Decision Tree model got the best results consistently with KNN following second.
    The SVM did not perform well compared to the others.

    The Decision Tree model has a good prediction of if the client will subscribe a term deposit.

# Next Steps
    
    - Revisit the models in this exercise with different selections of features to see if there are any better results.
    - Test the best model with new updated data
