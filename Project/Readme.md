
Unit 2: Optimizing Indoor Climate for Energy Efficiency and Environmental Sustainability in Karuizawa
Noah Hoffman
Project Overview
Criteria A: Planning
Problem Definition
The Karuizawa Town Hall has recently announced its commitment to reducing power consumption which will hopefully reduce the environmental impact in Karuizawa, promoting sustainability. Research has shown that indoor temperature and humidity levels significantly impact energy efficiency and Karuizawa residents’ comfort, especially in the winter seasons. Inefficient heating and cooling systems in combination with a lack of awareness about the benefits of power conservation in the form of making sure windows and doors are closed in homes can lead to unnecessary energy consumption and increased carbon emissions. The challenge I have taken is to identify the fluctuations in indoor environmental conditions in homes that could potentially cause energy inefficiencies and provide a comprehensive data-driven conclusion that suggests solutions for optimizing power consumption. 

Proposed Solution
Considering the client’s needs and budgetary constraints, an effective solution involves using the DHT11 sensor to monitor temperature and humidity levels in residential rooms over a 48-hour period. The DHT11 sensor, priced at under $5 USD, offers adequate precision (Temperature Range: 0°C to 50°C [well within the realistic range], Humidity Range: 20% to 90%) and uses simple SPI communication, making it suitable for large-scale deployment.
Here's a revised version of your solution components section, incorporating the use of the Flask library, a 5-second data collection interval, data upload to a local server, and graph analysis with Matplotlib. This is formatted for a professional Google Doc or project report:

Components of the Solution

Hardware Solution
Device: Arduino UNO Microcontroller
Cost-effective (< $6 USD)
Programmable and expandable
Software Solution
The proposed software tool is Python due to its:
Open-source nature and platform independence
Ease of scalability and maintenance
High-Level Language (HLL): Automatic memory management, making it easier for developers to enhance the solution.

Data Collection
The core of the data collection process involves capturing temperature and humidity readings using the DHT11 sensor using a Raspberry Pi 4 Model B. This process ensures continuous and precise data logging.
Hardware Solution
Device(s): 
Raspberry Pi 4 Model B 
Cost-effective (<¥6000)
Modular/expandable, programmable
		DHT-11 Sensor 
Cost-effective (<¥1000)
Easily usable, programmable	
Software Solution
Python Script: A custom Python script will capture temperature and humidity readings from the DHT11 sensor every 5 seconds.
CSV: The readings will be stored locally in a .csv file for easy data access and management.
Real-Time Upload: Data will also be uploaded to a local server online using HTTP requests, enabling seamless data storage and redundancy.

Data Analysis and Visualization
Collected data will be analyzed using the Matplotlib library and associated tools to identify inefficiencies and generate meaningful insights:
Graph Generation: The script will create graphs to visualize:
Temperature Trends over time.
Humidity Patterns and fluctuations.
Comparisons between other local sensor readings
Trend Analysis: By identifying patterns in the data, the solution can pinpoint periods of:
Excessive Heating or Cooling: Detects when temperatures are maintained higher or lower than necessary.
High Humidity: Recognize situations where high humidity levels may lead to increased air conditioning use.
Identifying Energy Inefficiencies
By analyzing the data, the solution will identify specific inefficiencies in energy usage, such as:
Overuse of Heating Systems during mild temperatures 
Excessive Air Conditioning caused by high humidity levels. 
Inconsistent Temperature Control due to external environmental factors.
As a note, the heaters in the room where the sensor is located will be turned onto the 3rd level out of 5, the maximum and the air condition will be turned off by myself. If the status of these devices changes it may indicate a shift in the temperature in the room which will be used for solution proposals and will be discussed further in the analysis. 


Recommendations
Based on the insights gained from the analysis, practical recommendations will be provided to optimize energy consumption, including:
Improving Ventilation to naturally regulate indoor climate.
Adjusting Thermostat Settings to maintain energy-efficient temperature levels.
Using Humidifiers or Dehumidifiers to achieve optimal humidity levels efficiently.
Periodic Monitoring to ensure continued optimization and adjust strategies as necessary.

Technical Stack
Data Collection: Python, DHT11 Sensor, 
Data Visualization: Matplotlib, NumPy
Data Storage: .csv, Local Online Server

Design Statement
Our team is developing a Python-based system using a DHT11 sensor to monitor indoor temperature and humidity levels. Data will be recorded over 48 hours and stored in a .csv file database. The goal is to identify the fluctuations in indoor environmental conditions in homes that could potentially cause energy inefficiencies and provide a comprehensive data-driven conclusion that suggests solutions for optimizing power consumption in residences in Karuizawa.

