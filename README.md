# Analysis Weather
 This research aims to analyze the relationship between latitude and weather.
***

# Summary
I created a Python script to visualize the weather of over 500 cities of varying distances from the equator. First, the Python code randomly selectsed a group of 500+ cities across the world. Then,  I collected data from the OpenWeatherMap API. 

I analyzed the following relationships.

- Temperature (C) vs. Latitude
- Humidity  vs. Latitude
- Cloudiness  vs. Latitude
- Wind Speed  vs. Latitude

I found that the maximum temperature decreases less on the Southern Hemisphere than on the Northern Hemisphere  far from the equator. So I further analyzed the relationship between factors such as between (humidity, wind speed, cloudiness) and the maximun temperature.

***
# Analysis

## 1. create a series of scatter plots

<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig1.png"
  width="200"
  height="150"
/>
<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig2.png"
  width="200"
  height="150"
/>
<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig3.png"
  width="200"
  height="150"
/>
<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig4.png"
  width="200"
  height="150"
/>

## 2. Compute Linear Regression for Each Relationship
 ### <ins>Analysis between temperature and latitude On Northern Hemisphere </ins> 
- As latitude increases, the maximum temperature falls.(A positive coefficient sign). 
- On Northern Hemisphere, the Maximum temperature is closely related to latitude.(r value -0.84) <br>
  > We can see that the variation increases when the latitude reaches 50 degrees or more. **Through this, we infer that not only latitude but also other factors have a meaningful effect on the Maximum temperature in areas above 50 degrees.**<br>
  > And It can be seen that the variance of humidity is small at more than 50 degrees north latitude. <br>It is necessary to examine whether humidity affects temperature.
- We can predict that the Maximum temperature will drop 0.77 degrees for every 1 degree increase in latitude.
 ### <ins>Analysis between temperature and latitude On southern Hemisphere </ins> 
- As latitude increases, the maximum temperature rises.(A negative coefficient sign). 
- On Southern Hemisphere, the Maximum temperature is a little related to latitude.(r value -0.39) <br>
  > **It strongly suggests that there will be more variables that affect the Maximum temperature.** <br>
  > At the end of this report, I will examine other influencing factors.
- We can see that the Maximum temperature will drop 0.16 degrees for every 1 degree decrease in latitude.

**Compare two Datasets:** 
- Two datasets show that the further away from the equator, the lower the maximum temperature.
- The northern Hemisphere has a high correlation between latitude and maximum temperature, but the southern Hemisphere has a lower correlation than the northern Hemisphere. The Maximum temperature in the southern Hemisphere is influenced by other factors as well as latitude.

<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig5.png"
  width="200"
  height="150"
/><img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig6.png"
  width="200"
  height="150"
/>

### <ins>Analysis between humidity and latitude  on Northern Hemisphere</ins> 
- As latitude increases, the humidity increase.(A positive coefficient sign). 
- On Northern Hemisphere, The correlation between humidity and latitude is about 48 percent.(r value 0.48) <br>
- It means that less half of the variance in the outcome variable is explained by the model
  > **However We can see that the variation decreases when the latitude reaches 50 degrees or more. Considering that the maximum temperature variance increases when the latitude is over 50 degrees, we need to research whether humidity affects temperature.**
- We can see that humidity will increase 0.5 for every 1 degree increase in latitude.

<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig7.png"
  width="200"
  height="150"
/>
<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig8.png"
  width="200"
  height="150"
/>

### <ins>Analysis between cloudiness and latitude</ins>  
- The corelation between latitude and cloudiness is low in both the northern and southern hemisphere(Northern r value : 0.29, Southern r value is 0.23). Therefore, it is difficult to predict cloudiness depending on the change in latitude.

<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig9.png"
  width="200"
  height="150"
/>
<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig10.png"
  width="200"
  height="150"
/>


### <ins>Analysis between Wind speed and Latitude</ins>    
- Wind speed and latitude are not related on the northern hemisphere.(r value is 0.06) The southern hemisphere is more relevant than the northern hemisphere, but it does not show enough relevance to predict wind speed with latitude.(r value is -0.29)

<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig11.png"
  width="200"
  height="150"
/>
<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig12.png"
  width="200"
  height="150"
/>

### <ins>Analysis between latitude and other facts related to the max temperature.</ins>    
- On the Northern Hemispere, the correlation coefficient between humidity and temperature is (-0.49.)
- On the other hand, on the Southern Hemisphere, it is -0.38. 
- Through this, it can be seen that the higher the humidity, the lower the maximum temperature.
  The correlation coefficient is below 0.5, so it is difficult to say that the data is well explained.
  However it shows a higher correlation coefficient than other factors. Through this, it can be confirmed that humidity has some effect on the maximum temperatures on the both Hemishpere.
- In conclusion, it can be estimated that on the Southern Hemisphere, various factors other than latitude and humidity
- In the given data set, it can be seen that humidity affects temperature in addition to latitude.

<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig13.png"
  width="200"
  height="80"
/>
<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/Fig14.png"
  width="200"
  height="80"
/>
***
# Vacation Planning

Create a map that displays a point for every city by using the city data collected above.(The size of the point is the humidity in each city)

<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/plot15.png"
  width="400"
  height="250"
/>

Narrow down the data to find your ideal weather condition. 
- A max temperature lower than 27 degrees but higher than 21
- Wind speed less than 4.5 m/s
- Zero cloudiness

For each city, use the Geoapify API to find the first hotel located within 10,000 meters.

Add the hotel name and the country as additional information in the hover message for each city on the map

<img
  src="/Users/unghwanahn/git/Python_API_Challange/WeatherPy/output_data/plot16.png"
  width="400"
  height="250"
/>