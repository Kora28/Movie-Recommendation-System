# Movie-Recommendation-System
The data set which was used is "The Movie Dataset" from Kaggle which has over 45,000 movies. Simpler and Content Based Recommendation is being created with respect to different users.

# SIMPLE RECOMMENDER/ Demographic Filtering:
This type of recommenders offers based on movie popularity and genre. This recommender does not give personalized recommendations based on the user history. All we have to do is sort our movies based on ratings and popularity and display the top movies of our list.

In order to find the Weighted Rating, The formula which is used is IMBD weighted rating:

                        Weighted Rating (WR) = (v/(v+m))R + (m/(v+m))C

v is the number of votes for the movie
m is the minimum votes required to be listed in the chart
R is the average rating of the movie
C is the mean vote across the whole report

Then, we could could sort the weighted rating to find the Top rated movies. 

## SIMPLE RECOMMENDATION WITH GENRE:

We could take genre name as input along with data and Percentile for choosing minimum votes(m) required to be listed in chart.
After that genre , remove particular set of data and then use the same Weighted Rating Formula and sort teh best rated movies for this particular genre.

# CONTENT BASED RECOMMENDER
The content of the movie (overview, cast, crew, keyword, tagline etc) is used to find its similarity with other movies. Then the movies that are most likely to be similar are recommended.

## MOVIE DESCRIPTION/PLOT BASED RECOMMENDER:
As the computation is very higher if we use all 40,000 data, so we will take percentile to be 70% from the previous Recommeder and then use it here for the movie Description based Recommender.

In this recommender, we will use TfidfVectorizer and find the matrix from that, we could apply Linear Kernel and find the final matrix which shows importantance of each word features to that particlular movie. And with those information, we will get Recommendation based on the movie we mentioned.

As our recommender only recommends based on the Plot or description of the movie, but many of us prefers movies based on actors or other crew members.

## CREW/CAST BASED RECOMMENDER:

In this recommender, we will use important crew/cast numbers for our recommendation to reduce the computational cost. 
Like for crew , we will use Director.
For Cast, Top 3 important characters.

In this content based recommendation, we will also use genre and Keywords column to determine the better results. As there are many features for each movie, In order to give higher weight for some particular features , I multiplied Director Feature by 3. This will help in giving better recommendation results based on the Directors movies also.

