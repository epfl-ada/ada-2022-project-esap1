View our datastory here: https://sylveri.github.io/ada/
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

If there is a meaningful connection here, some potential use cases of these findings would be being able to better market certain types of beer to users who are more likely to be receptive to them in order to consistently score above average reviews.

## Methods
### Step 1: Data-scraping, Data-handling, and Filtering

* Convert a .txt file into an easily readible .csv directly accessible  by pandas.read_csv
* Remove rows with missing values (we have a lot of data, we don't have to be stingy with it)

### Step 2: Preliminary analysis and Data vizualisation

* Analyze and visualize the overall distributions of ratings inter and intra beer, of nationality of users and breweries, of number of raitngs inter and intra beer, 
* Compare BeerAdvocate and RateBeer to see if they can be merged (they can't, the distribution don't overlap quite significantly)
* Drop data relative to beers that have only 1 review
* We will focus the analysis on the US for the BeerAdvocate dataset due 73% coverage of the dataset by American users. Also, we think the fact that users are not American might affect the quality of lexicon and hence, our analysis. This is still to be determined.

### Step 3: Generating metadata and preprocessing
- Generate the following metadata:
  1. Difference between a reviewer's specific rating and the average rating for that beer 
  2. Both user and country location data, and a boolean value depending on whether they are matching or not
  3. The number of reviews written by each reviewer
  4. Length of review
  5. Complexity of the lexicon used for the review 
  6. relative time between user's review and the first review of a given beer
  9. Group and replace countries and states by areas
  
These help us measure trends and make comparisons among different populations of people. For example, do East coast Americans review and drink more beer than West Coast Americans? Perhaps one nationality or group of reviewers uses more sophisticated English in their reviews, possibly demonstrating that they are more saavy about beer. Adding these features could help us find out.

### Step 4: Applying Machine learning algorithms

* Train and Test split (no Validation test since we are using cross-validation)
* Do a linear regression with X = (features selected and created), Y = (rating - average_rating_for_that_beer)

### Step 5: Extracting impactful features and Centralization of the Analysis

* Extract most impactful features by taking those that give the biggest contribution to the explanation of the variance. Hypothesize and eventually test the reason why those are actually the most impactful
* Depending on which features turn out to be most important, do a specific deep dive in that (e.g. let's say that the match between nationality of user and beer is the most impactful, then we might look further into which nation care the most that the beer is from their own country. Other similar analysis might be done for other features)

### Step 6: Discussions and Prospects

* Final discussion and interpretation of the results



##  Timeline

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

