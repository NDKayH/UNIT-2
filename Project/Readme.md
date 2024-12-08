# Unit 2: Optimizing Indoor Climate for Energy Efficiency and Environmental Sustainability in Karuizawa
**Noah Hoffman**

## **Criteria A: Planning**

## **Problem Definition**

The Karuizawa Town Hall has recently announced its commitment to reducing power consumption, promoting sustainability. Research shows that indoor temperature and humidity levels significantly impact energy efficiency and residents’ comfort, especially in winter. Inefficient heating and cooling systems, combined with a lack of awareness about power conservation (like ensuring windows and doors are closed), lead to unnecessary energy consumption and increased carbon emissions.

**Challenge**: Identify fluctuations in indoor environmental conditions causing energy inefficiencies and provide a comprehensive, data-driven solution for optimizing power consumption.

## **Proposed Solution**

### **Components of the Solution**

### **Data Collection**

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

---

### **Identifying Energy Inefficiencies**

- **Insights**:
  - Overuse of heating systems during mild temperatures  
  - Excessive air conditioning caused by high humidity  
  - Inconsistent temperature control due to external factors  

**Note**: Heaters set to level 3 (out of 5), and air conditioning turned off.

---

## **Recommendations**

Based on the analysis, practical solutions include:

- **Improving Ventilation** to regulate indoor climate naturally  
- **Adjusting Thermostat Settings** for energy efficiency  
- **Using Humidifiers/Dehumidifiers** for optimal humidity  
- **Periodic Monitoring** for ongoing optimization

---

### **Technical Stack**

- **Data Collection**: Python, DHT11 Sensor  
- **Data Visualization**: Matplotlib, NumPy  
- **Data Storage**: CSV, Local Server  

---

## **Design Statement**

*Our team is developing a Python-based system using a DHT11 sensor to monitor indoor temperature and humidity levels. Data will be recorded over 48 hours and stored in a CSV database. The goal is to identify fluctuations in indoor conditions and provide data-driven solutions to optimize power consumption in Karuizawa homes.*

---

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
