# songs-predictorr

INTRODUCTION

DJ Khaled boldly claimed to always know when a song will be a hit.
We decided to further investigate by asking three key questions: 
Are there certain characteristics for hit songs, what are the largest influencers on a song’s success, 
and can old songs even predict the popularity of new songs? Predicting how popular a song will be is no easy task. 
To answer these questions, we made use of the Million Song Dataset provided by Columbia, Spotify’s API, and machine learning prediction models.
We present a model that can predict how likely a song will be a hit, defined by making it on Billboard’s Top 100, with over 68% accuracy.


Cleaning dataset

Many fields in the dataset were unusable due to old deprecated data. 
Many data fields were missing and there was no echonest API to fill in data since the API was modified by Spotify. 
Therefore many fields had to be dropped. Some features that were only missing a reasonable amount we decided to fill in the missing values with the mean.
An example of this is the artist familiarity field which had only 10 missing values.

The process can be summarized as followed:

Download the data subset from labrosa Columbia
Convert the data format from h5 to data frame
Scrape songs that have appeared on Top 100 BillBoard chart
Classified songs in the data
Cleaning the data set

![image](https://user-images.githubusercontent.com/72747338/205502471-3514a5e3-ec67-413a-b369-9a4fa1d0c893.png)

Artist Location

Artist Longitude vs. Song Hotness

![image](https://user-images.githubusercontent.com/72747338/205502515-3083f90d-d6ca-4ea7-8c63-67ca080686ad.png)

MODEL SELECTION & TUNING

We trained our data on different models to predict if a song is a hit song or not.
Xgboost appears to be the one with the highest accuracy at 0.63 area under the curve (AUC) score,
before tuning. The table below shows the results of some of the models that we tried.

![image](https://user-images.githubusercontent.com/72747338/205502565-6fe1f226-5e58-4c88-8507-cf94fc5df016.png)


RESULTS

This project demonstrated the possibility of predicting music hotness, identified trends in popular music,
and developed feature extraction tools using Spotify’s API. 
XGBoost provided the best predictions on the training model, with an AUC score of 0.68.

![image](https://user-images.githubusercontent.com/72747338/205502612-6cf68606-e930-4cc6-b6b9-62d32c8a285d.png)


CONCLUSION

Going into this endeavour, we were uncertain if it is even possible to predict, better than random, 
if a song will be popular or not. After testing our model on new songs pulling from Spotify,
we observe that it is significantly simpler to correctly predict a bad song rather than a hit.
It may have been easier to predict non hit songs because our data was skewed, with only 1,200 hit songs.
Moving forward, we would like to explore how additional features such as artist location or release date can influence a song’s popularity.
In addition, we may consider using the full dataset to see if we can improve our models. 
Another alternative is to use Spotify API to collect our own data.
