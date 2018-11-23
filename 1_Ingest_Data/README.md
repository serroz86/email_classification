# SMART EMAIL CLASSIFIER

# Ingest Data
In this notebook I am going to explore and ingest the ENRON email dataset.

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