Success Criteria
Visual Representation:
 The solution will provide clear and accurate graphs illustrating temperature and humidity trends inside a dormitory over a 48-hour period. These graphs will visually depict variations and patterns to help identify potential inefficiencies in indoor climate management.
 [Issue Tackled]: Identifying trends in environmental conditions to optimize energy use and comfort.


Data Collection and Storage:
 Temperature and humidity readings will be recorded every 5 minutes using a DHT11 sensor. The data will be stored locally in a CSV file for easy retrieval and analysis.
 [Issue Tackled]: Ensuring consistent data logging for accurate monitoring and historical analysis.


Mathematical Modeling:
 The solution will utilize linear models to analyze the collected temperature and humidity data. This will help in understanding trends and predicting future conditions based on historical data.
 [Issue Tackled]: Providing accurate analysis to identify patterns and potential inefficiencies.


Comparative Analysis:
 The collected data will be analyzed to produce comparative statistics, including:


Mean
Standard Deviation
Minimum and Maximum Values
Median
 These insights will help in understanding the range and variability of indoor conditions.
 [Issue Tackled]: Offering comprehensive data insights to identify areas for climate optimization.
Prediction:
 Based on the 48-hour data, the system will provide a 12-hour prediction for temperature and humidity trends. This forecast will help in preemptively adjusting indoor conditions to optimize energy use.
 [Issue Tackled]: Anticipating future environmental conditions to improve energy efficiency and comfort.


Poster Presentation:
 A detailed poster will be created to summarize the project findings. This will include:


Visual representations of data trends.
Insights from mathematical modeling and comparative analysis.
Practical recommendations for maintaining optimal indoor temperature and humidity.
 [Issue Tackled]: Communicating results and recommendations effectively to stakeholders.
This solution leverages CSV data storage and graphical analysis to provide actionable insights, ensuring an efficient and sustainable approach to indoor climate management.

TOK Connection Questions
How do technological limitations affect the accuracy of environmental data?


What ethical responsibilities arise when collecting data from private spaces?


How does context influence the interpretation of indoor climate data?





This solution aims to provide a comprehensive yet accessible approach to optimizing indoor climate conditions for Karuizawa Town Hall, promoting energy efficiency and environmental sustainability through reliable data collection, analysis, and visualization.

Criteria B: Design
System Diagram (SL)
Fig.1: System diagram for the proposed solution. The DHT11 sensor is connected to a Raspberry Pi, which records data and communicates with an API for real-time monitoring.

Record of Tasks
Task No
Planned Action
Planned Outcome
Time Estimate
Target Completion Date
Criterion
1
Write the Problem Definition
Clear articulation of the project’s scope
15 minutes
Nov 22
A
2
Develop Data Collection Script
Python script to log sensor data
2 hours
Nov 27
B
3
Create Response Script for Real-Time Access on Laptop
Access data via a web interface
2 hours
Nov 29
B
4


5
Create Test Graphs  


Analyze Data and Begin to Understand Problem 
Understand MatPlotLib Library 

Insights into heating/cooling inefficiencies       
1 hour


3 hours 
Nov 29


Dec 6
C


C



6
Develop Visualizations
Graphs to display collected data
2 hours
Dec 7
C
7
Create Project Poster
Summarize findings in a poster
1 hour
Dec 8
D


Criteria C: Development
Techniques Used
Python Functions for modular code design.
Dictionaries & Lists to store sensor data.
For Loops and While Loops for continuous data collection.
Try and Except for error handling.
SQLite Database for storing data.
Flask API for real-time data access.
Requests Library for communicating with the server.
Matplotlib for creating visualizations.
CSV File Handling for data backup.

Code Implementation
Data Collection Script
import time                       # Import the relevant libraries
import requests                   
import Adafruit_DHT               
from datetime import datetime     

DHT_SENSOR = Adafruit_DHT.DHT11  # Specify that we are using the DHT11 sensor
DHT_PIN = 4                      # The GPIO pin number connected to the sensor's data line
SENSOR_ID = 26                   # A unique ID for the sensor (can be adjusted as needed)

# Server details
SERVER_URL = "http://192.168.4.137/reading/new"  # The server endpoint to send data to
USERNAME = "noah"                       
PASSWORD = "aiobahn"                       

# Function to obtain an access token from the server for authentication
def get_access_token():
    login_data = {"username": USERNAME, "password": PASSWORD}  # Create login credentials as a dictionary
    response = requests.post("http://192.168.4.137/login", json=login_data)  # Send a POST request to log in
    return response.json().get("access_token")  # Extract and return the access token from the response

