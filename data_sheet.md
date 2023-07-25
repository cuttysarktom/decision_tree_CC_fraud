# Datasheet Template

## Motivation

- For what purpose was the dataset created? 

The dataset has been collected and analysed during a research collaboration of Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection.



- Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Who funded the creation of the dataset?

See comment above. The version I have used is the one hosted on Kaggle (https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud), and the requested citations in the acknowledgements were as follows:

Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. Calibrating Probability with Undersampling for Unbalanced Classification. In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015

Dal Pozzolo, Andrea; Caelen, Olivier; Le Borgne, Yann-Ael; Waterschoot, Serge; Bontempi, Gianluca. Learned lessons in credit card fraud detection from a practitioner perspective, Expert systems with applications,41,10,4915-4928,2014, Pergamon

Dal Pozzolo, Andrea; Boracchi, Giacomo; Caelen, Olivier; Alippi, Cesare; Bontempi, Gianluca. Credit card fraud detection: a realistic modeling and a novel learning strategy, IEEE transactions on neural networks and learning systems,29,8,3784-3797,2018,IEEE

Dal Pozzolo, Andrea Adaptive Machine learning for credit card fraud detection ULB MLG PhD thesis (supervised by G. Bontempi)

Carcillo, Fabrizio; Dal Pozzolo, Andrea; Le Borgne, Yann-Aël; Caelen, Olivier; Mazzer, Yannis; Bontempi, Gianluca. Scarff: a scalable framework for streaming credit card fraud detection with Spark, Information fusion,41, 182-194,2018,Elsevier

Carcillo, Fabrizio; Le Borgne, Yann-Aël; Caelen, Olivier; Bontempi, Gianluca. Streaming active learning strategies for real-life credit card fraud detection: assessment and visualization, International Journal of Data Science and Analytics, 5,4,285-300,2018,Springer International Publishing

Bertrand Lebichot, Yann-Aël Le Borgne, Liyun He, Frederic Oblé, Gianluca Bontempi Deep-Learning Domain Adaptation Techniques for Credit Cards Fraud Detection, INNSBDDL 2019: Recent Advances in Big Data and Deep Learning, pp 78-88, 2019

Fabrizio Carcillo, Yann-Aël Le Borgne, Olivier Caelen, Frederic Oblé, Gianluca Bontempi Combining Unsupervised and Supervised Learning in Credit Card Fraud Detection Information Sciences, 2019

Yann-Aël Le Borgne, Gianluca Bontempi Reproducible machine Learning for Credit Card Fraud Detection - Practical Handbook

Bertrand Lebichot, Gianmarco Paldino, Wissam Siblini, Liyun He, Frederic Oblé, Gianluca Bontempi Incremental learning strategies for credit cards fraud detection, IInternational Journal of Data Science and Analytics
 
## Composition

- What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? 
The instances represent credit card transactions which have undergone PCA transformation to select 28 key variables (labelled V1-V28 for anonymisation reasons), along with the monetary amount, time in seconds since the first transaction, and an outcome variable "Class" which is 1 for fraudulent items and 0 for non-fraudulent.

- How many instances of each type are there? 
There are 284,807 transactions, of which 492 are fraudulent and the remainder are non-fraudulent.
- Is there any missing data?
No, the data has already been pre-processed and cleansed so there are no rows with NA values.
- Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by    doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)?
The data would be considered confidential if it had not been transformed, but is now fully anonymised, including even the field names (beyond time, amount, and class).

## Collection process

- How was the data acquired? 
The dataset has been collected and analysed during a research collaboration of Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection. The method of collection is unknown to the author of this data sheet.

- If the data is a sample of a larger subset, what was the sampling strategy? 
This is not known to the author of this data sheet. 

- Over what time frame was the data collected?
This is not known to the author of this data sheet. 

## Preprocessing/cleaning/labelling

- Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remaining questions in this section. 

Yes, the data was fully anonymised and underwent PCA transformation. As a result, the version of the data available and used here is 28 variables labelled V1-V28, along with time in seconds since first transaction in the dataset, monetary amount, and class (fraudulent or not).

- Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? 

This is not known to the author of this datasheet.
 
## Uses

- What other tasks could the dataset be used for? 
The dataset is an anonymised credit card dataset. Based on the information available, it could potentially be used to predict the amount of transactions, but the primary purpose is in identification of fraud. 

- Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other risks or harms (e.g., legal risks, financial harms)? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? 
It is unknown if any of the fields in the data could lead to unfair treatment as they are anonymised and even the field names changed to V1-V28. However, because of this, the data will not be used beyond building and testing models (given it would not be possible without knowledge from the original collectors and processors) to take new data and classify it using the model built on this dataset.

- Are there tasks for which the dataset should not be used? If so, please provide a description.
Without having knowledge of the original data collected and transformations applied, this should only be used to build and test potential models on this dataset itself. 


## Distribution

- How has the dataset already been distributed? 
The version of the dataset that I have used is available on Kaggle: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The author of this data sheet is unaware of other distributions.

- Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?  

The data has an "Open Database" licence which is available for review here: https://opendatacommons.org/licenses/dbcl/1-0/


## Maintenance

- Who maintains the dataset?

It does not appear the dataset is maintained - it was updated 5 years ago and appears to be stationary.