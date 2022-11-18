# The uncooperative part of taste reviews  
___Why are some people more critical than others ?___

## Abstract
Is deliciousness in the taste buds of the drinker? 
It is reasonable to look at the rating someone gives to a beer as being composed of two factors; the actual quality of the beer and their personal taste. But is personal taste actually atomic {of or forming a single irreducible unit or component in a larger system} or, like an actual atom it is composed of sub-parts? 
We feel it might be the latter.
To see whether our gut instinct is right, we will analyze the Beer Reviews dataset. Focusing on informations other than those directly about the beer and beer quality, we will see if we are able to explain the variance in the ratings for a given beer. Finally we’ll do a deep dive on the aspect that turns out to be the best at explaining said variance.




## Research Questions
1) Can our data + new features explain the variance of the ratings for a given beer
2) Can our data + new features predict whether a review will be above or below the average?
3) Which of our features is most predictive?
4) Why could that be the case?



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
