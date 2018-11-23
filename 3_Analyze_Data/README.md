# SMART EMAIL CLASSIFIER

## Analyze Data
The goal of this notebook is to analyze the data and plot the results. The analysis algorithms are unsupervised ML.


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
