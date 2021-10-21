# Python API - What's the Weather Like?

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. 
Using Python requests, APIs, and JSON traversals to answer the fundamental question: "What's the weather like as we approach the equator?"

![Equator](Images/equatorsign.png)


## Part I - WeatherPy

Created a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. 

Utilized a [simple Python library](https://pypi.python.org/pypi/citipy), and the [OpenWeatherMap API](https://openweathermap.org/api),to create a representative model of weather across world cities.

From the data gathered, a series of scatter plots were generated to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

The data was separated into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude) and linear regression was used to model the relationship:

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots is a brief analysis of the linear regression model, referencing any noticeable relationships.

The final notebook:

* Randomly selected **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Performed a weather check on each of the cities using a series of successive API calls.
* Included a printed log of each city as it's being processed with the city number and city name.
* Saved a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Used skills in working with weather data to plan future vacations, utilizing jupyter-gmaps and the Google Places API.

* Created a heat map that displays the humidity for every city from part I.

  ![heatmap](Images/heatmap.png)

* Narrowed down the DataFrame to find the ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Dropped any rows that don't contain all three conditions as you want to be sure the weather is ideal.

* Used Google Places API to find the first hotel for each city located within 5000 meters of specified coordinates.

* Plotted the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)
