# Smart Drainage Monitoring System (CPC357)
This project is an IoT-based **Smart Drainage Monitoring System** developed for the CPC357: IoT Architecture & Smart Applications course.  
The system monitors drainage water levels and rainfall conditions in real time, detects drainage blockages, and provides early flood risk alerts to support **UN SDG 11 – Sustainable Cities and Communities**.

## System Overview
The system uses sensors to collect real-time drainage and rainfall data, sends the data to a cloud database, and visualizes it through a web-based dashboard.
Key capabilities include:
- Real-time water level monitoring
- Rain detection and rain-state analysis
- Drain blockage detection using consecutive data thresholds
- Flood risk prediction using weather forecast data
- Interactive dashboard with real-time and historical data filtering

## Features
**Water Level Status Card**
  - Green (<40%): Normal
  - Orange (40–69%): Warning
  - Red (≥70%): Danger (blinking alert)

**Rain Detection**
  - Rain state visualized using bar chart color changes

**Drain Blockage Detection**
  - Detects blockage when water level remains high or drops very slowly after rain
  - Uses 30 consecutive data points and threshold-based logic

**Flood Prediction**
  - Triggered when:
    - Water level remains high for 30 consecutive readings
    - Future rainfall is predicted using OpenWeather API
  - Alert displayed as red blinking warning

**Data Visualization**
  - Water Level graph with date-range filtering
  - Water Level vs Rain State graph:
    - Real-time mode (last 500 data points)
    - Historical mode (1h, 6h, 24h, or custom date range)

**Data Tables**
  - Sensor data table (water level, rain state, timestamp)
  - 5-day weather forecast table

## Set Up and Configurations
### Hardware Set Up and Configurations
### Rain Sensor
 **DO Pin** -> NodeMCU Pin23 / Breadboard A18
 **VCC Pin** -> Breadboard Power Rail Positive (left)
 **GND Pin** -> Breadboard Power Rail Negative (left)

### Ultrasonic Sensor
 **VCC Pin** -> Breadboard Power Rail Positive (left)
 **GND Pin** -> Breadboard Power Rail Negative (left)
 **TRIG Pin** -> NodeMCU Pin5 /Breadboard A10
 **ECHO Pin** -> NodeMCU Pin17 /Breadboard A9

### Resistors
 **Green LED Cathode** (Breadboard F24) -> Breadboard Power Rail Negative (Right)
 **Yellow LED Cathode** (Breadboard F26) -> Breadboard Power Rail Negative (Right)
 **Yellow LED Cathode** (Breadboard F28) -> Breadboard Power Rail Negative (Right)

### Green LED
 **Anode** (Breadboard F23), **Cathode** (Breadboard F24)
 **SIG Pin** (Breadboard H23) -> NodeMCU Pin25 / Breadboard J11

### Yellow LED
 **Anode** (Breadboard F25), **Cathode** (Breadboard F26)
 **SIG Pin** (Breadboard H25) -> NodeMCU Pin26 / Breadboard J10

### Red LED
 **Anode** (Breadboard F27), **Cathode** (Breadboard F28)
 **SIG Pin** (Breadboard H27) -> NodeMCU Pin27 / Breadboard J9

### Breadboard
 **NodeMCU 5V** / Breadboard J1 -> Breadboard Power Rail Positive (Right)
 **NodeMCU GND** / Breadboard J6 -> Breadboard Power Rail Negative (Right)
 **NodeMCU GND** / Breadboard A19 -> Breadboard Power Rail Negative (Left)
 **Breadboard Positive Power Rail** (right) -> Breadboard Positive Power Rail (left) 

## Software Setup

1. Clone the repository:
   git clone https://github.com/ongxq/CPC357Project.git

2. Navigate to the project folder:
   cd CPC357Project

3. Install dependencies:
   npm install

4. Configure environment variables:
   Create a .env file and add:
   VITE_SUPABASE_URL=your_supabase_url
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
   VITE_OPENWEATHER_KEY=your_api_key

6. Run the application:
   npm run dev



## Dependencies and Requirements
### System Requirements
- Node.js (v16 or above)
- npm
- Internet connection

### Frontend Dependencies
- Vue.js
- Chart.js
- Axios
- Tailwind CSS

### Backend / Cloud
- Supabase

### APIs
- OpenWeather API

### Hardware Requirements
- ESP32 / Microcontroller
- Ultrasonic Sensor
- Rain Sensor
- Green LED
- Yellow LED
- Red LED
- Resistors
- Breadboard
- Jumper Wires
- USB cable


