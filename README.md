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

* Make .txt file with a weird format into a .csv directly readible by pandas.read_csv
* Remove rows with missing values (we have a lot of data, we don't have to be stingy with it)

### Step 2: Preliminary analysis and Data vizualisation

* Analyze and visualize the overall distributions of ratings inter and intra beer, of nationality of users and breweries, of number of raitngs inter and intra beer, 
* Compare BeerAdvocate and RateBeer to see if they can be merged (they can't, de distribution don'overlap quite significantly)
* Drop data relative to beers that don't have enough reviews (50 seems like a good value with pur analysis up to date, but we might change it in hindsight)

### Step 3: Generating metadata & Preparing for process

* Generate the following metadata: (difference between every rating and the average rating for that beer, binary value {1: above average rating, 0: below average rating} for every review (average rating is the average for that beer), Matching between country of beer, number of reviews written by each user, length of review, complexity of lexicon used (inverse of frequency of that word being used in “normal” english), relative time between 1st review for a given beer and the given review, popularity of each beer (number of reviews at the time of review), prevalence of beer drinking in the country of the user.
* Drop rows for which the metadata is not available (again, we don't have to be stingy)
* Normalize features

### Step 4: Applying Machine learning algorithms

* Train, Test, Validation split
* Do a linear regression with X = (features selected and created), Y = (rating - average_rating_for_that_beer)
* Do a logistic regression with X = (features selected and created), Y = (1 if ratings above average for that beer; 0 if below)
* (This we are still discussing whether to do it or not) Do a single layer NN regression with  X = (features selected and created) and both Y = (rating - average_rating_for_that_beer)  Y = (1 if ratings above average for that beer; 0 if below)

### Step 5: Extracting impactful features and Centralization of the Analysis

* Extract most impactful features by taking those that have a higher coefficient (and maybe take into consideration Pearson's coefficient/ mutual information as well; see question for TAs), for NN look at questions for TAs
* Depending on which features turn out to be most important, do a soecific deep dive in that (e.g. let's say that the match between nationality of user and beer is the most impactful, then we might look further into which nation care the most that the beer is from their own country. Other similar analysis might be done for other features)

### Step 6: Discussions and Prospects

* Final discussion and interpretation of the results



## Proposed timeline
| | Task |
| :---:|---|
| Alessandro| |
| Eric | |
| Paul | |
| Selim | |

## Organization within the team: A list of internal milestones up until project Milestone P3.


## Questions for TAs (optional): Add here any questions you have for us related to the proposed project.
1) Is it meaningful to do the NN analysis part? We would use a single hidden layer NN: $f(x)=\sum_ic_iReLU(w_ix)$. Then we would define the impact of feature j as $\frac{\sum_i|c_i||w_i|w_{ij}}{\sum_i|c_i||w_i|}$

