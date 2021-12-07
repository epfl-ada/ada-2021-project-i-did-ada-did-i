 # ADA Project - News source quoting style

## **Abstract :** 
Using the Quotebank dataset, we were initially interested in how different social factors influenced the language used by people when talking to the press. However, we reasoned that these quotes, although coming from their original speaker, are not necessarily representative of the speakers themselves, but rather of the news source using them. Indeed, it is the news source that chooses how, and whether, to quote someone. For instance, two different news outlets could quote the same speech very differently, one quoting the long flowery passages and the other going for punchy snippets. Therefore the question we would like to answer is: How do different news outlets choose the quotes they use, looking at quote length, word complexity, positivity, and speaker information such as job title, education, sex, and age. 


## **Research Questions :**

Our main research question is:
__How do different news outlets choose the quotes they use, looking at quote length, the complexity of words, positivity, and speaker information such as job title, education, and gender.__

This is a broad research question that will give us information on a multitude of websites. To show the relevance of this question, we thought of interesting ways to analyze the data it will generate. The general idea is to group websites according to different factors (ie. political views, target age range, age of the news outlet, etc.) and see if correlations emerge in the way they quote. Here is a tentative and non-exhaustive question list we would like to look at:

* Does the quotation style vary over time (for the whole dataset or subsets)? We could for example think that quotes are generally becoming shorter in news sites to adapt to new media (i.e. Twitter) being very concise. 
* Is there a significant difference in the way Republican and Democrat-leaning news outlets quote (looking at predefined news outlets)? We could look at clustering for all the quote parameters and each parameter separately.

Additionally, we would like to give our data the opportunity to shine by itself. Instead of looking for a correlation according to a predetermined grouping of news sources, we’ll also cluster them according to the quote parameters we mentioned and then try to interpret the results. This will allow new, potentially unexpected, proximity between websites to emerge from the data. Finding a known grouping of news sites would serve as a validation of this process.


Here are our old potential research questions, in case something needs to be adjusted with the one we chose. They all had the same issue of wanting to look at the language of ‘quotee’ without taking into account the choice of the ‘quoter’.

1. How do social factors such as job, education level, age, etc. influence the language used by people when they talk to the press?
2. How does the language used when talking to the press influence your popularity?
3. What is the vocabulary of different job titles / genders / age groups when they speak to the press? How do these vocabularies evolve over time?
4. How do standard vocabularies of different job titles / genders / age groups compare to the vocabularies used in these contexts / by these people when talking to the press?
5. Is there a link between the quality/length/positivity of a quote and the number of occurrences?



## **Additional datasets :**

**Wikidata**: get the speaker’s QID (warning, can have multiple QIDs) from the file provided along with Quotebank and then extract speaker data. 

**Cambridge Dictionary**: want to extract the CEFR word level (A1-C2) for all the words within the quote. The API is not open access, so we are using web page scraping. Not every word has a rating, we’ll use stemming and lemmatization to mitigate this problem (plural and conjugated forms do not have a CEFR level). Also, we might have to lower the request rate. Otherwise, we might be taken for a bot and blocked. We are not sure of the possible rate of request yet. 

## **Methods :**

We’ll focus most of our analysis on quotes that have a speaker with a unique QID. We’ll then extract the speaker’s information from the provided Wikidata files. We’ll group the quotes by news source (domain name in the URL). For each quote, we’ll compute length and assign a positivity score (nltk library). The quotes will be tokenized and those tokens will be preprocessed by removing stop words & punctuation, stemming, lemmenizing, etc. We’ll assess the complexity of each token using the CEFR word-level we will get from the Cambridge dictionary website data scraping.

## **Tentative timeline :**
Milestone 2: Data exploration, formulation of data (pre)processing pipeline, and most of the data preprocessing

Until 26/11: Solving homework 2

Week of the 29/11: Finishing data preprocessing: scaling up the pipeline described in methods

Week of the 06/12: SAINT NICOLAS: run the analysis and have a first draft of the website

Week of the 13/12: Finish the analysis and the data story


## **Team Organization**

Iris: preliminary data analysis, data preprocessing, website

Théo: Readme, data story creation, data visualization

Quentin: Cambridge and Wikidata data extraction, website

Jocelyn: Data exploration, grouping quotes by news source, positivity analysis (nltk)


 ## **Analysis Pipeline**
 1. Analysis of quotes per year getting averages for length, sentiment and positivity (Nationality=US, Year_by_year=1)
 
     a) All websites together: has the overall quoting style changed between 2015 and 2020?
         --> Do a graph over time, plotting average of all 3 parameters (separately or on same graph if it's doable to add multiple y axis label
         
     b) Grouping for political orientation of the news site: Is there a difference in the quoting style of left&right-leaning websites and has that difference evolved between 2015 and 2020? 
         --> 1 graph per parameter, do the graphs over time showing the averages for the 2 categories (left/right) in different colors (overlapping barplot, similar to homeworks)
         --> Look at what looks better, merging (left=left+center-left) or using only the extremes (left=left)
         
     c) Compare political orientation of speakers (%democrat,republican, neutral) in websites of different political orientation and it's evolution over time: Do left websites quote left speakers more, and vise versa (correlation) ? Are left or right leaning websites more prone to equally quoting speakers from all political orientation?   
         --> Maybe first do political orientation of speakers independent of website orientation (just to see if overall more democrat or republican are quoted)
         --> Graphs over time of % of speakers's political leaning (1 graph per website political orientation): Lines of different color for democrat speakers, republican and neutral in each graph (might remove neutral is we want, and readjust % so that republican + democrat = 100%)
         
       
         
 2. Compare left, right and center website by taking only a few manually selected high traffic websites (because way more center-left), and pooling all the years. 
     
     a) Compare length, sentiment and positivity: left more positive and right more negative?
         --> Repeating what we did earlier but just to check that our selection of website didn't fuck things up 
         --> Do a graph
     
     b) Look at impact of the website's political orientation on how they report on speakers based on the speakers' political orientation: Will a left website take shorter and more negative quotes for right speakers and vice versa?
         --> graph?
         
 3. All years pooled
     
     a) Grouping by factual reporting (factual_reporting): Do websites with higher factual reporting rating use longer and more neutral quotes?
         --> Barplot, x axis: factual reporting , y axis = average for length/sentiment/positivity (so do 3 graphs I guess)
         
     b) Correlation of factual reporting and political leaning of websites: Are right/left leaning websites more factualy accurate?
         --> graph: x=website political leaning, y=factual_reporting
         
     c) Correlation between factual reporting and websites ratio of speakers from their own orientation and from the oposite orientation: Are websites that quote more speakers from opposite political orientation more factually accurate? (can this be used as an indicator of factual accuracy?)
         --> Graph: nuage de poitn ou qqch du genre x= ratio of speakers (same political orientation as the journal)/(different political orientation as journal) continuous axis from 0 to 100%, y = factual reporting (categorical, ordered)
             (on pourrait mettre les websites avec différentes orientation politiques de différentes couleurs
             
     d) PCA?
     
