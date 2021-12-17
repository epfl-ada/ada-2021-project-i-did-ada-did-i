 # ADA Project - News source quoting style

## Links to resources
**Website**: https://naevyys.github.io/Little-quotes-story/

**Google Drive containing files**: https://drive.google.com/drive/u/0/folders/11yDMWMrmvY3E3brx1rw3JUCIXX40vjGt 

## **Abstract :** 
Using the Quotebank dataset, we were initially interested in how different social factors influence the language used by people when talking to the press. However, we reasoned that these quotes, although coming from their original speaker, are not necessarily representative of the speakers themselves, but rather of the news source using them. Indeed, it is the news source that chooses how, and whether, to quote someone. For instance, two different news outlets could quote the same speech very differently, one quoting the long flowery passages and the other going for punchy snippets. These differences could implicitly change the way readers perceive the quoted speakers. Therefore the question we would like to answer is: How do different news outlets choose the quotes they use, looking at quote length, sentiment analysis (polarity score) and political party of the speaker. 


## **Research Questions :**

Our main research question is:
__How do different news outlets choose the quotes they use, looking at quote length, sentiment analysis (polarity score) and political party of the speaker?__

This is a broad research question that will give us information on a multitude of websites. To show the relevance of this question, we thought of interesting ways to analyze the data it will generate. The general idea is to group websites according to different factors (ie. political views, target age range, age of the news outlet, etc.) and see if correlations emerge in the way they quote. Here is a tentative and non-exhaustive question list we would like to look at:

* Does the quotation style vary over time (for the whole dataset or subsets)? We could for example think that quotes are generally becoming shorter in news sites to adapt to new media (i.e. Twitter) being very concise. 
* Is there a significant difference in the way Republican and Democrat-leaning news outlets quote (looking at predefined news outlets)? We could look at clustering for all the quote parameters and each parameter separately.

## **Additional datasets and sources of information :**

**[Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page)**: get the speaker’s QID (warning, can have multiple QIDs) from the file provided along with Quotebank and then extract speaker data.
**[Media Bias Check](https://mediabiasfactcheck.com/)**: Get additional information on the news outlets for our analyses.
 
## **Methods :**

  We start by evaluating which news outlets produce the most number of quotes. Based on the biggest news outlet, we select the most relevant news source for our analysis. We will define their political leaning plus factual reporting based on the website _https://mediabiasfactcheck.com/_. To the list we will also add: the nationality, and whether they are content creator or simply report others' content.

  From this list of top news outlets, we group the quotes by news source (domain name in the URL) and year. For each quote, we compute length and assign a positivity score (via nltk library).
  Still from this selection of relevant news sources, we select the most cited speakers. We extract their information from the provided Wikidata files and determine whether they are politician or not. Then we create three tops of Republican, Democrats and apolitical speakers. From these different tops we run the analysis described below. 


 ## **Analysis Pipeline**
 1. Analysis of quotes per year getting averages for length, sentiment and positivity (Nationality=US, Year_by_year=1, Content_creator=1)
 
     a) All websites together: has the overall quoting style changed between 2015 and 2020?
         
     b) Grouping for political orientation of the news site: Is there a difference in the quoting style of left & right-leaning websites and has that difference evolved between 2015 and 2020? 
         
     c) Compare political orientation of speakers (democrat, republican, neutral) in websites of different political orientation and its evolution over time: Do left websites quote left speakers more, and vice versa (correlation) ? Are left or right leaning websites more prone to equally quoting speakers from all political orientation?   
         
 2. Quoting style according to political orientation
     
     a) Compare length, sentiment: left more postive and right more negative?

     b) Look at impact of the website's political orientation on how they report on speakers based on the speakers' political orientation: Will a left website take shorter and more negative quotes for right speakers and vice versa?
    
 3. Comparing factual reporting of different websites and correlation with length and sentiment
 
    a) Grouping by factual reporting (factual_reporting): Do websites with higher factual reporting rating use longer and more neutral quotes?
         
    b) Correlation of factual reporting and degree of political leaning of websites: Are more central leaning news oulets more factually accurate than right/left leaning website?
        
4. PCA/clustering

    a) Visualise the results of PCA based on political leaning of the webiste.

    b) Visualise the results of PCA based on factual reporting of the webiste.

## **Team Organization**

**Iris**: Preliminary data analysis, data preprocessing, website code creation (i.e. most of sections B & C of the notebook, website)

**Quentin**: Additional data preprocessing, data computation, notebook formatting (part of sections C and D, readme)
 
**Jocelyn**: Data visualisation, help on data computation (most of section D and E)

**Théo**: Design of the study (choice of visualisations and website layout), graph analysis, data story creation, readme (mainly section E and website)
     
*Github commits are not representative of the work of each team member, as all the work was done on a google colab.
