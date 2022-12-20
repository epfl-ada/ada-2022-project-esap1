### Repository organization:
* There are in total four notebooks located in the Notebook folder
 * The first is <code>Group and make into csv.ipynb</code>. It corresponds to how we transformed our raw data to make it into a handy csv file for pandas
 * The second one <code>Initial_analysis.ipynb</code>. It contains the preliminary analysis of the data. That is when we chose to separate the analysis for the two datasets (__BeerAdvocate__ and __RateBeer__). This will be explained later.
 * The third one <code>metadata_ba.ipynb</code> is then a scratch on the building of extra features from BeerAdvocate dataset.
 * The fourth one <code>metadata_rb_ipynb</code> is the same for RateBeer dataset.

# Is deliciousness in the taste buds of the drinker? 

## Abstract
It is reasonable to look at someone's rating of a beer as being composed of two factors; the actual quality of the beer and their personal taste. But is personal taste actually atomic, as in formed of a single irreducible unit or component in a larger system, or like an actual atom, composed of sub-parts? 
We feel it might be the latter.
To see whether our gut instinct is right, we will analyze the Beer Reviews dataset. Focusing on informations other than those directly about the beer and beer quality, we will see if we are able to explain the variance in the ratings for a given beer. Finally we’ll do a deep dive on the aspect that turns out to be the best at explaining said variance.


## Research Questions
1) Can our data + new features explain the variance of the ratings for a given beer
2) Can our data + new features predict whether a review will be above or below the average?
3) Which of our features is most predictive?
4) Why could that be the case?

## TODO: Why are these questions important? What can we do/How can we utilize our conclusions?

## Proposed additional datasets:
Here is a list of the additional datasets we should be using:
  * This [page](https://en.wikipedia.org/wiki/List_of_countries_by_beer_consumption_per_capita) lists the __beer consumption of all countries per capita__. We should be using BeautifulSoup, and Request libraries to extract the table from the html link and transform it into a Pandas dataframe. This data will give us insights on the prevalance of each reviewer to beer consumption. With it, we can make a new feature, consumption, that would take the nationality of the reviewer and map it to the corresponding average consumption. Although, reviewers may consume more beers than the average, we make the assumption that it is still representative of prevalence to beer consumption. We will set boundaries before the analysis to be sure to have sufficient reviews from countries and enough reviewers.
  * The [BeerInfo](https://beerinfo.com/beer-consumption-by-state-per-capita/) website provides the same kind of data as the previous link, but for each states in the United States. Since Americans represent 86% of the reviewers, we thought it would be insightful to apply the same process as the previous additional dataset. Variance in consumption might be less than for the international dataset since we are only studying one country, but the data set will be much richer so this compensates.

## Methods
### Step 1: Data-scraping, Data-handling, and Filtering

* Convert a .txt file into an easily readible .csv directly accessible  by pandas.read_csv
* Remove rows with missing values (we have a lot of data, we don't have to be stingy with it)

### Step 2: Preliminary analysis and Data vizualisation

* Analyze and visualize the overall distributions of ratings inter and intra beer, of nationality of users and breweries, of number of raitngs inter and intra beer, 
* Compare BeerAdvocate and RateBeer to see if they can be merged (they can't, the distribution don't overlap quite significantly)
* Drop data relative to beers that don't have enough reviews (50 seems like a good value with pur analysis up to date, but we might change it in hindsight)
* We might focus the analysis on the US for the BeerAdvocate dataset due 73% coverage of the dataset by American users. Also, we think the fact that users are not American might affect the quality of lexicon and hence, our analysis. This is still to be determined.

### Step 3: Generating metadata & Preparing for process

* Generate the following metadata: (difference between every rating and the average rating for that beer, binary value {1: above average rating, 0: below average rating} for every review (average rating is the average for that beer), Matching between country of beer, number of reviews written by each user, length of review, complexity of lexicon used (inverse of frequency of that word being used in “normal” english), relative time between 1st review for a given beer and the given review, popularity of each beer (number of reviews at the time of review), prevalence of beer drinking in the country of the user.
* Drop rows for which the metadata is not available (again, we don't have to be stingy)
* Normalize features (the normalization should depend on the distribution from Step1 of the different features.
* We are still thinking if it would be better to translate the reviews that are not in English (which directly affects review meaning, and lexicon as well). Otherwise, we use complexity of lexicon in the review language but we get less reviews of the same language.

### Step 3: Generating metadata and preprocessing New
- Generate the following metadata:
  1. Difference between a reviewer's specific rating and the average rating for that beer (binary value depending on whether the user's rating was below or above the average rating)
  2. Both user and country location data, and a boolean value depending on whether they are matching or not
  3. The number of reviews written by each reviewer
  4. Length of review
  5. Complexity of the lexicon used for the review 
  6. relative time between user's review and the first review of a given beer
  7. Popularity of each beer
  8. Prevalence of beer in the country of the reviewer
  9. For US users, their state and region within the United States
  10. For Non US users, their region within their continent  
  
These help us measure trends and make comparisons among different populations of people. For example, do East coast Americans review and drink more beer than West Coast Americans? Perhaps one nationality or group of reviewers uses more sophisticated English in their reviews, possibly demonstrating that they are more saavy about beer. Adding these features could help us find out.

### Step 4: Applying Machine learning algorithms

* Train and Test split (no Validation test since we are using cross-validation)
* Do a linear regression with X = (features selected and created), Y = (rating - average_rating_for_that_beer)
* Do a logistic regression with X = (features selected and created), Y = (1 if ratings above average for that beer; 0 if below)
* (This we are still discussing whether to do it or not) Do a single layer NN regression with  X = (features selected and created) and both Y = (rating - average_rating_for_that_beer)  Y = (1 if ratings above average for that beer; 0 if below)

### Step 5: Extracting impactful features and Centralization of the Analysis

* Extract most impactful features by taking those that have a higher coefficient (and maybe take into consideration Pearson's coefficient/ mutual information as well; see question for TAs), for NN look at questions for TAs
* Depending on which features turn out to be most important, do a soecific deep dive in that (e.g. let's say that the match between nationality of user and beer is the most impactful, then we might look further into which nation care the most that the beer is from their own country. Other similar analysis might be done for other features)

### Step 6: Discussions and Prospects

* Final discussion and interpretation of the results



## Proposed timeline

* Step 1-2: 23/11/2022 (clean into function files what has be done already)
* (Homework 2)
* Step 3: 05/12/2022 
* Step 4: 12/12/2022
* Step 5-6: 16/12/2022
* Building the DataStory and clean repository/notebooks, enhance data vizualisation : until Deadline

## Organization within the team
| | Task |
| :---:|---|
| Alessandro| Data scraping. Normalization of features. Enhancement of data visualization, Final analysis|
| Eric | Creation of metadata and Preparation for process, Website handling|
| Paul | Preliminary analysis & Data viz. Extraction of impactful features, Final analysis|
| Selim | Linear/Logistic Regression Build-ups, Web data extraction|