# Get the access token before starting data collection
access_token = get_access_token()                       # Call the function to get the access token
headers = {"Authorization": f"Bearer {access_token}"}   # Create a headers dictionary with the token for authentication

# Collect and send data every 5 seconds
try:
    while True:
        # Read humidity and temperature from the sensor
        humidity, temperature = Adafruit_DHT.read_retry(DHT_SENSOR, DHT_PIN)
        
        # Get the current time in ISO 8601 format (e.g., "2024-12-04T18:35:00")
        current_time = datetime.now().isoformat()

        # Check if the sensor reading is successful
        if humidity is not None and temperature is not None:
            # Create a payload (data packet) for the temperature reading
            payload = {
                "datetime": current_time,       # Record the current timestamp
                "sensor_id": SENSOR_ID,         # Include the sensor ID
                "value": round(temperature, 1)  # Round the temperature to 1 decimal place
            }

            # Send the temperature reading to the server
            temp_response = requests.post(SERVER_URL, json=payload, headers=headers)
            print(f"Sent Temperature: {payload}, Response: {temp_response.status_code}")

            # Create a payload for the humidity reading
            humidity_payload = {
                "datetime": current_time,        # Record the same timestamp for humidity
                "sensor_id": SENSOR_ID,          # Include the same sensor ID (update if humidity has a different sensor ID)
                "value": round(humidity)         # Round the humidity to the nearest whole number
            }

            # Send the humidity reading to the server
            humidity_response = requests.post(SERVER_URL, json=humidity_payload, headers=headers)
            print(f"Sent Humidity: {humidity_payload}, Response: {humidity_response.status_code}")
        else:
            # Print an error message if the sensor fails to retrieve data
            print(f"{current_time}, {SENSOR_ID}, Failed to retrieve data")

        # Wait for 5 seconds before taking the next reading
        time.sleep(5)

# Stop the data collection loop when the user presses Ctrl+C
except KeyboardInterrupt:
    print("\nData collection stopped.")





Server Communication
Register and Login Script
import requests
import csv
from datetime import datetime

# Server details
SERVER_URL = "http://192.168.4.137/readings" 
USERNAME = "noah"                             
PASSWORD = "aiobahn"                         

# Function to obtain an access token from the server for authentication
def get_access_token():
    login_data = {"username": USERNAME, "password": PASSWORD}  # Create login credentials as a dictionary
    response = requests.post("http://192.168.4.137/login", json=login_data)  # Send a POST request to log in
    return response.json().get("access_token")  # Extract and return the access token from the response

# Function to get data from the server
def get_readings():
    access_token = get_access_token()                            # Get the access token
    headers = {"Authorization": f"Bearer {access_token}"}        # Add token to headers
    response = requests.get(SERVER_URL, headers=headers)         # Send GET request to server
    return response.json().get("readings", [])                   # Return the list of readings

# Function to save readings to a CSV file in the desired format
def save_readings_to_csv(readings, filename):
    # Define CSV headers based on your desired format
    headers = ["datetime", "sensor_id", "value", "humidity"]

    # Write data to the CSV file
    with open(filename, mode='w', newline='') as file:
        writer = csv.DictWriter(file, fieldnames=headers)
        writer.writeheader()  # Write the header row

        # Iterate over readings and write each one to the file
        for reading in readings:
            # Assuming the server returns a dictionary with datetime, sensor_id, value, and humidity
            writer.writerow({
                "datetime": reading["datetime"],
                "sensor_id": reading["sensor_id"],
                "value": round(reading["value"], 1),
                "humidity": round(reading.get("humidity", 0))  # Default to 0 if humidity is not available
            })

# Main function to execute the script
def main():
    readings = get_readings()                      # Fetch readings from the server
    if readings:
        # Create a filename with a timestamp
        filename = f"server_readings_{datetime.now().strftime('%Y%m%d_%H%M%S')}.csv"
        save_readings_to_csv(readings, filename)   # Save the readings to a CSV file
        print(f"Readings saved to {filename}")
    else:
        print("No readings found on the server.")

# Run the script
if __name__ == "__main__":
    main()





Flow Charts
Authentication Flow

Figure 3: The flowchart describes an authentication process using the requests library.


Criteria D: Functionality
A 7-minute video demonstration showcasing the following:
Data Collection from the DHT11 sensor.
Real-Time Data Visualization via API.
Graphical Analysis of temperature and humidity.
Recommendations for optimizing energy efficiency.
[Video Link Placeholder]



Predictive Analysis:
 Use machine learning models (e.g., linear regression) to predict temperature and humidity trends more accurately.


Detailed Poster Presentation:
 Include high-quality visuals, client testimonials, and a comparison of alternative solutions to strengthen your presentation.



