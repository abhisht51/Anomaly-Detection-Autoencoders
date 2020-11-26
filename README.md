# Anomaly Detection using Autoencoders

AutoEncoders are great for compressing a high dimensional data into very compact data representing the most essential information about the data. This compact representation is called the latent space. AutoEncoders have been used for numerous applications specifically useful in generative models like Variational Autoencoder or improving the resolution of the image, dehazing the image. One of the most underrated applications of autoencoders would be anomaly detection. Anomaly detection is broadly a classification based problem where the model tries to predict where an example is ‘real’ data or an anomaly. This has been widely used in credit card fraud detection during transaction processing. 


## The Dataset 
The original dataset for "ECG5000" is a 20-hour long ECG downloaded from Physionet. The dataset contains 5,000 Time Series examples (obtained with ECG) with 140 timesteps. Each sequence corresponds to a single heartbeat from a single patient with congestive heart failure.  The data was pre-processed in two steps: (1) extract each heartbeat, (2) make each heartbeat equal length using interpolation. This dataset was originally used in the paper "A general framework for never-ending learning from time series streams", DAMI 29(6). After that, 5,000 heartbeats were randomly selected. The patient has severe congestive heart failure and the class values were obtained by automated annotation. 
The dataset has 5 types of heartbeats (classes [1,2,3,4,5] ):
Normal (N)
R-on-T Premature Ventricular Contraction (R-on-T PVC)
Premature Ventricular Contraction (PVC)
Supra-ventricular Premature or Ectopic Beat (SP or EB)
Unclassified Beat (UB).
There are 2919 samples of normal heartbeats. This dataset is heavily imbalanced however, we will consider every other class other than class 1 as an ‘anomaly’ thus the dataset becomes just slightly imbalanced. An important thing to note here is that we would be training the AutoEncoder on only the normal class data and having ~3000 samples of that is a good thing for our purpose.


## Approach 

Model 1 is built using Stacked AutoEncoders and not treating the data as a time series. 
Model 2 is build using LSTM based AutoEncoders thus treating the data as time series. 

