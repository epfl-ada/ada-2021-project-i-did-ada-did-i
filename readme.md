# ADA Project - News source quoting style

## **Abstract :** 
Using the Quotebank dataset, we were initially interested in how different social factors influenced the language used by people when talking to the press. However, we reasoned that these quotes, although coming from their original speaker, are not necessarily representative of the speakers themselves, but rather of the news source using it. Indeed, it is the news source that chooses how, and whether, to quote someone. For instance, two different news outlets could quote the same speech very differently, one quoting the long flowery passages and the other going for punchy snippets. Therefore the question we would like to answer is: How do different news outlets choose the quotes they use, looking at quote length, word complexity, positivity and speaker information such as job title, education, sex and age. 


## **Research Questions :**

Our main research question is:
**How do different news outlets choose the quotes they use, looking at quote length, complexity of words, positivity and speaker information such as job title, education and gender. **

This is a broad research question that will give us information on a multitude of websites. To show the relevance of this question, we thought of interesting ways to analyze the data it will generate. The general idea is to group websites according to different factors (ie. political views, target age range, age of the news outlet etc.) and see if correlations emerge in the way they quote. Here is a tentative and non-exhaustive question list we would like to look at:

* Does the quotation style vary over time (for the whole dataset or subsets)? We could for example think that quotes are generally becoming shorter in news sites to adapt to new medias (ie twitter) being very concise
* Is there a significant difference in the way republican and Democrat leaning news outlets quote (looking at predefined news outlets) ? We could look at clustering for all the quote parameters and for each parameter separately.

Additionally, we would like to give our data the opportunity to shine by itself. Instead of looking for a correlation according to predetermined grouping of news sources, we’ll also cluster them according to the quote parameters we mentioned and then try to interpret the results. This will allow new, potentially unexpected, proximity between websites to emerge from the data. Finding known grouping of news sites would serve as a validation of this process.


Here are our old potential research questions, in case something needs to be adjusted with the one we chose. They all had the same issue of wanting to look at the language of ‘quotee’ without taking into account the choice of the ‘quoter’.

1. How social factors such as job, education level, age etc. influence the language used by people when they talk to the press ?
2. How does the language used when talking to the press influence your popularity?
3. What is the vocabulary of different job titles / genders / age groups when they speak to the press ? How do these vocabularies evolve over time?
4. How do standard vocabularies of different job titles / genders / age groups compare to the vocabularies used in these contexts / by these people when talking to the press?
5. Is there a link between the quality/length/positivity of a quote and the number of occurrences ?



## **Additional datasets :**

**Wikidata**: get the speaker’s QID (warning, can have multiple QIDs) from the file provided along with Quotebank and then extract speaker data. We have not decided yet whether to use the data dump or wikidata’s API

**Cambridge Dictionary**: want to extract the CEFR word level (A1-C2) for all the words within the quote. The API is not open access, so we are using web page scraping. Not every word has a rating, we’ll use stemming and lemmatization to mitigate this problem (plural and conjugated forms do not have CEFR level). Also we might have to lower the request rate not to be taken for a bot, we are not sure of the possible rate of request

## **Methods :**

We’ll focus most of our analysis on quotes that have a speaker with a unique QID. We’ll then extract the speaker’s information from the provided wikidata files. We’ll group the quotes by news source (domain name in the url). For each quote, we’ll compute length and assign a positivity score (nltk library). The quotes will be tokenized and those tokens will be preprocessed by removing stop words & punctuation, stemming, lemmenizing etc. We’ll assess the complexity of each token using the CEFR word level we will get from the Cambridge dictionary website data scraping.

## **Tentative timeline :**
Milestone 2: Data exploration, formulation of data (pre)processing pipeline and most of data preprocessing

Until 26/11: Solving homework 2

Week of the 29/11: Finishing data preprocessing: scaling up the pipeline described in methods

Week of the 06/12: SAINT NICOLAS: run the analysis and have a first draft of the website

Week of the 13/12: Finish the analysis and the data story


## **Team Organization**

Iris: preliminary data analysis, data preprocessing, website

Théo: Readme, data story creation, data visualisation

Quentin: Cambridge and wikidata data extraction, website

Jocelyn: Data exploration, grouping quotes by news source, positivity analysis (nltk)
