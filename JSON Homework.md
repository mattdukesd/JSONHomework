

```python
# Dependencies
import matplotlib.pyplot as plt
import requests as req
import pandas as pd
import openweathermapy as ow
import citypy as cp
```


```python
# Save config information.
api_key = "25bc90a1196e6f153eece0bc0b0fc9eb"
settings = {"units": "imperial", "appid": api_key}
```


```python
# Some random coordinates
lat_lngs = []
cities = []

lats = np.random.uniform(low=20,high=80,size=1500)
longs = lngs = np.random.uniform(low=60,high=160,size=1500)
lat_lngs = zip(lats,lngs)


```


```python
for lat_lng in lat_lngs:
    city = citipy.nearest_city(lat_lng[0],lat_lng[1]).city_name
    if city not in cities:
        cities.append(city)

```


```python
cities = cities[:499]
```


```python

```


```python

```


```python
city_weather_data = [ow.get_current(city, **settings) for city in cities]
```


```python
summary = ["main.temp", "coord.lat", "coord.lon"]
# Create a Pandas DataFrame with the results
data = [response(*summary) for response in weather_data]

column_names = ["Temperature", "Latitude", "Longitude"]
weather_data = pd.DataFrame(data, index=cities, columns=column_names)
weather_data
```


```python
for index, row in city_weather_data.iterrows():
    try:
        # Grab the username
        target_user = row['city']
        # print(target_user)

        # Use the username with the Twitter API get_user
        user_account = api.get_user(target_user)
        user_real_name = user_account["name"]

        # Get the specific column data
        user_tweets = user_account["statuses_count"]
        user_followers = user_account["followers_count"]
        user_following = user_account["friends_count"]
        user_favorites = user_account["favourites_count"]

        # Replace the row information for each
        popular_tweeters.set_value(index, "Real Name", user_real_name)
        popular_tweeters.set_value(index, "Tweets", user_tweets)
        popular_tweeters.set_value(index, "Followers", user_followers)
        popular_tweeters.set_value(index, "Following", user_following)
        popular_tweeters.set_value(index, "Favorites Count", user_favorites)
    
    except:
        continue
```


```python
city_list = []
try:
    city.append(row['city'])
    
except:
    print(row['city'])

```


```python
city_weather_data = city_weather_df[city_weather_df['city'].isin(city_list)]
```


```python
# Create an "extracts" object to get the temperature, latitude,
# and longitude in each city
summary = ["main.temp", "coord.lat", "coord.lon"]
# Create a Pandas DataFrame with the results
data = [response(*summary) for response in weather_data]

column_names = ["Temperature", "Latitude", "Longitude"]
weather_data = pd.DataFrame(data, index=cities, columns=column_names)
weather_data
```


```python
 # Build a scatter plot for each data type
plt.scatter(weather_data["lat"], weather_data["temp"], marker="o")

# Incorporate the other graph properties
plt.title("Temperature in World Cities")
plt.ylabel("Temperature (Celsius)")
plt.xlabel("Latitude")
plt.grid(True)

# Save the figure
plt.savefig("TemperatureInWorldCities.png")

# Show plot
plt.show()
```
