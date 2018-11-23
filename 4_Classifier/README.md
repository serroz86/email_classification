# SMART EMAIL CLASSIFIER

## Build model classifier 
The goal of this notebook is to create the model that classifies the data. It uses wikipedia as training dataset for supervised ML models.

## Prepare the training dataset

Our email classifier would classify our emails in these categories: business, leisure, news, personal, research and spam.

We are going to look for datasets that will be our training input. For that, we use two different sources: wikipedia and a spam dataset (http://www.dt.fee.unicamp.br/~tiago/smsspamcollection/).

The inputs are two files:

- 'Pages_Names_Sample.txt', which contains these words (each one in one line): Social Media, Business, Job, Sports, Email Spam, Entertainment, Science, Politics, Trading. These will be the input for the wikipedia search
- 'spam_dataset.csv', a cleaned version of the source, downloaded from http://www.dt.fee.unicamp.br/~tiago/smsspamcollection/smsSpamCollection.arff

Both files should be in '../data/databases'

## Running the models
To choose the word embeddings (using word2vec), the following file should be present: '../data/GoogleNews-vectors-negative300.bin.gz'

## Running the notebook

The code can be run by running all the cells in the notebook. 

The main function start with options that are set to True/False. We select whether we want to prepare the database (i.e., download the wikipedia articles of the selected groups), train ad test the model, or check the output with some examples of articles and emails.

The following word processing can be chosen: TF-IDF,word2vec 
The following models can be chosen to be run: Naive Bayes, SVM and Logistic Regression.

```
    prepare_database=False
    train_model=True
    check_result=True
```
```

        vectors='tfidf'     # choose from: tfidf,word2vec 
        classifier = 'linearSVC' # choose from: nb,linearSVC,logit
        run_models(vectors,classifier)


```
