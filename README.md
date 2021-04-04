# World Weather Analysis

## Overview of the World Weather Analysis

In this Module, we learned how to retrieve the city weather data from OpenWeatherMap API, created scatter plot of the city weather data, used linear regression to find the relationship between city’s latitude and maximum temperature, percent humidity, percent cloudiness and wind speed respectively. Lastly, used Google Maps and Places API created Heatmaps for weather parameters. 

In order to allow the beta tester to filter the data by inputting weather preferences to identify potential travel destinations and nearby hotels in the PlanMyTrip app, we are going to add the weather description to the city weather data, and use the Google Maps Directions API to create a travel route between the cities as well as layer map. 

Here are the tasks:

1.	Retrieve the weather data from OpenWeatherMap API.
2.	Create a Customer Travel Destinations Map.
3.	Create a Travel Itinerary Map.

## Analysis

1.	Retrieve the weather data 

(1)	Used random.uniform() function in Numpy to create 2,000 random latitudes and longitudes. 

(2)	Then used zip() function to create tuples for each pair of latitude and longitude. Since the zipped tuple can only be unzipped once before it is removed from the computer’s memory, added the latitudes and longitudes to a list. 

(3)	Used citypy.nearest_city() to identify the nearest city for each latitude and longitude combination, saved in cities list. 

(4)	Looped though all the city in the cities list, run the API request to get the JSON file that contains all the information we need. Then parsed the JSON file and get the latitude, longitude, maximum temperature, percent of humidity, percent of cloudiness, wind speed, country, and current weather description and stored them in each variables. Saved all the information in city_data list.

(5)	Created a DataFrame from the city_data list, then reordered the columns.

(6)	Export the data to CSV file.

2.	  Create a Customer Travel Destinations Map.
(1)	Read in the CSV file created from the first task. 

(2)	Prompted the user to enter the minimum and maximum temperature and stored the values in variables. These variables will be used to filter the data in following step.

(3)	Created a new DataFrame by using the variables created from step(2) to filter the city data dataframe. 

(4)	Removed the records with missing values.

(5)	Created a dataframe with city, country, max temperature, current weather description, latitude and longitude as the columns. Added a blank column for hotel name.

(6)	Get the hotel name from Google Direction API based on the latitude and longitude from the dataframe. Insert the values into the dataframe.

(7)	Remove the records with missing values to get the final cleaned dataframe for hotel.

(8)	Output the dataframe to a CSV file.

(9)	Created the map.

3.	Create a Travel Itinerary Map.

(1)	Read in the CSV file created from task 2.

(2)	Created a heatmap, and pick 4 cities to create a vacation itinerary route to travel between the four cities. 


## Results

1.	The sample of final WeatherPy Database. 

![ins1](https://user-images.githubusercontent.com/79289806/113497630-fab35880-94d3-11eb-8b69-be6fd39d7201.png)

2.	The hotel information dataframe:

![ins2](https://user-images.githubusercontent.com/79289806/113497631-fb4bef00-94d3-11eb-9705-d7f7c3d5a55d.png) 

Customer Travel Destinations Map:

![ins3](https://user-images.githubusercontent.com/79289806/113497632-fb4bef00-94d3-11eb-8fd2-33e54016d524.png) 

3.	New dataframe for the 4 cities:

![ins4](https://user-images.githubusercontent.com/79289806/113497633-fb4bef00-94d3-11eb-9d86-39cf10370dfd.png) 

Travel Itinerary Map:

![ins5](https://user-images.githubusercontent.com/79289806/113497634-fb4bef00-94d3-11eb-9cc0-a5d903378cad.png)  

![ins6](https://user-images.githubusercontent.com/79289806/113497635-fbe48580-94d3-11eb-8986-434e75aadff3.png) 

## Summary: 

Through the variety of APIs, we are able to get the weather data from random selected cities and create the heatmaps. In the meantime, we could customize the information in the heatmap. This will help the users to have a better experience when using the app to find their preferred place to travel based on temperature. Additionally, provide them with the hotel information.

The current code could be modified to create additional user-friendly selections. We could use APIs to retrieve information that needed for each selection, such as travel purpose (relaxing vacation, or hiking etc.) to give them all the possible choices all over the world. 


