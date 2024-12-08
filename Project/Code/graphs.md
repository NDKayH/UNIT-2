```.py

from matplotlib import pyplot as plt
import matplotlib
import pandas as pd
import numpy as np
from myLib import moving_average

plt.style.use('ggplot')
matplotlib.use('MacOSX')  # Fix for macOS

# Load CSV file
data = pd.read_csv('/Users/noahhoffman/UWCISAK/Projects/Unit2.2/raw_readings.csv')

# Extract temperature and humidity data for sensor_id 26
temp = data[data['sensor_id'] == 26]['value'].tolist()  # Temperature data
hum = data[data['sensor_id'] == 26]['humidity'].tolist()  # Humidity data

# Create x-axis range for data points collected every 5 seconds (up to 48 hours)
temp_x = list(range(len(temp)))
hum_x = list(range(len(hum)))

# downsampling for clarity (too many data points over the course of the 48 hour period and it kept on making my graphs impossible to discern/interpret)
downsample_step = 100  # Plot every 100th point to reduce clutter
temp_downsampled = temp[::downsample_step]
hum_downsampled = hum[::downsample_step]
temp_x_downsampled = temp_x[::downsample_step]
hum_x_downsampled = hum_x[::downsample_step]

# applying moving average (import from separate file)
window_size = 50
temp_smoothed = moving_average(windowSize=window_size, x=temp_downsampled)
hum_smoothed = moving_average(windowSize=window_size, x=hum_downsampled)

# ensure x-axis ranges match the lengths of the smoothed data (previous problem I kept on running into)
temp_x_smoothed = temp_x_downsampled[:len(temp_smoothed)]
hum_x_smoothed = hum_x_downsampled[:len(hum_smoothed)]

# linear model for temperature
temp_slope, temp_intercept = np.polyfit(temp_x_downsampled, temp_downsampled, deg=1)
temp_linear = [temp_slope * x + temp_intercept for x in temp_x_downsampled]

# linear model for humidity
hum_slope, hum_intercept = np.polyfit(hum_x_downsampled, hum_downsampled, deg=1)
hum_linear = [hum_slope * x + hum_intercept for x in hum_x_downsampled]

# create the visualization
fig, axs = plt.subplots(2, 1, figsize=(15, 10), dpi=100, sharex=True)

# temperature plot
axs[0].plot(temp_x_downsampled, temp_downsampled, color='green', marker='x', linestyle='-', markersize=4, linewidth=1, alpha=0.5, label='Raw Temperature')
axs[0].plot(temp_x_smoothed, temp_smoothed, color='black', linewidth=2, label='Smoothed Temperature')
axs[0].plot(temp_x_downsampled, temp_linear, color='purple', linestyle='--', linewidth=2, label='Linear Model')

# customize the temp plot
axs[0].set_title("Temperature Readings", fontsize=18, fontweight='bold')
axs[0].set_ylabel("Temperature (°C)", fontsize=14)
axs[0].grid(True, linestyle='--', alpha=0.5)
axs[0].legend(fontsize=12)

# humidity plot
axs[1].plot(hum_x_downsampled, hum_downsampled, color='blue', marker='o', linestyle='-', markersize=4, linewidth=1, alpha=0.5, label='Raw Humidity')
axs[1].plot(hum_x_smoothed, hum_smoothed, color='red', linewidth=2, label='Smoothed Humidity')
axs[1].plot(hum_x_downsampled, hum_linear, color='purple', linestyle='--', linewidth=2, label='Linear Model')

# Customize the humidity plot
axs[1].set_title("Humidity Readings", fontsize=18, fontweight='bold')
axs[1].set_ylabel("Humidity (%)", fontsize=14)
axs[1].set_xlabel("Time (Seconds)", fontsize=14)
axs[1].grid(True, linestyle='--', alpha=0.5)
axs[1].legend(fontsize=12)

# Adjust subplot spacing and display the plots
plt.tight_layout()
plt.show()

```
