import requests

def get_ip_location():
    url = "https://ipinfo.io/json"
    response = requests.get(url)

    if response.status_code == 200:
        data = response.json()
        return {
            "IP": data.get("ip"),
            "City": data.get("city"),
            "Region": data.get("region"),
            "Country": data.get("country"),
            "Coordinates": data.get("loc"),
            "ISP": data.get("org")
        }
    else:
        return "Error fetching data"

location = get_ip_location()
for k, v in location.items():
    print(f"{k}: {v}")

    # Simulated GPS coordinates
latitude = 28.6139
longitude = 77.2090

print("Latitude:", latitude)
print("Longitude:", longitude)
