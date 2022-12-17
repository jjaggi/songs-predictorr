# songs-predictorr

INTRODUCTION

DJ Khaled bragged that he always predicts when a song will become popular.
We chose to carry out more research by focusing on the following three issues:
What factors have the biggest impact on a song's success, are there specific traits for hit songs, and can the success of older songs even be predicted by the success of newer ones? It's difficult to forecast a song's popularity.
We used the Columbia University Million Song Dataset, Spotify's API, and machine learning prediction models to get the answers to these questions.
We offer a model that, with over 68% accuracy, can forecast the likelihood that a song will be a hit, as measured by its appearance in Billboard's Top 100.


Cleaning dataset

The dataset contained several unusable fields because of outdated data.
Since Spotify changed the API, there was no echonest API to fill in the many blank data fields.
As a result, numerous fields had to be removed. We chose to use the mean to fill in the missing values for those features that were just missing a small amount.
The artist familiarity field, which had only 10 missing data, serves as an illustration of this.

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

In this study, Spotify's API was used to construct feature extraction algorithms, identify trends in popular music, and demonstrate the feasibility of predicting music hotness.
With an AUC score of 0.68, XGBoost offered the training model's best predictions.

![image](https://user-images.githubusercontent.com/72747338/205502612-6cf68606-e930-4cc6-b6b9-62d32c8a285d.png)


CONCLUSION

We weren't sure if it was even possible to anticipate a song's popularity more accurately than at random when we started this project. After putting our model to the test on fresh tracks downloaded from Spotify, we find that it is much easier to forecast a dud than a hit.
Due to the skewed nature of our data—only 1,200 hit songs—it may have been simpler to predict non-hit songs.
Moving future, we'd like to investigate how details like the artist's location or the song's release date can affect how popular a song is.
We might also think about using the entire dataset to see if we can make our models better.
Using the Spotify API to get our own data is another option.
