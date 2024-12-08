![image](https://github.com/user-attachments/assets/1f39e71d-9d2a-4e8f-a032-ac97bb7419ff)

# Unit 2: Optimizing Indoor Climate for Energy Efficiency and Environmental Sustainability in Karuizawa
**Noah Hoffman**

## **Criteria A: Planning**

## **Problem Definition**

The Karuizawa Town Hall has recently announced its commitment to reducing power consumption which will hopefully reduce the environmental impact in Karuizawa, promoting sustainability. Research has shown that indoor temperature and humidity levels significantly impact energy efficiency and Karuizawa residents’ comfort, especially in the winter seasons. Inefficient heating and cooling systems in combination with a lack of awareness about the benefits of power conservation in the form of making sure windows and doors are closed in homes can lead to unnecessary energy consumption and increased carbon emissions. The challenge I have taken is to identify the fluctuations in indoor environmental conditions in homes that could potentially cause energy inefficiencies and provide a comprehensive data-driven conclusion that suggests solutions for optimizing power consumption. 

## **Proposed Solution**

Considering the client’s needs and budgetary constraints, an effective solution involves using the DHT11 sensor to monitor temperature and humidity levels in residential rooms over a 48-hour period. The DHT11 sensor, priced at under $5 USD, offers adequate precision (Temperature Range: 0°C to 50°C [well within the realistic range], Humidity Range: 20% to 90%) and uses simple SPI communication, making it suitable for large-scale deployment.

My project will  take into consideration different factors like the on/off status of heating systems, the status of windows and doors, and the weather outside the building to detect anomalies and patterns in the data. For instance, if the heating systems are left on for long periods or if the window is accidentally left open, these events can drastically affect indoor temperatures and result in wasted energy. By analyzing these, the study will be able to find out specific causes of energy inefficiency and suggest necessary solutions for their improvement.

The proposed solution is very affordable and simple, considering most households function on a very tight budget. The DHT11 sensor, for example, costs less than $5 USD and can deliver acceptable precision for this purpose, covering the temperature from 0°C to 50°C and 20% to 90% in terms of humidity. The collected data would be stored in CSV and uploaded to a local server for redundancy and ease of access.

This investigation also considers long-term sustainability and adaptability. The system is designed to be scalable and maintainable, allowing for enhancements and modifications in the future if needed. For example, it could include extra sensors or more sophisticated data analysis methods to gain even deeper insights.

## **Success Criteria**

### **1. Visualization of Data**

The solution will be able to display clear, accurate graphs depicting **temperature** and **humidity** trends in residential homes over a duration of **48 hours**. This time frame encompasses two complete day-night-day cycles, recording both daytime and nighttime variations very effectively. These graphs are intended to visually show all fluctuations and patterns that may indicate a possible inefficiency in managing indoor climate.

**Quote from the problem definition:  
*"…find the variations in the indoor environmental conditions of households that may lead to energy wastage and draw a comprehensive inference based on the data analysis."*

### **2. Economical Data Collection**

The indoor environment variables will be measured with a **DHT11 sensor** connected to a **Raspberry Pi 4 Model B**. The hardware required for this experiment comprises:

- **Temperature and Humidity Sensor**: Cheap (less than $5 USD) and sufficient for domestic usage.
- **Raspberry Pi**: An affordable, extensible platform (< ¥6000).
 
This setup will guarantee that ample data is gathered at the least cost and can be accommodated by the households in the budget constraint.
 
**Quote from the problem definition**: 
*"…providing a comprehensive data-driven conclusion that suggests solutions for optimizing power consumption."*
  
### **3. Mathematical Modeling**

The solution will give **mathematical models** that can be used to analyze temperature and humidity levels. Using **linear regression** models, the data is analyzed for trends and the prediction of future conditions. This will ensure a proper understanding of indoor climate variations.

**Quote from the problem definition**:  
*"…identify the fluctuations in indoor environmental conditions in homes that could potentially cause energy inefficiencies."*

### **4. Comparative Analysis**

The solution will produce a **comparative analysis** in the areas of temperature and humidity levels, including:

* **Mean** 
* **Standard Deviation** 
* **Minimum and Maximum Values** 
* **Median**

The data visualization provided will help the residents spot periods when energy use has not been very efficient.

**Quoting the problem definition:**
 * "…draw a comprehensive data-driven conclusion which could indicate solutions to optimize power consumption."*

### **5. Data Storage and Redundancy**

Data read by the DHT11 sensor will be:

1. **Stored Locally** in a CSV file for easy access and backup. 
2. **Uploaded to a Local Server** in real time to ensure data redundancy and avoid data loss during power outages.

This dual approach ensures regular logging of data and data availability.

**Quote from the problem definition**:
*“…inefficient heating and cooling systems… can lead to unnecessary energy consumption and increased carbon emissions.”*

### **6. Predictive Analysis**

The solution will provide a **12-hour prediction** for temperature and humidity trends based on the 48-hour data collected. This forecast will help preemptively adjust indoor conditions to optimize energy use and comfort.

**Quote from the problem definition**:  
*“…identify the fluctuations in indoor environmental conditions… and provide a comprehensive data-driven conclusion.”*

## **7. Poster Presentation**

A detailed **poster** will be prepared to summarize the project findings. This shall include:

- Graphical representation of temperature and humidity trends  
- Key observations from mathematical modeling and comparative analysis  
- Practical recommendations on enhancing energy efficiency  

The poster will present the data and conclusions in an accessible format for residents who may not have a technical background.

**Quote from the problem definition**:
*"…in a data-driven conclusion to proffer solutions for energy optimization."*

---

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


## **Design Statement**

*Our team is developing a Python-based system using a DHT11 sensor to monitor indoor temperature and humidity levels. Data will be recorded over 48 hours and stored in a CSV database. The goal is to identify fluctuations in indoor conditions and provide data-driven solutions to optimize power consumption in Karuizawa homes.*

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

**Issue Tackled**: Effective communication with stakeholders

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
