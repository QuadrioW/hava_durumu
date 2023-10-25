# hava_durumu

import requests
import json

api_key = "eb8dd83609ff42a7b899d2347e84f5be"

url = f"https://api.weatherbit.io/v2.0/current?lat=41.2944&lon=36.3319&key=eb8dd83609ff42a7b899d2347e84f5be&include=minutely"

response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    temperature = data['data'][0]['temp']
    print(f"Hava Sıcaklığı: {temperature}°C")
else:
    print(f"Hata kodu: {response.status_code}. İstek başarısız oldu.")
