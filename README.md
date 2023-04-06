# Songs-Prediction-Analysis
Sentiment Analysis &amp; Predictive Analytics (NLP)

PROJECT OVERVIEW:

For our project, we wanted to analyze song lyrics for several things:

Word count trend: Visualize general trends for word count in relation to artists.

Lyric trend: Investigate which words are most commonly used by different artists.

Sentiment analysis: Investigate the overall sentiment related to each artist.

Predictive modeling: Predict the artist given the lyrics to a song

IDENTIFICATION OF DATASET:

Our dataset was acquired from Kaggle which consisted of three columns namely: Artists, Label & Lyrics.
Link to Datasets: 
https://www.kaggle.com/datasets/karnikakapoor/lyrics
https://www.kaggle.com/datasets/deepshah16/song-lyrics-dataset?select=csv

STAKEHOLDERS AND USE:

Artists: The artists could relate their song length, use of words and overall sentiment of the song and then analyse these areas. They could see the trend of lyrics, song sentiments and words in the current scenario and then make songs to fit the current scenario.

Music Streaming Platforms: The streaming platforms can use our system to observe the sentiment related to the songs and then generalize their category.

Movie Directors: The directors could observe the lyrics length to ensure it fits the general criteria and could also suggest changes in the words to make the sentiment of the song fit the overall sentiment of the scene.

Music Producers: The music producers could suggest change in repetitive words by an artist and they could also suggest changes in sentiment to fit the requirement.

Song Writers: The song writers could use our predictive model to know which artist could best deliver the lyrics that they have written.

OVERVIEW:

Python File 1: 

- We have imported the dataset and have dislayed a sample fo the dataset.
- We have tokenized the one single lyrics and have inspected any abnormalities during the tokenization, to rectify it in further process.
- We have tokenized the lyrics and removed unwanted inclusions in the tokenization step, we have then insterted this new tokenized entry into a column called tokenized lyrics.
- We created three new columns namely for Lyrics length, standardized lyrics length and average lyrics length respectively. In this step we have added the lyrics length of each of the songs, standardized the lyrics length and finally calculated the average lyrics length for an artist considering all his/her songs in the datset.
- We have displayed the top 10 artists with highest average lyrics length and the bottom 10 artists as well.
- Plot of the average lyrics length of artists
- We used the nltk library WordNetLemmatizer to Lemmatize the tokenized words. The lyrics first have been tokenised and then lemmatised. Also, we used the required nltk extensions such as wordnet,averaged perceptron tagger for the Lemmatizing the lyrics and doing Parts of Speech Tagging and word Frequency. We removed all the english stopwords and punctuations as well.
- We have counted the frequency of the words using Counter and tokenised words of the lyrics on the basis of the song of each artist.
- We used the word frquency to find the most common words used in the song by eah artist.
- We have used nltk library SentimentIntensityAnalyser to find the sentiment of each song. We have also calculated the Polarity scores/Sentiment scores for each song which ranges from -1 to 1. 

Pythong File 2: 

-This folder contains 2 datasets and the predictive models ran on both.

-The first dataset is one csv file that contains 745 songs made by 21 different artists.

-The second dataset contains 21 artists but we scrapped BTS since they are not exclusively english.

-We also scrapped 8 other artists that had the least amount of songs in their csv since we wanted to see the model trained on a lot of data. We also wanted to keep the songs per artist consistant in our model.

-This left us with 12 artists each having 296 songs in the dataset. Both models are using a neural network with the following structure: 

-Dense Layer with 100 outputs, relu activation, and a 25% dropout -> Dense Layer with 50 outputs, relu activation, and a 25% dropout -> Dense layer with 21/12 targets, softmax activation. 
Both models use ADAM with a learning rate of 1e-4 and a cross entropy loss function. The dropout layers were included toincrease our validation accuracy.

-With both datasets during training, we use a batch size of 70 along with having 1/4 of the data be for validation. 

-Both models preform almost perfect on the training data and the first and second model have an accuracy of 29% and 68% respectively. 

-Since the first model has 21 targets compared to 12 we wanted to see how much better each model does compared to a random guess.

-We found that the first model has a 6.09x better chance of guessing the correct artist while the second model has a 7.92x better chance of guessing the correct artist.


CHALLENGES:

1. Procuring dataset that is large enough for predictive modeling: As the predicitve modeling gets better with larger amounts of data, one challange we faced was to provide the model with large enough dataset for processing. 
2. Ambiguity of words used in the lyrics for POS Tagging: As the POS tagging works on words in english and there are times when it can not properly differentiate between the words to give it the correct POS.
3. “word###EmbedShare” found in the lyrics : words like these came up in chunks which were a challange to deal with. 
4. Some jargons could not be detected during lemmatization: Some jargons that would mean something else could not be converted completely during lemmatization, thats something we could consider in future scope of work. 
5. Words used in different languages: As there were many songs that had words used in different languages it was not possible to inlucde such words in the most common words counter as these words would not match with most other songs that were in english.

LIMITATIONS:

1. Limited Data: As mentioned above, with extensive data the model could give better predictions.
2. Limited Attributes to work on: We only had 3 columns that we could work on, with more attributes like date, time, ranking etc the model would be in a better position to arrive at predictions that before. 

FUTURE WORK:

Add more artists and songs to the dataset to train the model to be more accurate and span more artists for the practical applications

Enhance the data to give more categories (i.e. song billboard rank, release date, album name, genre, ect.) and create models that use those new categories to better predict the artist.

Utilize these new categories to predict billboard rank based on all other factors so writers and artists could try to predict if their song is a hit.

