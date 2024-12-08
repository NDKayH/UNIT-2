```.py

import requests
import pandas as pd
from datetime import datetime

# Server details
SERVER_URL = "http://192.168.4.137/readings"
USERNAME = "noah"
PASSWORD = "aiobahn"
CSV_FILE = "raw_readings.csv"

# Function to obtain access token
def get_access_token():
    login_data = {"username": USERNAME, "password": PASSWORD}
    response = requests.post("http://192.168.4.137/login", json=login_data)
    return response.json().get("access_token")

# Function to fetch data from the server
def fetch_data(access_token):
    headers = {"Authorization": f"Bearer {access_token}"}
    response = requests.get(SERVER_URL, headers=headers)
    if response.status_code == 200:
        return response.json().get("readings", [])
    else:
        print("Failed to retrieve data:", response.status_code)
        return []

# Main process
def main():
    # Get access token
    access_token = get_access_token()
    if not access_token:
        print("Failed to get access token. Check your credentials.")
        return

    # Fetch data from server
    readings = fetch_data(access_token)

    # Convert the readings into a DataFrame and save to CSV
    if readings:
        df = pd.DataFrame(readings)
        df.to_csv(CSV_FILE, index=False)
        print(f"Data saved successfully to {CSV_FILE}")
    else:
        print("No data found.")

if __name__ == "__main__":
    main()

```
