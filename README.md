# Web-scrapping project on Openrice

The purpose of this project is to develop my web-scraping skills as a tool to collect data from external sources, which can then be used to create valuable insights.

## Table of Contents
- Aims and objectives
- Scenario
- Data Collection
- Data Processsing 
- Exploratory Data Analysis
- Conclusion
- Challenges
- Next Steps


## Aims and objectives

- The aim of this project is to collect relevant data from OpenRice.com, a restaurant review platform, using web-scraping. This data will then be analysed and used to provide business advise for new restaurant owners on where to open and at what price range based on the cuisine type.
- The business value we intend to create by doing this project is to give restaurant owners and investors data driven justification on why they should open in a particular area in Hong Kong


## Scenario 
 
A restaurant owner is looking to open a new Japanese restaurant in Hong Kong, but wants to get a better understand of the market for this particular cuisine. We were hired as consultants to help the individual develop these insights.

![Banner](https://user-images.githubusercontent.com/70877020/127438241-3787d43d-64b0-42f8-9b8b-6fc44e9aac9b.png)


## Data Collection

The following data was scarped from openrice.com.

- Address
- Price Range
- No. of Reviews
- Likes/Dislikes
- Cuisine Details (Type of Japanese Food) 
- No. of Bookmarks

![Screenshot 2021-07-29 at 14 42 40](https://user-images.githubusercontent.com/70877020/127444328-3724c09f-95a0-4281-a9b8-5ee6e407fcfc.png)


## Data Processing 

1) Dropping Duplicates based on unique id (res_id)
2) Removing restaurants with less than 5 reviews as contributes less reliable insights for our analysis

![Screenshot 2021-07-29 at 14 58 35](https://user-images.githubusercontent.com/70877020/127446390-ba3ff9a5-658c-46a2-935b-b48bc62ba333.png)

3) Splitting the address to create a new "District Column" which can be used to classify location

![Screenshot 2021-07-29 at 15 00 10](https://user-images.githubusercontent.com/70877020/127446614-44fbc055-807a-4f09-91ed-7cf3cd79f3f7.png)

4) Creating a metric for like as percentage (%) 

![Screenshot 2021-07-29 at 15 05 06](https://user-images.githubusercontent.com/70877020/127447249-a7bb438f-63ba-4f25-94e1-ef8162c20dbd.png)

5) Update invalid district found in specific row

![Screenshot 2021-07-29 at 15 05 23](https://user-images.githubusercontent.com/70877020/127447298-589b10c5-16cd-48d2-96ef-89ddfd2fadf8.png)

6) Found that although filtered for Japanese cuisine, some took the form of fusions with other cuisine i.e "Japanese / French" 

![Screenshot 2021-07-29 at 15 06 04](https://user-images.githubusercontent.com/70877020/127447571-463c7934-4235-4286-9f2a-d0737d1fbc4c.png)

7) Creating a metric to determine popularity 

As the financial performance of the resaurants were unavailable, a metric was devised that would allow us to determine the popularity of the restuarant instead. The assumption is the more popular the restuarant, the more profitable it will be. 


After investigating the relationship between the number of 'likes', 'dislikes', "likes (%), 'bookmarks' and 'reviews', it was identified that there is a high correlation between 'bookmarks' and 'review'. Therefore, these columns were used to create the folowing popularity metric:

                                                            Popularity Index = Number of bookmarks x Like precentage

## Exploratory Data Analysis

After defining popularity, an EDA was conducted comparing it to location, food type, and price-range.

### Location

An outline of the most popular locations in Hong Kong for Japanese Restaurants. Causeway Bay appears to be the most popular location by far, followed by Central.

![Analysis_location](https://user-images.githubusercontent.com/70877020/127450480-d5b3041f-efdd-49ba-818e-75068b7c5461.png)


### Food Type

All-you-can-eat Japanese Restaurants appears to be the most popular choice.

![download_1](https://user-images.githubusercontent.com/70877020/127450739-0b2747a5-1c98-4c11-835f-0b640846f73b.png)


### Price-Range

Interestingly, the higher price-range of $801+ seems to be the most popular. However, this could potential be explained by the previous findings

1) Causeway Bay and Central are prime locations in Hong Kong, with high rental cost. This makes it a popular hotspot for high end restaurants which attracts customers that are willing to spend more money on their meals.
2) All-you-can-eat buffet option tends to be more expensive in general

![unknown](https://user-images.githubusercontent.com/70877020/127450800-49600ecb-afd0-4357-9d58-993655175d99.png)


## Conclusion 

Based on our insights, an assumption can be made that the best place to open a new Japanese Restaurant would be in Causeway Bay, offering all-you-can-eat and charging a price range of $801+. However, other factors and personal preferences should be considered like what type of consumer is being targeted. For examples, is it a sophisticated restuarant trying to attract business individauls? or is it more of a young and vibrant vibe which would attract a younger demographic. This would indeed have an impact on their consumer preference and price-range. 

Another consideration is the saturation of the market. For instance, Causeway Bay appears to be highly saturatred with Japanese Restaurants. Therefore, the client might want to consider area that is still growing in popularity like Sheung Wan or Wan Chai.

In conclusion, the insights can provide justifiactions for why the client might want to open a restauarant in a particular location. However, other factors should be considered in the decision making process.

## Challenges 

1) Whilst web-scraping it was found that Openrice.com would only return 250 entries for each search. To fix this, the data was collected in batches by adjusting the search scope each time.

2) Invalid entries in 'District' and 'Cuisine' meant these had to be manually ammeneded during data processing. This was achievable with the current data-set, however it could prove an issue with larger data-sets.

## Next Steps

- The above analysis should be applied to other food cusiines (American, Italian, Chinese etc.) to see if similar insights can be generated.
- Potentially explore other food review websies, and adding new features to our data-set by combining multiple sources.
- As the judgement of popularity is currently based on an assumption, a more reliable measure wil need to be used like finacial reports. This should also be compared to market research on how the restaurant industry is performing at the time and any other relevant news/information.









