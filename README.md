# Music_Recommender_System

![blocks-T3mKJXfdims-unsplash](https://github.com/MaddieSmithers/Music_Recommender_System/assets/132934793/0e9ddbaa-f0eb-4aab-ac90-edcdf8c35f82)

## Introduction
In this project I use a dataset of about 600,000 tracks from Spotify to explore the best ways to recommend music to users. In order to combat current issues of bias in recommender systems, emerging music platforms should carefully consider which data features to emphasize or minimize in their models. By using audio data, popularity, release data, and the predicted language of each track, I explore trends in music over the last century in order to draw conclusions about what's really important to listeners. I discover that non-English music has been growing steadily in popularity since about 2011, while English music has been declining. I use a KMeans Clustering model to identify clusters in the dataset, then a Random Forest Classifier to identify the most important features in splitting the data. Through this process, I discover that langauge plays a very minor role in splitting the dataset, while the release decade appeared to have the most importance. Finally, I create a simple content-based recommender system that uses cosine similarity to recommend songs that are up 99% similar to a sample track, regardless of language. 
## Data Sources
- tracks.csv ---> contains the raw Spotify dataset
- master_track_data.csv ---> contains the cleaned and ammended dataset that includes columns for release decade and predicted track language
## Data Limitations
It is important to note that this data is limited in scale as it designed to be able to run locally on most personal laptops. Furthermore, many of the audio features of tracks rely on subjective answers, such as 'danceability' or 'liveness.' Finally, the language of each track was predicted using the langdetect library, which we cannot assume works with 100% accuracy. 
## Data Analysis 
<img width="1010" alt="Screenshot 2023-08-18 at 11 01 12 PM" src="https://github.com/MaddieSmithers/Music_Recommender_System/assets/132934793/1b5b9635-7005-4b36-9744-d7c777833513">
By looking at a correlation map, we can see some features that might be leading to multi colinearity. 

![lang](https://github.com/MaddieSmithers/Music_Recommender_System/assets/132934793/50611611-8374-4a5a-b558-dbba9d537835)

The dataset contains about 50 different languages, with English being the largest subset. 

<img width="880" alt="Screenshot 2023-08-18 at 11 03 40 PM" src="https://github.com/MaddieSmithers/Music_Recommender_System/assets/132934793/5f3b0ad7-3024-44f1-97bf-612ac8b3ab85">

From about 2011, non-English music surpasses English music in popularity. The gap only continues to widen until 2020, where our data ends. 

## Modeling
This notebook runs a KMeans Clustering model to split the data into nine distinct clusters. It then uses a Random Forest Classifier to extract the most important features of each cluster. From this, we learn that the release decade is the most indicative, while language didn't play an important role in any cluster. 
Because of this, I decided to drop all language columns before writing my content-based recommender system. By using cosine similarity and using "Where Have You Been?" by Rihanna as a sample track, the simple recommender system can identify tracks with up to 99% similarity from a variety of different languages. 
## Conclusion
While many recommender systems today continue to perpetuate bias and emphasize popular, English-language songs, newer systems that focus more on audio quality and less on language or location can provide accurate recommendations from a more diverse set of artists. Our analysis of the data shows that users are increasingly favoring non_Enlglish music, which suggests that users will likely be happy with more diverse recommendations. Because we saw the most important feature in predicting audio qualities to be the release decade, recommender systems should focus on release time features and consider also recommending playlists for different time periods. 
## Future Steps
This analysis should be run on a larger dataset to better represent the massive libraries available on streaming services. It should also be paired with real user-data in order to create a hybrid model for better recommendations. 

## Repository Structure 


```

├── data_cleaning.ipynb
├── data_EDA.ipynb
├── data
    ├── tracks.csv
    ├── master_track_data.csv
├── README.md
```

