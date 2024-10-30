# 5003_enron_emails_nlper

To begin, run the code in the file ***Data_Preprocessing_Visu.ipynb***, which handles downloading and preprocessing for the ***Enron Email dataset***. Once the dataset is cleaned and preprocessed, you can proceed with either the ***ML_NLP_classification.ipynb*** or ***Sentiment_Analysis.ipynb*** file. These files address different tasks, performing anomaly detection and sentiment analysis separately.

## Data_Preprocessing_Visu.ipynb
### Database download

In order to download the database, run the first cell in jupter notebook, the database will download
```python
import requests
url = "https://www.cs.cmu.edu/~./enron/enron_mail_20150507.tar.gz"
filename = "../enron_mail_20150507.tar.gz"
with open(filename, "wb") as f:
    r = requests.get(url)
    f.write(r.content)
```
and unzip automatically.
```python
print("Unzipping Enron dataset (This may take a while)")
import tarfile
tfile = tarfile.open("../enron_mail_20150507.tar.gz")
tfile.extractall(".")
tfile.close()
```
After downloading the database, it will show "You're ready to go!", which named "maildir".

You can make this cell to command after you download the database successfully.

### Convert Enron database to .csv file

Read files' content in maildir files, and create a .csv file named "enron_emails.csv".

The .csv file will contain two columns -- "file", "message"

1. file: store the directly name of file
2. message: store the content of the email that we read from file

After run the cell to read the files and write into .csv file, a "enron_emails.csv" will be autogenerated under the same folder of our raw database.

**_The "enron_emails.csv" file will be automatically saved into parent folder_**

### Data Preprocessing

After data cleaning and preprocessing, it will generate a new csv file called "enron_emails_cleaned.csv", both ML_NLP_classification and Sentiment Analysis have to first import this cleaned enron email datasets into code then proceeded to next procedure.

## Data Visualization 

All Graphs are saved in ***Graphs for Data Visualization*** file as part of results of our project, for easy arranging. 

## File Structure:

<img width="350" alt="image" src="https://github.com/user-attachments/assets/b70d879b-1e89-4a57-a8a7-d2daa7873403">



