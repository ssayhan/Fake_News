# Group_Project_Fake_News

### Group
 - Amanda Goguen
 - Salih Ayhan
 - Anthony Marquez
 - Kevin Whitiak

## Project Overview

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

In the end we swtiched from SciKitLearn to Spark-NLP which is a library created by John Snow Labs for preforming efficient natural language processing tasking using Spark. We decided to use this because it it was something we learned brefly in a preveous moduel and learning it can improve our skills. but also it is made for decifering words and so far it does it well with a 94 %. It also has a whole pipe line which include removing stop words which helps alot. It also is used for huge data which means this data set could be scaled and still produce results. Its not by all means perfect. Transformation code is a little clunky and manipulation is not as easy as pandas(could be a personal oppinon). You need to use it on google colab (good and bad thing). 

### Description of preliminary data preprocessing
* Data went through many transformations when trying to make it work with pyspark nlp pipeline. One being having it actually reading it correctly because the many tabs, enters and commas in it that are miss read as escape and delimiter value. After which we finally go into the pipeline which includes: 
   * tokenizing the data : which splits the strings into a list of words
   * removing SW: Removing stop words that really dont have any meaning to the thext it self 
   * Hashing : turns the code into a matrix that holds the occurrence counts
   * IDF: idf is a vector that fix a huge underlying problem of non meaningfull words that appear many times within our text 
   * vectorAssember
 * after which we split the data in training and testing data using pysparks code : randomSplit([0.7, 0.3], 21)
 * train the data and fit it 
 * and test it to see our accuracy
* So far we have a 94% accuracy
### Description of preliminary feature
 * befor i orginaly i had 93 befor i had the mashine learning also look at thet text as well
 * 94 % is good but not perfect. Word Bias would be important to look at fallowing through. with out research ive created my own code that would make a confusion matrix given a word. doing so showws if the word were wrong guessing it was fake news when it reality it should have been real and vise versa. seeing this can give us a better understanding of each value
### Conclussion
 * there is still much to do. starting this week i wanto try removing data with words that may confuse the matrix. I also want to try replacing None( our word we used to replace N/A) with another word that might not pop up as much cause this could create bias as well. 
 
 #### Problems with code
 * The only bugs that can really effect the code is the data it self. It needs to be cleaned. 
  * Tabs and enters have to be removed in pandas. 
  * Nan and empy cells need to be replaced. 
 * Well trying my own way of checking bias it was found that removing the word complelty only made the percentage lower. 
=======
#### Group Project Fake News



