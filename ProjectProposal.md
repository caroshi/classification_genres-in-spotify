# Classification Project Proposal

## Question: 
As a music fanatic and vinyl collector, I often find myself in a circular debates with friends and family about the construct of genres in music that seems to go nowhere. Are genre labels meaningless, what is the point of sub genres? Is it possible for a machine learning model to distinguish between different music genres? What features help a machine distinguish between one and the other. I plan to set out to see if it is possible for a model to assign genres to tracks I have pulled from Spotify. 

## Data: 
I plan on starting off with a set of 10,000 songs pulled from Spotify, using their API, grabbing only songs under the "Jazz" and "Rock" genre to see how well my model is able to distinguish between the two. I am intentionally picking two genres that might have more disparity so my model has an easier time classifying tracks. Time allowing, I would like to grab another set of songs from another genre to see how my model fairs. 

I will be grabbing the following features:

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

## Tools:
* Numpy, Pandas for EDA
* SQL for data storage
* Matplotlib, Seaborn  for data visualization
* Scikit-learn for modelling and analysis
* API for data acquisition

## MVP:
Ideally, I would like to have a few different types of classification models implemented for my MVP. 
