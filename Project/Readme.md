![image](https://github.com/user-attachments/assets/1f39e71d-9d2a-4e8f-a032-ac97bb7419ff)

# Unit 2: Optimizing Indoor Climate for Energy Efficiency and Environmental Sustainability in Karuizawa
**Noah Hoffman**

## **Criteria A: Planning**

## **Problem Definition**

The Karuizawa Town Hall has recently announced an engagement in power consumption reduction toward decreasing the environmental impact for the purpose of keeping a comfortable environment in the region. Being a town facing cold winters, with significant indoor climate fluctuations, questions of energy efficiency have become of greater importance to both the government and the residents. Indoor temperature and humidity have been found to be greatly influential on energy efficiency and the comfort of Karuizawa residents, especially in winter seasons when heating systems are in heavy use.
Most households use inefficient heating and cooling systems, which, when combined with a lack of awareness about simple power conservation practices-such as ensuring that windows and doors are closed-can lead to unnecessary energy consumption and increased carbon emissions. These inefficiencies contribute to higher energy bills for residents and further exacerbate the environmental impact through excess power usage.

The above challenge provokes my interest in assessing the changes in indoor environmental conditions within residential homes and determines specific factors that result in energy inefficiencies. I will carry out a continuous temperature and humidity monitoring effort to derive a well-documented, data-driven conclusion from the investigation. The objective will be to provide feasible, actionable recommendations for the improvement of power consumption that can aid in improving energy efficiency and the protection of the environment.

My project involves the collection of real-time environmental data by using some cost-effective, reliable tools such as DHT11 sensors and Raspberry Pi. The system, over a period of 48 hours, will record the temperature and humidity at periodic intervals with a great deal of detail about the indoor climate. This will be done through automated data collection to minimize errors and ensure that consistency is maintained without necessarily going through the cumbersome work of manual recording.

Also, it will take into consideration different factors like the on/off status of heating systems, the status of windows and doors, and the weather outside the building to detect anomalies and patterns in the data. For instance, if the heating systems are left on for long periods or if the window is accidentally left open, these events can drastically affect indoor temperatures and result in wasted energy. By analyzing these, the study will be able to find out specific causes of energy inefficiency and suggest necessary solutions for their improvement.

The proposed solution is very affordable and simple, considering most households function on a very tight budget. The DHT11 sensor, for example, costs less than $5 USD and can deliver acceptable precision for this purpose, covering the temperature from 0°C to 50°C and 20% to 90% in terms of humidity. The collected data would be stored in CSV and uploaded to a local server for redundancy and ease of access.

In furtherance of enhancing the usefulness of this project, the information collected will be visualized using graphs and charts created with Python's library, Matplotlib. These visualizations will draw out trends, anomalies, and inefficiencies in heating and cooling practices. Presenting this information in a format that is easy to understand allows the residents to quickly comprehend where energy is being wasted and make informed improvements in their energy usage.

This investigation also considers long-term sustainability and adaptability. The system is designed to be scalable and maintainable, allowing for enhancements and modifications in the future if needed. For example, it could include extra sensors or more sophisticated data analysis methods to gain even deeper insights.

In summary, this project addresses the need for optimizing indoor climate conditions in Karuizawa homes by leveraging affordable technology and data-driven analysis. Through continuous monitoring, analysis, and clear recommendations, the goal is to reduce energy consumption, lower carbon emissions, and promote a more sustainable living environment for the community.


## **Proposed Solution**

Considering the client’s needs and budgetary constraints, an effective solution involves using the DHT11 sensor to monitor temperature and humidity levels in residential rooms over a 48-hour period. The DHT11 sensor, priced at under $5 USD, offers adequate precision (Temperature Range: 0°C to 50°C [well within the realistic range], Humidity Range: 20% to 90%) and uses simple SPI communication, making it suitable for large-scale deployment.
Here's a revised version of your solution components section, incorporating the use of the Flask library, a 5-second data collection interval, data upload to a local server, and graph analysis with Matplotlib. This is formatted for a professional Google Doc or project report:

### **Components of the Solution: Data Collection**

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


## **Design Statement**

*Our team is developing a Python-based system using a DHT11 sensor to monitor indoor temperature and humidity levels. Data will be recorded over 48 hours and stored in a CSV database. The goal is to identify fluctuations in indoor conditions and provide data-driven solutions to optimize power consumption in Karuizawa homes.*

## **Success Criteria**

### **Visual Representation**

- **Graphs** illustrating temperature and humidity trends over 48 hours.

**Issue Tackled**: Identifying trends in environmental conditions to optimize energy use.

### **Data Collection and Storage**

- **Every 5 Minutes**: Temperature and humidity readings logged in CSV format.

**Issue Tackled**: Ensuring consistent and accurate data logging.

### **Mathematical Modeling**

- **Linear Models** to analyze trends and predict future conditions.

**Issue Tackled**: Accurate analysis for identifying inefficiencies.

### **Comparative Analysis**

- **Insights**:  
  - **Mean**  
  - **Standard Deviation**  
  - **Min/Max Values**  
  - **Median**  

**Issue Tackled**: Comprehensive data insights for climate optimization.

### **Prediction**

- **12-Hour Forecast** based on 48-hour data.

**Issue Tackled**: Anticipating conditions to optimize energy use.

### **Poster Presentation**

- **Summary**: Visual representations, insights, and recommendations.

**Issue Tackled**: Effective communication with stakeholders.

---

## **TOK Connection Questions**

1. **Technological Limitations**: How do they affect the accuracy of environmental data?  
2. **Ethical Responsibilities**: What are the implications of collecting data from private spaces?  
3. **Contextual Influence**: How does context impact the interpretation of indoor climate data?

---

## **Criteria B: Design**

### **System Diagram (SL)**

![image](https://github.com/user-attachments/assets/729b0e92-5b97-4fcf-ae8b-1104378d28f6)
*Fig. 1: SL System Diagram*

---

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

## **Criteria C: Development**

### **Techniques Used**

1. **Python Functions** for modular design  
2. **Dictionaries & Lists** to store sensor data  
3. **For Loops and While Loops** for data collection  
4. **Try and Except** for error handling  
5. **SQLite Database** for data storage  
6. **Flask API** for real-time data access  
7. **Requests Library** for server communication  
8. **Matplotlib** for data visualization  
9. **CSV File Handling** for backups  

---

## **Code Implementation**

### **Data Collection Script**

```python
import time
import requests
import Adafruit_DHT
from datetime import datetime

DHT_SENSOR = Adafruit_DHT.DHT11
DHT_PIN = 4
SENSOR_ID = 26
SERVER_URL = "http://192.168.4.137/reading/new"
USERNAME = "noah"
PASSWORD = "aiobahn"

def get_access_token():
    login_data = {"username": USERNAME, "password": PASSWORD}
    response = requests.post("http://192.168.4.137/login", json=login_data)
    return response.json().get("access_token")

access_token = get_access_token()
headers = {"Authorization": f"Bearer {access_token}"}

try:
    while True:
        humidity, temperature = Adafruit_DHT.read_retry(DHT_SENSOR, DHT_PIN)
        current_time = datetime.now().isoformat()

        if humidity is not None and temperature is not None:
            payload = {"datetime": current_time, "sensor_id": SENSOR_ID, "value": round(temperature, 1)}
            requests.post(SERVER_URL, json=payload, headers=headers)
            print(f"Temp Sent: {payload}")

            humidity_payload = {"datetime": current_time, "sensor_id": SENSOR_ID, "value": round(humidity)}
            requests.post(SERVER_URL, json=humidity_payload, headers=headers)
            print(f"Humidity Sent: {humidity_payload}")

        time.sleep(5)
except KeyboardInterrupt:
    print("\nData collection stopped.")
