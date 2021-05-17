# python-api-challenge

## Background

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. Using Python requests, APIs, and JSON traversals, this project answers the basic question: "What's the weather like as we approach the equator?"

## Part I - WeatherPy

I created a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator using a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), generating a representative model of weather across world cities.

My first requirement was to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
![image](https://user-images.githubusercontent.com/69601778/118565545-383c1000-b727-11eb-9eb2-d295a07d03ef.png)

* Humidity (%) vs. Latitude
![image](https://user-images.githubusercontent.com/69601778/118565528-307c6b80-b727-11eb-9037-00ef0bc8899c.png)


* Cloudiness (%) vs. Latitude
![image](https://user-images.githubusercontent.com/69601778/118565515-26f30380-b727-11eb-8966-ac557c964dd7.png)

* Wind Speed (mph) vs. Latitude
![image](https://user-images.githubusercontent.com/69601778/118565446-0a56cb80-b727-11eb-80b1-e14abe82612d.png)

After each plot I added a sentence or too explaining what the code is and analyzing.

My second requirement is to run linear regression on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots I explain what the linear regression is modeling such as any observed relationships and any other relevant analysis.

My final notebook:

* Randomly selects **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Performs a weather check on each of the cities using a series of successive API calls.
* Includes a print log of each city as it's being processed with the city number and city name.
* Saves a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Uses jupyter-gmaps and the Google Places API for this part of the assignment.

* Creates a heat map that displays the humidity for every city from the part I of the homework.

![image](https://user-images.githubusercontent.com/69601778/118565806-aed90d80-b727-11eb-9d17-caed9d67dfe6.png)

* Narrows down the DataFrame to find your ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Drops any rows that don't contain all three conditions.

  * **Note:** Feel free to adjust to your specifications but be sure to limit the number of rows returned by your API requests to a reasonable number.

* Using Google Places API, finds the first hotel for each city located within 5000 meters of your coordinates.

* Plots the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.
![image](https://user-images.githubusercontent.com/69601778/118565905-dc25bb80-b727-11eb-8fa4-85f8607be808.png)
