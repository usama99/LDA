# Latent Dirichlet Allocation
# Step 1: Load the dataset
As you can see that there are some distinct themes in the news categories like sports, religion, science, technology, politics, etc.
# Step 2: Data Preprocessing
Lemmatizer Example
Stemmer Example
# Step 3: Bag of words on the dataset
# Step 4: Running LDA using Bag of Words
We are going for 10 topics in the document corpus.

** We will be running LDA using all CPU cores to parallelize and speed up model training.**

Some of the parameters we will be tweaking are:

num_topics is the number of requested latent topics to be extracted from the training corpus.

id2word is a mapping from word ids (integers) to words (strings). It is used to determine the vocabulary size, as well as for debugging and topic printing.

workers is the number of extra processes to use for parallelization. Uses all available cores by default.

alpha and eta are hyperparameters that affect sparsity of the document-topic (theta) and topic-word (lambda) distributions. We will let these be the default values for now(default value is 1/num_topics)

Alpha is the per document topic distribution.

High alpha: Every document has a mixture of all topics(documents appear similar to each other).
Low alpha: Every document has a mixture of very few topics
Eta is the per topic word distribution.

High eta: Each topic has a mixture of most words(topics appear similar to each other).
Low eta: Each topic has a mixture of few words.
** passes ** is the number of training passes through the corpus. For example, if the training corpus has 50,000 documents, chunksize is 10,000, passes is 2, then online training is done in 10 updates:

#1 documents 0-9,999
#2 documents 10,000-19,999
#3 documents 20,000-29,999
#4 documents 30,000-39,999
#5 documents 40,000-49,999
#6 documents 0-9,999
#7 documents 10,000-19,999
#8 documents 20,000-29,999
#9 documents 30,000-39,999
#10 documents 40,000-49,999
Classification of the topics
Using the words in each topic and their corresponding weights, what categories were you able to infer?

0: Graphics Cards
1: Religion
2: Space
3: Politics
4: Gun Violence
5: Technology
6: Sports
7: Encryption
# Step 6: Testing model on unseen document
