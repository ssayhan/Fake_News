# Group_Project_Fake_News

### Group
 - Amanda Goguen
 - Salih Ayhan
 - Anthony Marquez
 - Kevin Whitiak

## Project OVerview

With the advent of the internet, and more importantly social media, fake news and missinformation has been on the rise and has been plaguing our society.  Some is so well hidden and advertised, it may be dfficult to spot if a source is fake news or not.  The purpose of this project is to create a Machine Learning model to detect fake news and missinformation.  We will be using Natural Language processing and Bianary Classification Evaluators on our dataset to help with training and testing of the Model.

# Technologies Used
## Data Cleaning and Analysis
Pandas will be used to clean the data and perform an exploratory analysis. Further analysis will be completed using Python and Machine Learning algorithms.

### Dependencies
•	python 3.x
•	nltk
•	numpy
•	sklearn
•	matplotlib
•	wordclouds
•	scipy
•	pandas
•	pyspark


### Dataset

The dataset usedi in this project is the Kaggle Dataset. It is including two types or article fake(0) and real(1) news. Dataset including only one file and more tha 70.000 artciles. Dataset contains the following information.

-	Title
-	Text
-	Label

## Approach

### Data preprocessing:

+ We started our journey with cleaning dataset. We replaced all “null’ values with ‘None’. 

+Then we moved stop words form our dataset with using ‘ stopwords’. After stopwords we recognize there are still words need to remove like ‘us’, ‘would’ etc. so we created custom stop words to remove them. To get better accuracy in ML.

**Stopwords**
<img width="1006" alt="stopwords" src="https://user-images.githubusercontent.com/77603561/187055919-159e7a47-1f9c-45b2-93d3-7b857f1c75ae.png">

**Custom stopwords**
<img width="1008" alt="custom stopwords" src="https://user-images.githubusercontent.com/77603561/187055924-8ce0784b-ae4d-4212-af65-7950be142049.png">

**Top ten words in title**

<img width="544" alt="top10 title" src="https://user-images.githubusercontent.com/77603561/187055940-b2d2d42d-3374-49d1-bf45-06332f121663.png">
    
**Top ten words in text**

<img width="649" alt="top10 text" src="https://user-images.githubusercontent.com/77603561/187055952-faa3123c-7830-4c3f-93cb-d9311b645135.png">

+ We created data frame which including 10 most common words in text columns with fake(0) and true(1) counting.

<img width="278" alt="fake true count" src="https://user-images.githubusercontent.com/77603561/187056363-330c445b-9c85-4c1d-abdb-a4f49160b9a7.png">


**BarH chart for most common words in text**
<img width="943" alt="Screen Shot 2022-08-27 at 1 54 08 AM" src="https://user-images.githubusercontent.com/77603561/187055993-9dbedb79-624c-4c50-9fda-671527b18e4f.png">

**Stacked chart for most common workds in text with 0(fake) and 1(true) count**
<img width="870" alt="Screen Shot 2022-08-27 at 1 54 15 AM" src="https://user-images.githubusercontent.com/77603561/187055996-40027a5e-983d-48bc-886d-d4f825f53f8b.png">


### Wordcloud Dataset

Wordcloud is the most frequent occurring words in the corpus to be shown.in wordcloud most common words appears larger font. As we see most frequent words in title and text.


<img width="957" alt="text" src="https://user-images.githubusercontent.com/77603561/187055987-60065027-69af-4f37-b958-4f5607ae6607.png">

<img width="969" alt="title" src="https://user-images.githubusercontent.com/77603561/187055988-359ac36e-3615-4753-8700-b4f624362b93.png">

## Database Storage
SQL is the database we intend to use, we used ORM and  SQLAlchemy library  on python to use some filters on our cleaned data set. We  used DB browser to stored our data.

<img width="1008" alt="Screen Shot 2022-08-27 at 10 13 14 PM" src="https://user-images.githubusercontent.com/77603561/187057181-b7e9a91a-2aea-456e-a926-a339f78afb6b.png">

<img width="1005" alt="Screen Shot 2022-08-27 at 10 13 27 PM" src="https://user-images.githubusercontent.com/77603561/187057185-a125f7d6-8e8f-4e18-9d15-8236ad5fbc1e.png">

<img width="1009" alt="Screen Shot 2022-08-27 at 10 14 49 PM" src="https://user-images.githubusercontent.com/77603561/187057188-69490864-02ff-4e15-a4ef-d5c6208e42bf.png">




## Machine Learning
SciKitLearn is the ML library we'll be using to create a classifier. Our training and testing setup is Natural Language processing and Bianary Classification Evaluators. 


