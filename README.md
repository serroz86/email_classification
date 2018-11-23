# SMART EMAIL CLASSIFIER

Email topic classification using unsupervised and supervised machine learning algorithms.

In this repo, we find notebooks that will perform topic classification in emails, in other words, classifying our emails into the following categories: spam, entertainment, sport, business, personal.

For that, we use two approaches:

- Unsupervised machine learning: 

We use the largest email database available from the ENRON company:

https://enrondata.readthedocs.io/en/latest/data/calo-enron-email-dataset/

To classify these emails, we use Latent Dirichlet Allocation (LDA)  and K-means algorithms to discover hidden topics from the articles.

- Supervised machine learning:

We use wikipedia data to train our models using several machine learning algorithms (SVM, logistic regression, Naive Bayes) using different approaches (bag of words/BOW, TF-IDF, word embeddings/word2vec).


The jupyter notebooks are run using python 3.

The requirements to run the notebooks are in the file prerequisites.txt



The project is divided in four folders:

# 1) Data ingestion

This folder contains the notebook which ingests the data of the emails from the ENRON company (as example). 


## Explore the ENRON data structure

- We check how the emails are distributed in folders etc.

- We see that there are 150 folders (each one corresponding to one person).

- We see that inside the folder 'stockley-c', there is a folder called 'Christian Stockley", so we manually move all the subfolders 'stockley-c'

- We also see that in the ingestion, we should not include the hidden files created by MAC ".DS_Store"

- The folder (tree) structure is different for each person (i.e., different depths per user).

- We take into account the coding, which is 'ISO-8859-15'


## Running the notebook

The main function start with options that are set to True/False. We select whether we want to check an email, read the csv from the splitted database or directly ingest the data. So once we set to "True" the parts of the code that we want, the code can be run by running all the cells in the notebook.    

```
    check_first_email=True
    loading_splitted=False
    ingest_data=False
    check_result=False

```


# 2) Data preprocessing

The goal of this notebook is to preprocess the data.



## Running the notebook

The code can be run by running all the cells in the notebook. 

As input, one has to provide with the input and output filenames, the number of emails to be processed (if not, all of them), if the preprocessing is restricted to the 1-1 emails and if the emails are going to be processed by area. Area is the group inside the company where the employees work (i.e., management, finances, legal, HR...).

```
    infile = 'email_classification/data/ingest/all/emails.csv'
    outfile = "email_classification/data/preprocessed/preprocessed_pos.csv"
    n_sample = 70000     #number of random emails to preprocess, select a number if only a sample is desired
#     n_sample = None    #if this line is uncommented, all the emails would be processed
    restriction=True     # set True if we want to restrict the analysis to 1-1 emails that are not fwd or reply
    restriction_by_area=False   # set True if the 1-1 emails are restricted to ENRON emails and processed by area



```

# 3) Data analysis

This notebook has the unsupervised machine learning algorithm that classifies the emails in groups. Also can use wikipedia articles as input.

The goal of this notebook is to analyze the data and plot the results. The analysis algorithms are unsupervised ML. The result can be plotted using pyLDAvis https://pyldavis.readthedocs.io/en/latest/ and wordclouds https://www.wordclouds.com/


## Running the notebook

The code can be run by running all the cells in the notebook. 

The main function start with options that are set to True/False. We select whether we want to restrict the analysis to areas of the employees, use LDA and plot the results, run TFIDF +K-means and plot the results, or analyze the data with word embeddings (using word2vec). As input, the number of clusters can also be set.


```
    by_area = False
    run_LDA = False
    load_LDA = False
    plot_LDA = False
    run_TFIDF = False
    run_embeddings = True
    plot_Kmeans = True    
    num_groups = 9    # number of clusters for the unsupervised clustering


```


# 4) Build the model classifier

This notebook contains the model classifier with the supervised machine learning approach.

The goal of this notebook is to create the model that classifies the data. It uses wikipedia as training dataset for supervised ML models.

## Prepare the training dataset

Our email classifier would classify our emails in these categories: business, leisure, news, personal, research and spam.

We are going to look for datasets that will be our training input. For that, we use two different sources: wikipedia and a spam dataset (http://www.dt.fee.unicamp.br/~tiago/smsspamcollection/).

The inputs are two files:

- 'Pages_Names_Sample.txt', which contains these words (each one in one line): Social Media, Business, Job, Sports, Email Spam, Entertainment, Science, Politics, Trading. These will be the input for the wikipedia search
- 'spam_dataset.csv', a cleaned version of the source, downloaded from http://www.dt.fee.unicamp.br/~tiago/smsspamcollection/smsSpamCollection.arff

Both files are by default in 'email_classification/data/databases'. 

## Running the models
To choose the word embeddings (using word2vec), the following file should be present: 'email_classification/data/GoogleNews-vectors-negative300.bin.gz'

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

