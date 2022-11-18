# The uncooperative part of taste reviews  
___Why are some people more critical than others ?___

## Abstract
Taste is a subjective opinion. This is demonstrated in this [study](http://i.stanford.edu/~julian/pdfs/icdm2012.pdf). Reviews of beers display the feelings of beer drinkers towards a specific beer. Their corresponding ratings of a beer helps to build an understanding in the variety of taste among consumers. As an extent of this analysis, we wish to explore the external parameters of the reviews and seek connections with the actual ratings. The external parameters are the features of a review that do not have anything to do with the actual beer. We can then study if 
certain types of people are just more difficult to satisfy than others, regardless of their taste. We use machine learning algorithms to promote the external features of a review that correlates with good/bad ratings. Hence, we obtain the parameters that define more or less critical reviewers. Inspecting the bias in a review, based on how critical the reviewer is, was found to be relevant.



## Research Questions
The study is built to tackle these questions:
  * What features are good candidates to describe how critical a reviewer is ?
  * What features are not ? 
  * Are there any of this metadata that correlates with the rating of the beer? 
  * If yes, why does this metadata correlates ? Or why are some reviewers harder to satisfy than others ?
  * Is the origin of the reviewer predictive of the average rating of this reviewer ?


## Proposed additional datasets (if any):
Here is a list of the additional datasets we should be using:
  * This [page](https://en.wikipedia.org/wiki/List_of_countries_by_beer_consumption_per_capita) lists the __beer consumption of all countries per capita__. We should be using BeautifulSoup, and Request libraries to extract the table from the html link and transform it into a Pandas dataframe. This data will give us insights on the prevalance of each reviewer to beer consumption. We can build from it a new feature, consumption that would take the nationality of the reviewer and map it to the corresponding average consumption. Although, reviewers may consume more beers than the average, we make the assumption that it is still representative of prevalence to beer consumption. We will set boundaries before the analysis to be sure to have sufficient reviews from countries and enough reviewers.
  * The [BeerInfo](https://beerinfo.com/beer-consumption-by-state-per-capita/) website provides the same kind of data as the previous link, but for each states in the United States. Since the Americans represent 86% of the reviewers, we thought it would be insightful to apply the same process as the previous additional dataset. Variance in consumption might be less than for the international dataset since we are only studying one country. But, the data set will be much richer so this compensates.

List the additional dataset(s) you want to use (if any), and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you’ve read the docs and some examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant. It is your responsibility to check that what you propose is feasible.



## Methods
### Step 1: Data-scraping, Data-handling, and Filtering

* One
* Two

### Step 2: Preliminary analysis and Data vizualisation

* One
* Two

### Step 3: Generating metadata & Preparing for process

* One
* Two

### Step 4: Applying Machine learning algorithms

* One
* Two

### Step 5: Extracting impactful features and Centralization of the Analysis

* One
* Two

### Step 6: Discussions and Prospects

* One
* Two



## Proposed timeline
| | Task |
| :---:|---|
| Alessandro| |
| Eric | |
| Paul | |
| Selim | |

## Organization within the team: A list of internal milestones up until project Milestone P3.


## Questions for TAs (optional): Add here any questions you have for us related to the proposed project.
