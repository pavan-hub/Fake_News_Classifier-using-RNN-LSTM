# Fake_News_Classifier-using-RNN-LSTM
This model was built using the Keras API. The dataset for the present model was obtained from kaggle(https://www.kaggle.com/clmentbisaillon/fake-and-real-news-dataset)
This metadata has 2 CSV files where one dataset contains fake news and the other contains true/real news and has nearly 23481 fake news and 21417 true news.
# Data Preprocessing and Cleaning
* The data is the missing the labels feature and hence I create a target column with value '0' for fake news and '1' for true news.

* The title of any news piece can be misleading. Only by reading the 'Title' along with the 'Text' can we obtain the whole idea about the news piece. Hence the next step would be to concatenate the 'Title' and 'Text' columns to obtain a comprehensive news article.

* The meta data provided is segregated, where fake and true news is given 2 seperate datasets. To create a robust model its better to provide the data containing both True and Fake news in a single file. Thats why the next step wud be to merge both datasets. 
## Removing Punctuations 
* The entire text is converted to lower case and with the help of REgular Expressions all the special characters, links, string punctuaions etc are removed.
## Removing Stop-words
* A stop word is a commonly used word (such as “the”, “a”, “an”, “in”) taht donot particularly contribute to the context of the sentence. We would not want these words to take up space in our database, or taking up the valuable processing time.

* We remove such wordsusing the NLTK library that has a list of stop-words in 16 different languages out of which we call the list of the English language.
## Stemming the text
* Stemming is a method of deriving root words from the inflected word. Here we extract the reviews and convert the words in reviews to their root word. We use the tool Porter Stemmer frorm the NLTK library to perform the stemming operation.
## One-hot encoding for Embedding layers with Padding
* We have to first set the vocabulary size to give a precedence for encoding the embedding layers. What one-hot encoding does, is it gives the words in the sentences an index value from the vocabulary size. Then those index values will be represented in the form of vectors in the embedding layers.
* To ensure that all the sentences provided to our LSTM model are of the same size,we consider a sentence length of 5000 and perform 'pre'padding. This inserts 'zeros' before the sentence so that the total length of the sentence reaches 5000.
## Creation and fitting of LSTM model
* An LSTM model with 100 neurons, a dropout rate of 30 % and a dense layer with sigmoid as the activation function was built and trained on the data for 10 epochs.
* The accuracy of the prediction was calculated at 96% while the prescision value obtained from the 	confusion matrix was 98%.
