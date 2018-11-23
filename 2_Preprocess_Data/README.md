# SMART EMAIL CLASSIFIER

## Preprocess Data
The goal of this notebook is to preprocess the data.



## Running the notebook

The code can be run by running all the cells in the notebook. 

As input, one has to provide with the input and output filenames, the number of emails to be processed (if not, all of them), if the preprocessing is restricted to the 1-1 emails and if the emails are going to be processed by area. Area is the group inside the company where the employees work (i.e., management, finances, legal, HR...).

```
    infile = '../data/ingest/all/emails.csv'
    outfile = "../data/preprocessed/preprocessed_pos.csv"
    n_sample = 70000     #number of random emails to preprocess, select a number if only a sample is desired
#     n_sample = None    #if this line is uncommented, all the emails would be processed
    restriction=True     # set True if we want to restrict the analysis to 1-1 emails that are not fwd or reply
    restriction_by_area=False   # set True if the 1-1 emails are restricted to ENRON emails and processed by area



```
