```.py
import time
import requests
import Adafruit_DHT
from datetime import datetime

DHT_SENSOR = Adafruit_DHT.DHT11
DHT_PIN = 4
SENSOR_ID = 26
SERVER_URL = "http://192.168.4.137/reading/new"

# Define the login credentials for accessing the server
USERNAME = "noah"
PASSWORD = "aiobahn"

# Function to obtain an access token for authentication with the server
def get_access_token():
    # Create a dictionary containing the login credentials
    login_data = {"username": USERNAME, "password": PASSWORD}
    
    # Send a POST request to the login endpoint with the credentials
    response = requests.post("http://192.168.4.137/login", json=login_data)
    
    # Extract and return the access token from the response
    return response.json().get("access_token")

# Get the access token before starting data collection
access_token = get_access_token()

# Create a dictionary containing the authorization header with the access token
headers = {"Authorization": f"Bearer {access_token}"}

# Start the continuous data collection process
try:
    while True:
        # Read humidity and temperature from the DHT11 sensor
        humidity, temperature = Adafruit_DHT.read_retry(DHT_SENSOR, DHT_PIN)
        
        # Get the current timestamp in ISO 8601 format (e.g., "2024-12-04T18:35:00")
        current_time = datetime.now().isoformat()

        # Check if the sensor reading was successful
        if humidity is not None and temperature is not None:
            # Create a payload (dictionary) for the temperature reading
            payload = {
                "datetime": current_time,       # Timestamp of the reading
                "sensor_id": SENSOR_ID,         # Unique sensor ID
                "value": round(temperature, 1)  # Temperature value rounded to 1 decimal place
            }

            # Send the temperature data to the server via a POST request
            requests.post(SERVER_URL, json=payload, headers=headers)
            print(f"Temp Sent: {payload}")      # Print a confirmation message with the sent payload

            # Create a payload for the humidity reading
            humidity_payload = {
                "datetime": current_time,        # Timestamp of the reading
                "sensor_id": SENSOR_ID,          # Unique sensor ID
                "value": round(humidity)         # Humidity value rounded to the nearest whole number
            }

            # Send the humidity data to the server via a POST request
            requests.post(SERVER_URL, json=humidity_payload, headers=headers)
            print(f"Humidity Sent: {humidity_payload}")  # Print a confirmation message with the sent payload

        # Wait for 5 seconds before taking the next reading
        time.sleep(5)

# Stop the data collection process when the user presses Ctrl+C
except KeyboardInterrupt:
    print("\nData collection stopped.")  # Print a message indicating that data collection has stopped

```
