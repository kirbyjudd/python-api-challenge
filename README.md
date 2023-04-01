# python-api-challenge
# Background
Data's true power is its ability to definitively answer questions. So, let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What is the weather like as we approach the equator?"

Now, we know what you may be thinking: “That’s obvious. It gets hotter.” But, if pressed for more information, how would you prove that?

# Summary
For this assignment I had to utilize python, jupyter notebook, matplotlib, and two API's (OpenWeatherMap API and Geoapify API) to analyze how weather differs when approaching or getting further away from the equator. There are two jupyter notebooks called WeatherPy and VacationPy that I worked on. 

# WeatherPy.ipynb
After retrieving random geographic coordinates from the citipy Python library, I had a list of 621 different cities. I then utilized the OpenWeather API to retrieve city weather data which included the: City Name, Latitude, Longitude, Max Temperature (C), Humidity (%), Cloudiness (%), Wind Speed (m/s) Country, and Date. I appended this data into the city_data list and now had a total of 573 cities with their respective weather data. I then created a csv file called cities.csv and put it into the output_data folder.

Next I had to create scatter plot of the cities Latitude vs a particular variable. Four scatter plots were created and output to the output_data folder. These included:
- Latitude vs Max Temperature
- Latitude Vs. Humidity
- Latitude Vs. Cloudiness
- Latitude vs. Wind Speed

The final task was to analyze cities in the northern hemisphere (greater than or equal to 0 latitude) and southern hemisphere (less than 0 latitude) and perform linear regression on the scatter plots. More discussion about the linear relationships is found in the WeatherPy notebook. 

# VacationPy.ipynb
Utilizing the cities.csv file that I created earlier, I generated a map that displays a point for every city in the file using pandas hvplot.

I then narrowed down the data to my ideal weather conditions which was: A temperature between 20 and 30 Celsius, a wind speed less than 7 m/s, a cloudiness percentage less than 8%, and humidity level less than 70%. Any rows with null values was dropped. 

I then created a new DataFrame with the new ideal weather conditions and named it hotel_df. An empty column was created to hold the "Hotel Name". Using Geoapify, I searched for the first hotel located within a 10,000 meter radius of the ideal weather city coordinates.

Lastly, I added the hotel name and country as additional hover message information for the previously generated hvplot map.

# File Location
The files are located in the "WeatherPy" folder.

- Both the WeatherPy_main.ipynb and VacationPy_main.ipynb files can be found in the "starter_code" folder. 
- The cities.csv and four scatterplot .png figures can be found in the "output_data" folder.
