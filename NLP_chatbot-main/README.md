# NLP_chatbot
This work implements text preprocessing, BoW and TF-IDF vectorization, and similarity calculation to enable a chatbot-like interaction by finding the most similar questions and returning their corresponding answers.
Text Preprocessing:

The code includes a function called text_normalization that performs various text normalization tasks such as converting text to lowercase, removing special characters, tokenizing the text, and lemmatizing the tokens using WordNet lemmatizer.
The nltk library is used for text preprocessing tasks, and the required resources (such as WordNet) are downloaded using nltk.download function.
Bag-of-Words (BoW) Representation:

The code uses the CountVectorizer class from the sklearn.feature_extraction.text module to convert the preprocessed text data into a numerical representation known as the Bag-of-Words.
The fit_transform method of CountVectorizer is applied to the preprocessed questions in the dataframe to obtain the BoW representation as a matrix.
The feature names (unique words) in the BoW representation are extracted using the get_feature_names_out method.
Cosine Similarity Calculation (BoW):

The cosine similarity between the BoW representation of the questions in the dataframe and a given input question is calculated using the pairwise_distances function from the sklearn.metrics.pairwise module.
The similarity values are obtained as a matrix, and the maximum similarity value corresponds to the most similar question.
The index of the most similar question is used to retrieve the corresponding answer from the dataframe.
TF-IDF (Term Frequency-Inverse Document Frequency) Representation:

The code uses the TfidfVectorizer class from the sklearn.feature_extraction.text module to convert the preprocessed text data into a TF-IDF representation.
The fit_transform method of TfidfVectorizer is applied to the preprocessed questions in the dataframe to obtain the TF-IDF representation as a matrix.
Cosine Similarity Calculation (TF-IDF):

The cosine similarity between the TF-IDF representation of the questions in the dataframe and a given input question is calculated using the pairwise_distances function with the metric set to 'cosine'.
The similarity values are obtained as a matrix, and the maximum similarity value corresponds to the most similar question.
The index of the most similar question is used to retrieve the corresponding answer from the dataframe.
Chat Functions:

Two chat functions, namely chat_bow and chat_tfidf, are defined to provide responses based on user queries.
These functions preprocess the input text, apply the respective vectorization technique (BoW or TF-IDF), calculate cosine similarity, and return the most relevant answer from the dataframe.
