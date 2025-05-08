# Movie Review Analysis

## About
This is an instructor-guided Data Science project of an international workshop - The Data Forge: Workshop and Contest, organized by NSDC-HerWILL Chapter Program. NSDC is the Northeast Big Data Innovation Hub’s National Student Data Corps (NSDC), part of Columbia University’s Data Science Institute.


## Overview
This project aims to analyze the users' sentiments on movie reviews and classify them into two (2) classes - `positive` and `negative`. It serves following aspects:

* Retrieving and accessing the target `.csv` file;
* Cleaning the data and preprocessing them;
* Training and testing the model;
* Predicting the type of reviews on the basis of trained model.


## Data Extraction
For this project, [Internet Movie Database (IMDb)](https://raw.githubusercontent.com/meghjoshii/NSDC_DataScienceProjects_SentimentAnalysis/main/IMDB%20Dataset.csv) was used, which contains 50,000 movie reviews pre-labeled with sentiment polarity (positive/negative). The dataset link was accessed using `read_csv` function. The dataset has two (2) columns - `review` and `sentiment`.


## Data Preprocessing
After successful data retrieval, preprocessing was performed using `nltk` library.

* `word_tokenize` function: Tokenizing the text
* `isalpha` function: Checking if a word is an alphabet or not
* `lower` function: Converting words to lowercase
* `stopwords` function (from `nltk.corpus` package): Getting a list of the stopwords (i.e., words that do not add any value to the text, e.g., a, an, the)
* `remove` function: Removing the stopwords
* `PorterStemmer` function (from `nltk.stem` package): Reducing a word to its root form


## Data Training and Testing
Preprocessed data were split into 2 categories - training (first 40,000 data) and testing (last 10,000 data). `CountVectorizer` function from `sklearn.feature_extraction.text` package was used to convert the text into a matrix of token counts. For the `sentiment` column, `LabelEncoder` function from `sklearn.preprocessing` package was used to convert the labels into numbers. Later, `fit_transform` and `transform` functions were used on the training and testing data, respectively, to fit the model to the data and then transform the data into a matrix of token counts.


## Building the Model
Multinomial Naive Bayes (`MultinomialNB` function from `sklearn.naive_bayes` package) was used to build the model.


## Data Visualization
To visualize the word frequnecy for a specific sentiment polarity, `WordCloud` function from the `wordcloud` package was used.

<table>
  <tr>
    <td align="center"><img src="https://github.com/ArnabUshna24/Movie-Review-Analysis/blob/main/positive_sentiment.png" alt="Positive Sentiment" width="300"/></td>
    <td align="center"><img src="https://github.com/ArnabUshna24/Movie-Review-Analysis/blob/main/negative_sentiment.png" alt="Negative Sentiment" width="300"/></td>
  </tr>
  <tr>
    <td align="center"> Fig. 1: Frequently used words having positive sentiment </td>
    <td align="center"> Fig. 2: Frequently used words having negative sentiment </td>
  </tr>
</table>


## Model Accuracy
Multinomial Naive Bayes: 0.7425


## Build from Source
Instructions are provided in the `ipynb` file.


If you have any queries, contact me: arnabnushna24@gmail.com
