# Sentiment-Analysis-of-Twitter-Data
The Sentiment Analysis on twitter data. The dataset has comma separated values with
series of columns about the tweet’s text, text sentiment, username and hashtag's etc. To
achieve our goal, the first thing is doing the preprocessing of data after loading the dataset.
I have done the preprocessing on the ‘text’ column of the data frame. Pre-processing
techniques include removal of hyperlinks (‘https, http, www, /’), any video references,
hashtag’s, HTML reference characters, non-letter characters, real names, stop word and
punctuation removals. This entire preprocessing is done after conversion of entire text into
lowercase strings. For this preprocessing I used ‘re’ and ‘string’ libraries from python. After
preprocessing, the dataset was split into training and testing sets. 80% of the data was
used for training, and 20% for testing. To ensure a balanced distribution of sentiment
classes in both sets, a stratified split was performed based on the sentiment labels.
Coming to the part of Sentiment analysis, there are four techniques to be performed which
includes Bag of words, TF-IDF embedded with Chi-square. 

The Bow model was applied to convert the text into a vectorized form, where each word corresponds to a feature, and
its frequency in the document is the value. Term Frequency-Inverse Document
Frequency (TF-IDF) was applied to weigh words based on their frequency across all
documents. The rare words gain higher weight while common words gain lower weight. The
top 100 features were selected using the chi-square test and used for both the models to
retain only the most informative words, reducing feature space size and improving
efficiency. Then, the next part pre-trained Word2Vec embeddings (Google’s Word2Vec,
trained on the Google News dataset) were used to represent each word as a 300-
dimensional vector. For each tweet, the word vectors of all words were averaged to form a
single 300-dimensional vector representing the entire tweet. 

These vectors were then fed into the SVM model for classification. Pre-trained GloVe embeddings (Global Vectors for
Word Representation), trained on Wikipedia and Giga word 5, were also used. The process
was similar to Word2Vec, where each tweet was represented as the average of its word
vectors. These GloVe vectors were used as features for the SVM model. The bonus part
includes sentence embedding. The Universal Sentence Encoder (USE) was applied to
create high-dimensional sentence embeddings. USE captures the semantic meaning of
the entire sentence, making it more advanced than word-level embeddings like Word2Vec or GloVe. 
The sentence embeddings were passed into the SVM classifier for sentiment prediction.
