
# WeatherPy

I am struggling with getting coordinates randomly generated, then transforming that into a city before performing the rest of the homework.. 

### Analysis


```python
import random
import matplotlib.pyplot as plt
import json
import requests
import pandas as pd
import seaborn as sns
import openweathermapy.core as owm
from config import gkey

```

### Generate Cities List


```python
url = "http://api.openweathermap.org/data/2.5/weather?"
settings = {"units": "metric",
           "appid": api_key}
query_url = url + "appid=" + api_key + "&q=" + city
#But I don't know the city
#Need to randomly select latitude and longtitude first

city = []
lat=["random.uniform(-90, 90)"]
temp=[]
humidity=[]
cloudiness=[]
windspeed=[]
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-10-1de8a9d5cced> in <module>()
          2 settings = {"units": "metric",
          3            "appid": api_key}
    ----> 4 query_url = url + "appid=" + api_key + "&q=" + city
          5 city = []
          6 lat=["random.uniform(-90, 90)"]
    

    NameError: name 'city' is not defined



```python
for latitude in lat:
    response=requests.get(query_url + city).json()
    lat.append(response["coord"]["lat"])
    temp.append(response["main"]["temp"])

print(f"The latitude information received is: {lat}")
print(f"The temperature information received is: {temp}")
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-9-1a18ef1653d4> in <module>()
    ----> 1 for latitude in lat:
          2     response=requests.get(query_url + city).json()
          3     lat.append(response["coord"]["lat"])
          4     temp.append(response["main"]["temp"])
          5 
    

    NameError: name 'lat' is not defined



```python
weather_response = requests.get(query_url)
weather_json = weather_response.json()

print(f"The weather API responded with: {weather_json}.")
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-6-22cf390d5337> in <module>()
    ----> 1 weather_response = requests.get(query_url)
          2 weather_json = weather_response.json()
          3 
          4 print(f"The weather API responded with: {weather_json}.")
    

    NameError: name 'query_url' is not defined


### Perform API Calls
