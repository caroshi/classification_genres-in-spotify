# Classifying Music Genres for Spotify Tracks
Caroline Shi

## Abstract
As a music fanatic, I often find myself in a circular debates with friends and family about the construct of genres in music that seems to go nowhere. Are genre labels meaningless, what is the point of sub genres? Is it possible for a machine learning model to distinguish between different music genres? What features can help a machine distinguish between one and the other. I plan to set out to see if it is possible for a model to assign music genres to tracks I have pulled from Spotify.

## Design
The goal of this project was to build a classification model that predicts music genres for a selection of tracks taken from Spotify. Initially a binary model with two genres, I eventually expanded to a six genre classification model to test my model's ability to handle more complexity. The model was fitted from a data set grabbed from Spotify's API with minimal EDA and feature engineering needed due to the comprehensive data provided by Spotify. I was able to fit my data into 4 types of models: KNN, Logistic Regression, Random Forest, and XGBoost with XGBoost as the model with the highest accuracy obtained. 

## Data
I initially grabbed 5,000 tracks each for Jazz and Rock genres but my final model incorporated 4 more genres: Electronic, Country, Hip-Hop, and Classical. I grabbed a total of ~28,000 tracks for the following 19 features; 4 of which were categorical features that were not used for my model:

1. Track Name
2. Album
3. Artist
4. Release Date
5. Length
6. Popularity
7. Danceability
8. Energy
9. Key
10. Loudness
11. Mode
12. Speechiness
13. Acousticness
14. Instrumentalness
15. Liveness
16. Valence
17. Tempo
18. Time Signature
19. Genre

## Algorithms
* _Importing and Cleaning Data_
	* Used Spotify's API to grab 6 different playlists I made for each different genre and merged them together as one dataset in Python
	* Looked for missing values, dropped unnecessary columns

* _Modelling_
	* For my binary, 3 class, and 6 class models, I ran my data through 4 different algorithms: KNN, Logistic Regression, Random Forest, and XGBoost
	* For KNN and Logistic Regression, I scaled my data but did not have to account for an imbalanced dataset as I created my own balanced dataset
	* GridSearchCV was attempted but took up too much computing power and time
	* Accuracy was chosen as my classification metric to judge my dataset on as one target label is not more ideal than another as my classification problem pertains to whether or not I can accurately predict all genres, therefore precision/recall/F1 might not be as relevant to me. 
	* I ultimately picked XGBoost in favor of a higher accuracy score in lieu of interpretability 
		
* _Visualizing Data_
	* Used Matplotlib to create visualizations looking at feature distribution and confusion matrices 
	* Used SHAP to create a series of visualizations looking at feature importance

## Tools
* Numpy, Pandas for EDA
* Matplotlib, Seaborn, SHAP for data visualization
* Scikit-learn for modelling and analysis
* Spotify API for data acquisition

## Insights
* Of the four models I used, a XGBoost model best predicts music genre though with some caveats:
	* The use of all 14 numeric features has caused some overfitting and complexity -- something that needs to be looked at further, maybe some can be dropped with little accuracy penalty
	* XGBoost could be further tuned for better accuracy 
	* Genres that have both vocal and non vocal tracks such as Jazz and Electronic have a harder time being classified, maybe I should look into dividing these broad genres into sub-genres for future work

