![image](https://github.com/user-attachments/assets/1f39e71d-9d2a-4e8f-a032-ac97bb7419ff)

# Unit 2: Optimizing Indoor Climate for Energy Efficiency and Environmental Sustainability in Karuizawa
**Noah Hoffman**

## **Criteria A: Planning**

## **Problem Definition**

The Karuizawa Town Hall has recently announced its commitment to reducing power consumption which will hopefully reduce the environmental impact in Karuizawa, promoting sustainability. Research has shown that indoor temperature and humidity levels significantly impact energy efficiency and Karuizawa residents’ comfort, especially in the winter seasons. Inefficient heating and cooling systems in combination with a lack of awareness about the benefits of power conservation in the form of making sure windows and doors are closed in homes can lead to unnecessary energy consumption and increased carbon emissions. The challenge given to me by the Mayor of Karuizawa is to identify the fluctuations in indoor environmental conditions in homes that could potentially cause energy inefficiencies and provide a comprehensive data-driven conclusion that suggests solutions for optimizing power consumption. 

## **Proposed Solution**

Considering the client’s needs and budgetary constraints, an effective solution involves using the DHT11 sensor to monitor temperature and humidity levels in residential rooms over a 48-hour period. The DHT11 sensor, priced at under $5 USD, offers adequate precision (Temperature Range: 0°C to 50°C [well within the realistic range], Humidity Range: 20% to 90%) and uses simple SPI communication, making it suitable for large-scale deployment.

My project will  take into consideration different factors like the on/off status of heating systems, the status of windows and doors, and the weather outside the building to detect anomalies and patterns in the data. For instance, if the heating systems are left on for long periods or if the window is accidentally left open, these events can drastically affect indoor temperatures and result in wasted energy. By analyzing these, the study will be able to find out specific causes of energy inefficiency and suggest necessary solutions for their improvement.

The proposed solution is very affordable and simple, considering most households function on a very tight budget. The DHT11 sensor, for example, costs less than $5 USD and can deliver acceptable precision for this purpose, covering the temperature from 0°C to 50°C and 20% to 90% in terms of humidity. The collected data would be stored in CSV and uploaded to a local server for redundancy and ease of access.

This investigation also considers long-term sustainability and adaptability. The system is designed to be scalable and maintainable, allowing for enhancements and modifications in the future if needed. For example, it could include extra sensors or more sophisticated data analysis methods to gain even deeper insights.

## **Success Criteria**

1. The solution will be able to display clear, accurate graphs depicting **temperature** and **humidity** trends in residential homes over a duration of **48 hours**.
2. The indoor environment variables will be successfully measured with a **DHT11 sensor** connected to a **Raspberry Pi 4 Model B**.
3. Data read by the DHT11 sensor will be:
   * **Stored Locally** in a CSV file for easy access and backup.
   * **Uploaded to a Local Server** in real time to ensure data redundancy and avoid data loss during power outages.
4. A detailed **poster** will be prepared to summarize the project findings. This shall include:
   * Graphical representation of temperature and humidity trends
   * Key observations from mathematical modeling and comparative analysis
   * Practical recommendations on enhancing energy efficiency

## **TOK Connection**

### **Technology and Environmental Understanding**

Application of sensors provides accurate and continuous information which, otherwise, cannot be collected manually due to fatigue and impracticability. There are also limitations to all good things, such as incurring sensor errors. This can, to a large extent be minimised by crosschecking data with other sensors or corroborating the data manually.

### **Responsibilities in Handling Personal Data**

Data collection from private homes needs consent and ethical treatment. The digital data can easily be copied and misused; hence, the security and privacy of data collected are important for sustaining trust and respect for residents' rights.

### **Cultural and Contextual Factors in Data Interpretation**

These might be due to the way the data is interpreted through various cultural and contextual biases. For example, comfort and the levels of acceptable temperature may differ between households. There is a potential for analysis bias leading to a conclusion that does not correctly depict the residents' experience or needs.

## **Components of the Solution:**

The core of the data collection process involves capturing temperature and humidity readings using the DHT11 sensor using a Raspberry Pi 4 Model B. This process ensures continuous and precise data logging.

#### **Hardware Solution**

- **Device(s)**:  
  - **Raspberry Pi 4 Model B**  
    - Cost-effective (< ¥6000)  
    - Modular/expandable, programmable  
  - **DHT11 Sensor**  
    - Cost-effective (< ¥1000)  
    - Easy to use and program  

#### **Software Solution**

- **Python Script**: Captures temperature and humidity readings every 5 seconds.  
- **CSV**: Stores readings locally in a `.csv` file.  
- **Real-Time Upload**: Data uploaded to a local server using HTTP requests.

### **Data Analysis and Visualization**

- **Graph Generation** (using Matplotlib):
  - **Temperature Trends** over time  
  - **Humidity Patterns** and fluctuations  
  - **Comparative Analysis** with other local sensors  

- **Trend Analysis**:
  - Detect excessive heating/cooling  
  - Identify high humidity levels causing increased air conditioning use

### **Technical Stack**

- **Data Collection**: Python, DHT11 Sensor  
- **Data Visualization**: Matplotlib, NumPy  
- **Data Storage**: CSV, Local Server  

### **Prediction**

- **Linear and Quadratic Model** based on 48-hour data.

**Issue Tackled**: Anticipating conditions to optimize energy use.

### **Poster Presentation**

- **Summary**: Visual representations, insights, and recommendations.

**Issue Tackled**: Effective communication with stakeholders

## **Criteria B: Design**

### **System Diagram (SL)**

![image](https://github.com/user-attachments/assets/729b0e92-5b97-4fcf-ae8b-1104378d28f6)
*Fig. 1: SL System Diagram*

### **Flow Charts**

![image](https://github.com/user-attachments/assets/e2623887-c2ae-482c-8b22-b53e326c2965)

This Flow chart illustrates the autentication process using the 'requests' library, meant to allow one to eventually access the stored data in the local server. 

![image](https://github.com/user-attachments/assets/90e557b4-9d6e-40ec-83d7-5c051c4d3cdc)

This flow chart illustrates the DHT-11 Data Collection Process, from the recognition of the sensor to the collection of data to the sending the data to the server online

![image](https://github.com/user-attachments/assets/8a2d70d6-64c3-45c1-b612-777cf66625b0)
![image](https://github.com/user-attachments/assets/daf76177-5279-4cb9-9399-2630eecba897)

This flow chart illustrates the procces by which I extracted data from the server and stored my sensor's data in a .csv file.

## **Record of Tasks**

| **Task No** | **Planned Action**                     | **Planned Outcome**                      | **Time Estimate** | **Target Date** | **Criterion** |
|-------------|-----------------------------------------|------------------------------------------|------------------|----------------|--------------|
| 1           | Write Problem Definition               | Clear project scope articulation         | 15 minutes       | Nov 22          | A            |
| 2           | Develop Data Collection Script         | Python script for sensor data logging    | 2 hours          | Nov 27          | B            |
| 3           | Create Response Script for Real-Time Access | Web interface for accessing data     | 2 hours          | Nov 29          | B            |
| 4           | Create Test Graphs                     | Analyze data with Matplotlib             | 1 hour           | Nov 29          | C            |
| 5           | Develop Visualizations                 | Graphs of collected data                 | 2 hours          | Dec 7           | C            |
| 6           | Create Project Poster                  | Summarize findings                       | 1 hour           | Dec 8           | D            |

---

| **Test No.** | **Test Type**              | **Description**                                                                                     | **Procedure**                                                                                                                          | **Expected Outcome**                                                                                                        | **Criteria** |
|--------------|----------------------------|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|--------------|
| 1            | Functional: Sensor Reading | Check that the DHT11 sensor reads temperature and humidity accurately.                             | Run the data collection script from the local pi.                                                                                      | Temperature and humidity readings are not fluctuating unrealistically.                                                    | B            |
| 2            | Functional: Data Logging   | Ensure data is being saved to the CSV file correctly. (sent to a placeholder '.csv')                | Run the script for 5 minutes and check the CSV file for accurate entries.                                                             | Data entries in the CSV match the real-time sensor readings.                                                               | B            |
| 3            | Functional: Server Upload  | Verify that temperature and humidity data are uploaded to the server successfully.                 | Run the script and check the local server's database for new entries corresponding to the sensor's readings.                         | Data appears correctly.                                                                                                     | B            |
| 4            | Functional: Data Redundancy| Check if data is stored both locally and on the server.                                            | Disconnect the server and ensure data is saved locally, then reconnect and check for data upload.                                     | Data is saved in the '.csv' during disconnection and uploaded to the server once reconnected.                              | B            |
| 5            | Non-Functional: Load Testing | Test how the system handles extended data collection over 48 hours.                                | Run the script continuously for 48 hours and monitor performance.                                                                     | System runs without crashes or data loss, and data is logged correctly throughout.                                         | C            |

### **Key Criteria References**

- **B**: Data Collection and Storage  
- **C**: Data Analysis and Visualization  
- **D**: Presentation and Communication of Results  

## **Criteria C: Development**

### **Techniques Used**

1. **Python Functions** for design  
2. **Dictionaries & Lists** to store sensor data  
3. **For Loops and While Loops** for data collection  
4. **Try and Except** for error handling  
5. **`.csv` Files** for data storage  
6. **API** for real-time data access  
7. **Requests Library** for server communication  
8. **Matplotlib** for data visualization  

---

## **Code Implementation**

### **Data Collection Script**

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

Before actual data collection starts, the script performs the following setup:

1. **User Authentication**

- The function `get_access_token()` provides an **access token** which is retrieved by sending a POST request to the server with the provided **username** and **password**. 
   - The access token should be used for authentication when uploading data to the server subsequently.
2. **Headers Configuration**: 

   - The token was placed in the **headers** to communicate securely with the server.
#### **Continuously Collecting Data Loop

The script does use a `while True:` loop to collect data every **5 seconds continuously.** This ensures the smooth running of the system all the time for minute capture of temperature and humidity fluctuation. The process involves, in each iteration of the loop:

1. **Sensor Data Reading**  

   - Temperature and Humidity readings by the script are obtained from the DHT11 sensor with the help of `Adafruit_DHT.read_retry(DHT_SENSOR, DHT_PIN)`.

2. **Timestamp Generation**

- The current timestamp is recorded in **ISO 8601 format** using `datetime.now().isoformat()`.

3. **Data Upload to Server** 

   - If the sensor readings are valid (i.e., not `None`), the script creates two payloads:  
     - **Temperature Payload**: Contains the timestamp, sensor ID, and temperature value (rounded to one decimal place).
- **Humidity Payload**: It contains the timestamp, sensor ID, and humidity value rounded to the nearest whole number.  
   - Each payload is sent to the server over a **POST request**.
  
4. **Local CSV Storage**:  

   - The data also gets printed to the console for easy monitoring at runtime.
5. **Delay Between Readings**

- A **5-second delay** is added using `time.sleep(5)` to manage the frequency of data collection.
  
### **Reasoning for the `while True` Loop**

The continuous `while True` loop is essential for maintaining uninterrupted data collection. This approach is beneficial because:

1. **Robustness to Errors**:

- If the server has an issue or the sensor is disconnected, the loop allows the system to fast **resume data collection** once the issue is fixed.
  
2. **Keep the loop simple**: 

   - Avoiding adding conditional checks in the loop means that no **computational overhead** can be added and the potential failure points are reduced.

```.py

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
```

#### **Data Redundancy and Reliability**

To be sure the data is collected, the script uses **double storage**:

1. **Local CSV Storage**: 

   - The fact that data is stored in a local repository will not imply any loss of data resultant from **network connectivity problems**.
     
2. **Server Upload**: 

   - Real-time recording of data on a **local server** to gain redundancy and make access easy to the most recent record.
This way, no matter which storage fails to work, data remains available with the continuity of recording unaffected.

**Benefits for Energy Efficiency Optimization**

1. **Quick Recovery**:  

   - This minimizes the amount of time the device is down and ensures that crucial fluctuations in temperature and humidity are captured accurately.
     
2. **Continuous Data Recording**:  

   - The recording allows for detailed insight into potential inefficiencies in **heating and cooling systems**.
3. **Efficient Data Storage:

- Both local and server-based storage maintains **data integrity** to support reliable analysis for optimizing power consumption.
  
#### **Overall Impact**

This code contributes to the project's aim of identifying and reducing **energy inefficiencies** in homes at Karuizawa. By harnessing continuous data collection, redundancy, and reliable storage, the solution contributes to:

- **Sustainability**  

- **Reduced Carbon Emissions**  
- **Improved Energy Efficiency**

This approach allows residents to make informed choices to optimize their indoor climate and support environmental sustainability.

## **Predictions**

![output](https://github.com/user-attachments/assets/3d1ed652-645f-4261-b709-eb9d6eb3842b)

1. **Graph 1: Temperature vs Humidity Quadratic Fit**
This graph illustrates the relationship between humidity and temperature readings collected over a 48-hour period. The blue dots represent the actual temperature data, while the red line shows the predictions made by the quadratic model. This model attempts to fit a quadratic curve to capture the relationship between humidity and temperature. However, the low R² value indicates that humidity is not a strong predictor of temperature, suggesting that temperature changes are significantly influenced by other factors. Additionally, the variability in the data has led to a situation where even the quadratic model struggles to accurately represent the relationship between these variables.

![49e76f97-fcf1-4466-9649-bd8357a05fad](https://github.com/user-attachments/assets/c285487e-b9eb-449d-83cb-b4d6d2c1d7d9)

2. **Graph 2: Temperature Predictions Over Time**
This graph displays the actual temperature readings (blue dots) alongside the predicted values (red line) generated by a quadratic model that utilized both time (timestamp) and humidity as predictors. The model aims to track the temperature trend throughout the 48-hour period. However, the model's low R² score and high MSE reveal that the predictions do not closely match the actual values. This limitation suggests that the basic quadratic model may not effectively account for the temperature fluctuations over time, potentially due to the absence of other influencing factors such as atmospheric pressure, sensor inaccuracies, or changes in the external environment.

### Limitations of the Model
1. **Simplistic Assumptions**:
The quadratic model relies on a straightforward polynomial relationship between temperature and the predictors, humidity and time, which may not accurately represent reality due to the presence of multiple influential variables.

2. **Limited Features**:
Only humidity and timestamp have been considered as predictors. Temperature variations could be affected by additional factors such as atmospheric pressure, weather conditions, sunlight exposure, and sensor variability, none of which have been taken into account here.

## **Data Visualization Code:**

```.py

# Import necessary libraries for data visualization and analysis
from matplotlib import pyplot as plt
import matplotlib
import pandas as pd
import numpy as np
from myLib import moving_average  # Custom function for smoothing data

# Set the style for the plots
plt.style.use('ggplot')  # Use the 'ggplot' style for a clean aesthetic
matplotlib.use('MacOSX')  # Fix for macOS compatibility issues with matplotlib

# Load CSV file containing sensor data
data = pd.read_csv('/Users/noahhoffman/UWCISAK/Projects/Unit2.2/raw_readings.csv')

# Extract temperature and humidity data specifically for sensor_id 26
temp = data[data['sensor_id'] == 26]['value'].tolist()  # List of temperature values
hum = data[data['sensor_id'] == 26]['humidity'].tolist()  # List of humidity values

# Create x-axis ranges for temperature and humidity data points collected every 5 seconds (48 hours)
temp_x = list(range(len(temp)))
hum_x = list(range(len(hum)))

# Downsampling data to reduce clutter and improve readability of graphs
downsample_step = 100  # Take every 100th data point
temp_downsampled = temp[::downsample_step]
hum_downsampled = hum[::downsample_step]
temp_x_downsampled = temp_x[::downsample_step]
hum_x_downsampled = hum_x[::downsample_step]

# Apply moving average to smooth out fluctuations in temperature and humidity data
window_size = 50  # Window size for smoothing
temp_smoothed = moving_average(windowSize=window_size, x=temp_downsampled)
hum_smoothed = moving_average(windowSize=window_size, x=hum_downsampled)

# Ensure the x-axis ranges match the lengths of the smoothed data
temp_x_smoothed = temp_x_downsampled[:len(temp_smoothed)]
hum_x_smoothed = hum_x_downsampled[:len(hum_smoothed)]

# Perform linear regression to fit a line to the temperature data
temp_slope, temp_intercept = np.polyfit(temp_x_downsampled, temp_downsampled, deg=1)
temp_linear = [temp_slope * x + temp_intercept for x in temp_x_downsampled]

# Perform linear regression to fit a line to the humidity data
hum_slope, hum_intercept = np.polyfit(hum_x_downsampled, hum_downsampled, deg=1)
hum_linear = [hum_slope * x + hum_intercept for x in hum_x_downsampled]

# Create a figure with two subplots for temperature and humidity
fig, axs = plt.subplots(2, 1, figsize=(15, 10), dpi=100, sharex=True)  # 2 rows, 1 column, shared x-axis

# Plot temperature data
axs[0].plot(temp_x_downsampled, temp_downsampled, color='green', marker='x', linestyle='-', 
            markersize=4, linewidth=1, alpha=0.5, label='Raw Temperature')
axs[0].plot(temp_x_smoothed, temp_smoothed, color='black', linewidth=2, label='Smoothed Temperature')
axs[0].plot(temp_x_downsampled, temp_linear, color='purple', linestyle='--', linewidth=2, label='Linear Model')

# Customize the temperature plot
axs[0].set_title("Temperature Readings", fontsize=18, fontweight='bold')  # Title for the plot
axs[0].set_ylabel("Temperature (°C)", fontsize=14)  # Y-axis label
axs[0].grid(True, linestyle='--', alpha=0.5)  # Add grid lines for better readability
axs[0].legend(fontsize=12)  # Display legend for temperature plot

# Plot humidity data
axs[1].plot(hum_x_downsampled, hum_downsampled, color='blue', marker='o', linestyle='-', 
            markersize=4, linewidth=1, alpha=0.5, label='Raw Humidity')
axs[1].plot(hum_x_smoothed, hum_smoothed, color='red', linewidth=2, label='Smoothed Humidity')
axs[1].plot(hum_x_downsampled, hum_linear, color='purple', linestyle='--', linewidth=2, label='Linear Model')

# Customize the humidity plot
axs[1].set_title("Humidity Readings", fontsize=18, fontweight='bold')  # Title for the plot
axs[1].set_ylabel("Humidity (%)", fontsize=14)  # Y-axis label
axs[1].set_xlabel("Time (Seconds)", fontsize=14)  # X-axis label
axs[1].grid(True, linestyle='--', alpha=0.5)  # Add grid lines for better readability
axs[1].legend(fontsize=12)  # Display legend for humidity plot

# Adjust layout to prevent overlap and display the plots
plt.tight_layout()
plt.show()

```



## **Result (Raw Data)**

![image](https://github.com/user-attachments/assets/b0c364ea-146d-45a9-930d-48f85d5d09ab)

I made the graph viewable by using **`axs`**, which allows a single figure to have multiple subplots. I used the `fig, axs = plt.subplots(2, 1, figsize=(15, 10), dpi=100)` to provide two vertically stacked subplots where they share the same x-axis, with **`axs[0]`** containing the humidity data and **`axs[1]`** containing the temperature. I used a moving average with a window size of 50 to smooth out noise in both datasets then downsampled by displaying every 100th data point to make them easier to read. This maintained general patterns while emphasizing trends more explicitly. Higher resolution was achieved by increasing the figure size and DPI, making details more clearly observable. Different colors, markers, thicker lines for the smoothed data, grid lines, bold titles, and unambiguous axis labels were added to each subplot. **`plt.tight_layout()`** was added to make sure that the subplots were spaced optimally, did not overlap, and were therefore easier to read. Together, these adjustments provide the visualization clarity, simplicity, and ease of interpretation.

I also used a moving average visualization to smooth data. This was a function stored in a separate `.py` file called `myLib.py`

```.py

def moving_average(windowSize:int, x:list)->list:
    x_smoothed = []
    for i in range(0, len(x)-windowSize):
        x_section = x[i:i+windowSize]
        x_average = sum(x_section)/windowSize

        x_smoothed.append(x_average)

    return x_smoothed

```



* Linear Regression Calculation:
    * `np.polyfit()` fits a linear model `(degree=1)` to the temperature data.
    * It returns te slope and intercept of the best-fit line.
    
* Generating Predictions:
    * The list comprehension computes the predicted temperature values (`temp_linear`) using the equation:
    * `Prediction=(slope×x)+intercept\text{Prediction} = (\text{slope} \times x) + \text{intercept}Prediction=(slope×x)+intercept`

* **How It Helps:** This allows you to visualize trends and identify if temperatures are rising or falling over time.

```.py
temp_slope, temp_intercept = np.polyfit(temp_x_downsampled, temp_downsampled, 1)
temp_linear = [temp_slope * x + temp_intercept for x in temp_x_downsampled]
```

## **Data Analysis**

The data gathered over a 48-hour period using the DHT11 sensor offers valuable insights into the temperature and humidity conditions of the monitored space. The main objective of this analysis was to pinpoint fluctuations in indoor environmental conditions that could result in energy inefficiencies and to assess whether these conditions meet optimal standards for energy conservation and environmental sustainability.

**Temperature Analysis:**  
The data shows that temperature levels vary significantly due to factors such as the operation of heating systems, the status of windows and doors, and external weather conditions. For example, instances where heating systems were left running for long periods resulted in higher indoor temperatures, while open windows caused rapid drops in temperature. These irregularities indicate that improved management of these factors could enhance energy efficiency. The temperature readings typically range from 0°C to 50°C, which is consistent with the DHT11 sensor’s specifications. However, the observed spikes and drops in temperature suggest potential inefficiencies that, if addressed, could lead to reduced energy consumption and lower carbon emissions.

**Humidity Analysis:**  
The humidity data collected varied between 20% and 90%, which aligns with the capabilities of the DHT11 sensor. Humidity levels also changed based on whether windows were open and the operation of heating systems. For instance, when windows were left open, humidity levels decreased, whereas closed environments with active heating systems retained higher humidity. These results underscore the importance of maintaining optimal humidity levels to ensure comfort and minimize unnecessary energy use.

**Identified Patterns and Anomalies:**  
The analysis revealed patterns where inefficient heating practices and open windows caused notable fluctuations in temperature and humidity. These inefficiencies lead to increased energy consumption and a greater environmental impact. Anomalies were detected.

## **Analysis and Conclusion**

From the data collected over a 48-hour period, it is evident that indoor temperature and humidity can be easily influenced by factors such as the condition of windows and doors, the operation of heating systems, and the current weather. These factors reveal trends in inefficiencies, including significant energy waste during prolonged heating system use and issues with unsealed windows and doors.

Mathematical models like linear regression and moving averages are effective tools for analyzing trends in indoor climate conditions and can help predict future changes. By using these models, households can anticipate shifts in temperature and humidity, allowing them to adjust their heating or cooling schedules accordingly. This predictive ability supports proactive energy management, helping residents optimize power usage and reduce unnecessary carbon emissions. The proposed solution is cost-effective and can be easily implemented with a DHT11 sensor and Raspberry Pi, making it scalable for widespread use in homes throughout Karuizawa.

Given these findings, the I strongly recommend that a community-wide initiative be launched through the Karuizawa Town Hall to promote awareness of energy-saving practices. This program should encourage the installation of basic monitoring systems for indoor temperature and humidity, provide guidelines for sealing windows and doors, and suggest efficient heating schedules. These measures will play a significant role in helping Karuizawa reduce power consumption and minimize its environmental impact while fostering a culture of sustainability among its residents.

## **Recommendations**

Integrate additional sensors by adding various types of sensors, such as CO₂ sensors, motion detectors, and light sensors, to gain a more complete picture of indoor climate conditions. This can help uncover relationships between air quality, occupancy, and energy consumption. Improve data logging frequency by increasing how often data is collected to capture more detailed fluctuations in temperature and humidity. This will provide deeper insights into short-term changes and help pinpoint subtle inefficiencies. Tackle connectivity issues with network stability enhancements by utilizing a more dependable network or implementing offline data storage that syncs with the server once the connection is restored. This ensures that no data is lost during disconnections. 

## **Sources**

- **Matplotlib Documentation**:  
  Comprehensive guide for creating visualizations and graphs in Python.  
  - *Website*: [https://matplotlib.org/stable/contents.html](https://matplotlib.org/stable/contents.html)

- **NumPy Documentation**:  
  Essential for performing mathematical operations, array manipulations, and data analysis.  
  - *Website*: [https://numpy.org/doc/](https://numpy.org/doc/)

- **Requests Library Documentation**:  
  For handling HTTP requests to interact with servers (e.g., data uploads).  
  - *Website*: [https://docs.python-requests.org/en/latest/](https://docs.python-requests.org/en/latest/)

- **Stack Overflow**:  
  A community-driven forum for troubleshooting code issues and finding best practices.  
  - *Website*: [https://stackoverflow.com/](https://stackoverflow.com/)

- **Kaggle**:  
  Community for data science, where you can find datasets and examples for data analysis and visualization.  
  - *Website*: [https://www.kaggle.com/](https://www.kaggle.com/)

- **Github Repositories**:  
  Search for repositories containing DHT11 sensor implementations and Python data visualization scripts.  
  - *Website*: [https://github.com/search?q=DHT11+Python](https://github.com/search?q=DHT11+Python)

- **Open Source Data Visualization Repositories**:  
  Repositories demonstrating the use of Matplotlib, Seaborn, and Plotly for visualizing sensor data.  
  - *Website*: [https://github.com/topics/data-visualization](https://github.com/topics/data-visualization)

- **YouTube Channels**:  
  - **Programming with Mosh**: Tutorials on Python coding and best practices.  
    - *Channel*: [https://www.youtube.com/c/programmingwithmosh](https://www.youtube.com/c/programmingwithmosh)  
  - **Tech with Tim**: Python, Raspberry Pi, and sensor projects.  
    - *Channel*: [https://www.youtube.com/c/TechWithTim](https://www.youtube.com/c/TechWithTim)  
  - **Corey Schafer**: Detailed Python tutorials, including data visualization.  
    - *Channel*: [https://www.youtube.com/c/Coreyms](https://www.youtube.com/c/Coreyms)

- **Reddit Communities**:  
  - **r/Python**: 
    - *Link*: [https://www.reddit.com/r/Python/](https://www.reddit.com/r/Python/)  
  - **r/raspberry_pi**: 
 
