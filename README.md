# Group_Project_Fake_News

### Group
 - Amanda Goguen
 - Salih Ayhan
 - Anthony Marquez
 - Kevin Whitiak

## Project Overview

With the advent of the internet, and more importantly social media, fake news and misinformation has been on the rise and has been plaguing our society.  Some misinformation is so well hidden and advertised, it may be difficult to identify whether or not that source is reliable.  The purpose of this project is to create a Machine Learning model to detect fake news and misinformation. We will be using Natural Language processing and Bianary Classification Evaluators on our dataset to help with training and testing of the Model.

# Technologies Used
## Data Cleaning and Analysis
Pandas will be used to clean the data and perform an exploratory analysis. Further analysis will be completed using Python and Machine Learning algorithms.

### Dependencies
•	python 3.x
•	numpy
•	sklearn
•	matplotlib
•	wordclouds
•	scipy
•	pandas
•	pyspark
•	NLP
• BinaryClassification

### Dataset

The dataset used in this project is the Kaggle Dataset. The data contains two types or articles, fake(0) and real(1) news. The data we used includes only one dataset with more tha 70,000 artciles. The dataset contains the following information/columns:

-	Title
-	Text
-	Label

## Approach

### Data preprocessing:

+ We started our journey with cleaning the dataset. We replaced all “null’ values with ‘None’. 

+ Then, we moved stopwords form our dataset with using ‘ stopwords’. After removing the stopwords, we recognized that there were still words we needed to remove like ‘us’, ‘would’, etc., so we created custom stop words to remove them in order to get a higher accuracy in our Machine Learning Model.

**Stopwords**
<img width="1006" alt="stopwords" src="https://user-images.githubusercontent.com/77603561/187055919-159e7a47-1f9c-45b2-93d3-7b857f1c75ae.png">

**Custom stopwords**
<img width="1008" alt="custom stopwords" src="https://user-images.githubusercontent.com/77603561/187055924-8ce0784b-ae4d-4212-af65-7950be142049.png">

**Top ten words in title**

<img width="544" alt="top10 title" src="https://user-images.githubusercontent.com/77603561/187055940-b2d2d42d-3374-49d1-bf45-06332f121663.png">
    
**Top ten words in text**

<img width="649" alt="top10 text" src="https://user-images.githubusercontent.com/77603561/187055952-faa3123c-7830-4c3f-93cb-d9311b645135.png">

+ We created dataframe which includes the 10 most common words in the 'text' columns while tracking the fake(0) and true(1) labels.

<img width="278" alt="fake true count" src="https://user-images.githubusercontent.com/77603561/187056363-330c445b-9c85-4c1d-abdb-a4f49160b9a7.png">


**Bar chart for most common words in the 'text' column**
<img width="943" alt="Screen Shot 2022-08-27 at 1 54 08 AM" src="https://user-images.githubusercontent.com/77603561/187055993-9dbedb79-624c-4c50-9fda-671527b18e4f.png">

**Stacked chart for most common words in the 'text' with labels: 0(fake) and 1(true) count**
<img width="870" alt="Screen Shot 2022-08-27 at 1 54 15 AM" src="https://user-images.githubusercontent.com/77603561/187055996-40027a5e-983d-48bc-886d-d4f825f53f8b.png">


### Wordcloud Dataset

Wordcloud is the most frequent occurring words in the corpus to be shown. In wordcloud, the most common words appear in a larger font. The images below display the most common words found in both the 'title' and 'text' columns.


<img width="957" alt="text" src="https://user-images.githubusercontent.com/77603561/187055987-60065027-69af-4f37-b958-4f5607ae6607.png">

<img width="969" alt="title" src="https://user-images.githubusercontent.com/77603561/187055988-359ac36e-3615-4753-8700-b4f624362b93.png">

## Database Storage
SQL is the database we used for storage. We also used ORM and SQLAlchemy library in python to apply filters on our cleaned dataset. We used DB browser to store our data.

<img width="1008" alt="Screen Shot 2022-08-27 at 10 13 14 PM" src="https://user-images.githubusercontent.com/77603561/187057181-b7e9a91a-2aea-456e-a926-a339f78afb6b.png">

<img width="1005" alt="Screen Shot 2022-08-27 at 10 13 27 PM" src="https://user-images.githubusercontent.com/77603561/187057185-a125f7d6-8e8f-4e18-9d15-8236ad5fbc1e.png">

<img width="1009" alt="Screen Shot 2022-08-27 at 10 14 49 PM" src="https://user-images.githubusercontent.com/77603561/187057188-69490864-02ff-4e15-a4ef-d5c6208e42bf.png">




## Machine Learning

In the end we swtiched from SciKitLearn to Spark-NLP, which is a library created by John Snow Labs for preforming efficient natural language processing tasks using Spark. We decided to use this because it was something we learned briefly in a preveous module and we figured that if we dived deeper into the topic, we could improve our analytic skills. It is also made for decifering words and for our analysis, it did a good job, giving us an accuracy score of about 94 %. It also has a whole pipeline which includes removing stopwords which made our analysis easier. It is used for huge data, which means this dataset could be scaled and still produce results. Although Spark-NLP was very useful in most way, it is by no means without flaws. The transformation code is a little clunky and we personally found that manipulation was not as easy as pandas. Another potential limitation is that is must be used on google colab, which can be either a good or bad thing depending on the user. 

### Description of preliminary data preprocessing
* Our dataset went through many transformations when trying to make it work with pyspark nlp pipeline. One of the issues we fixed was having it read the content of the data correctly because the many tabs, enters and commas in it were misread as an escape and delimiter value. After we solved that issue, we finally went into the pipeline which includes: 
   * tokenizing the data : which splits the strings into a list of words
   * removing SW: Removing stop words that really dont have any meaning to the text itself 
   * Hashing : turns the code into a matrix that holds the occurrence counts
   * IDF: idf is a vector that fixes a huge underlying problem of nonmeaningful words that appear many times within our text 
   * vectorAssember
 * After which we split the data into training and testing data using pysparks code : randomSplit([0.7, 0.3], 21)
 * We trained the data and fit it 
 * We tested it to see our accuracy
* The highest accuracy we have achieved is a 94% 

### Description of preliminary feature
 * before I orginaly i had 93 befor i had the mashine learning also look at thet text as well
 * 94 % is good but not perfect. Word Bias would be important to look at fallowing through. with out research ive created my own code that would make a confusion matrix given a word. doing so showws if the word were wrong guessing it was fake news when it reality it should have been real and vise versa. seeing this can give us a better understanding of each value
 
### Conclusion
 * there is still much to do. starting this week i wanto try removing data with words that may confuse the matrix. I also want to try replacing None( our word we used to replace N/A) with another word that might not pop up as much cause this could create bias as well. 
 
 #### Problems with code
 * The only bugs that can really effect the code is the data it self. It needs to be cleaned. 
  * Tabs and enters have to be removed in pandas. 
  * Nan and empy cells need to be replaced. 
 * Well trying my own way of checking bias it was found that removing the word complelty only made the percentage lower. 
=======
#### Group Project Fake News



