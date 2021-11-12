# ADA Project - Quotebank analysis

## **Abstract :** 
Using the Quotebank dataset, we were initially interested in how different social factors influenced the language used by people when talking to the press. However, we reasoned that these quotes, although coming from their original speaker, are not necessarily representative of the speakers themselves, but rather of the news source using it. Indeed, it is the news source that chooses how, and whether, to quote someone. For instance, two different news outlets could quote the same speech very differently, one quoting the long flowery passages and the other going for punchy snippets. Therefore the question we would like to answer is: How do different news outlets choose the quotes they use, and how has it evolved over time ? We will be looking at quote length, word complexity, positivity and speaker information such as job title, education, sex and age. 



## **Research Questions :**

Our main research question is:
How do different news outlets choose the quotes they use, and how has it evolved over time? We will be looking at quote length, complexity of words, positivity and speaker information such as job title, education and gender. 

This is a broad research question that will give us information on a multitude of websites. To show the relevance of this question, we thought of interesting ways to analyze the data it will generate. The general idea is to group websites according to different factors (ie. political views, target age range, age of the news outlet etc) and see if correlations emerge in the way they quote. Here are a few (tentative) questions to answer:

Are quotes generally becoming shorter in news sites? This could be in relation with twitter, which can act as an alternative news source while being extremely concise.
Is there a significant difference in the way republican and Democrat leaning news outlets quote (looking at predefined news outlets) ?


Here are our old potential research questions, in case something needs to be adjusted with the one we chose. They all had the same issue of wanting to look at the language of ‘quotee’ without taking into account the choice of the ‘quoter’.

1. How social factors such as job, education level, age etc. influence the language used by people when they talk to the press ?
2. How does the language used when talking to the press influence your popularity?
3. What is the vocabulary of different job titles / genders / age groups when they speak to the press ? How do these vocabularies evolve over time?
4. How do standard vocabularies of different job titles / genders / age groups compare to the vocabularies used in these contexts / by these people when talking to the press?
5. Is there a link between the quality/length/positivity of a quote and the number of occurrences ?



## **Additional datasets :**

Wikidata: get the speakers attribute from the file provided along with Quotebank
Cambridge Dictionary: want to extract the complexity value (A1-C2) for all the words within the quote

## **Methods :**

First we get each speaker’s vocabulary (series of words) and assign an importance score to each word with TF-IDF/look and assess its complexity with Cambridge dictionary dataset to dismiss non-useful words. Then we use wikidata to get data on the speakers to classify them by job title (+ education level, area of interest etc). We create a specific vocabulary for each job title by looking at correlation. Each category will have a set of words associated with it (potentially weighted) and words can be in multiple categories.

### Data exploration

* Number of quotes per speaker -> keep only those of speakers with at least X quotes?
* Number of quotes per year and/or month -> identify times where the data becomes very unreliable
* Length of quotes -> long quotes have different statistics than short quotes, e.g. contain on average more complex/relevant words
* Check validity of quotes
	* Do the quotes have any meaning/sense? -> no idea if we can check that at all
* Number of quotes per news outlet source
* Which information is available from WikiData

### Data preparation

* Clean data according to data exploration results
* Get each quote’s vocabulary
	* Tokenize (keep composed words as a single token, e.g. “United States”)
	* Remove punctuation and stopwords
	* Stem words
	* Pool by  news website for each year
* Assign importance score to each word
	* Complexity given by Cambridge Dictionary
	* log2 (group of interest +E  / ref group+E)
* Create a corpus for each news outlet
	* Classify quotes by news outlet 
		* Each quote can belong to multiple news outlet

### Data analysis
To be determined based on analysis, rough outline:

Correlation of the use of the word by the people of this category
	* Find the words used mainly by given category and not so much by other categories
	* Vocabularies may overlap
	* Words of the vocabs may be weighted


### Data visualisation and answering question

## **Proposed timeline :**
Data exploration: Milestone 2
Data preparation: Milestone 2
Data analysis: December 10th
Data visualisation & answering questions: December 24th

## **Team Organization Milestone 2 :**
wikidata
trier par news outlet - jocelyn
sentiment analysis
readme - théo
clean compound words analysis -> comment out NER, put collocations to analysis part (create analysis part) - Iris

Iris: preliminary data analysis, data preparation
Théo: Data story creation, ReadMe writing
Quentin: Data scraping, Cambridge and wikidata data extraction
Jocelyn: 

