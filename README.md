# CapstoneProject

# Cases of Dengue Fever in Malaysia

For this project I created a dataset that collected reported cases of Dengue Fever in Malysia in 10 different cities between the years 1993-2010. 

The first points of data I collected were from a preexisting dataset that provided information for contracted cases by city and year. After cleaning these
series I thought it might also be interesting to add weather data to this set, I did so using the darksky API.

First I looked at all the cities being represented:
![](https://github.com/FHyder/CapstoneProject/blob/master/df.city.unique.png)

Recorded all latitude,longitude values along with the keys:

![](https://github.com/FHyder/CapstoneProject/blob/master/df.city.unique2.png)

Then used a function to retrieve weather data for each city, month, and year represented on this set

![](https://github.com/FHyder/CapstoneProject/blob/master/getweatherdata.png)


I also used world bank to retrieve population and GDP data and added it to my Dataset leaving me with the following features and target(Count)

![](https://github.com/FHyder/CapstoneProject/blob/master/complete.png)

I then ran 7 different models on this data and appended the mean-squared-error of each onto a list to see which model performed best. In this 
case it was a random forest with untuned parameters.

![](https://github.com/FHyder/CapstoneProject/blob/master/MSE%20graph.png)

I checked feature importances for the selected model:
![](https://github.com/FHyder/CapstoneProject/blob/master/featureimportance.png)

And used the lime library to understand how these features were used:

![](https://github.com/FHyder/CapstoneProject/blob/master/LIME.png)


###My conclusions:

#### Contrary to my beliefs, weather didn't play a huge role in predicting count. Rather, location seems to be the big deciding factor. Specifically in the cities of Selangor, Johor, and Perak which, if you're residing in any of these cities, your likelihood of contracting Dengue seems to increase.

#### Conversely, 'not living' in Perlis seemed to cause increased cases of Dengue fever. Perhaps Perlis is a relatively safer city to be in when it comes to Dengue

#### Population also played a large role in predictions, although this feature is a bit controversial. The population reported on this dataset is that of the entire country and not of the cities. That being said, populations over 2,420,839 is linked to higher instances of the disease

#### Another noteworthy feature is year, observations made after 2002 allegedly linked to higher instances of Dengue


#### There's a lot more that can be done to achieve more accuracy with this dataset. To improve my results, I would try a bit harder to find city specific population counts, test out more models, and try to see if I can find any city/time specific precipitation data. Darksky did not report on rain for any of these cities which I found to be a huge setback. As a former resident of Southeast Asia (Bangladesh), I can assure you that mosquitos thrive in damp conditions. 
