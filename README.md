
# Web app For Monitoring a Patient's Health Status in Real Time 

This is the second project i worked on during my internship as a Health Data scientist/ AI engineer at LIP6. The goal of the project was to create a dashboard to visualize and process in real time various data emanating from one or more CSV type files which are continuously filled during an acquisition in order to display various calculated physiological parameters notabely Heart Rate(HR), Breathing Rate(BR), Blood oxygen saturation(SpO2), and temperature(T) on the acquired signals.

## Data 
Pulse Transit Time PPG Dataset: Available on PhysioNet, this database contains synchronized PPG and ECG recordings obtained from the fingers of healthy subjects while sitting, walking and running. The database also includes measurements of blood pressure, temperature and accelerometer data, which can be useful for multimodal analysis ([PhysioNet](https://physionet.org/content/pulse-transit-time-ppg/1.1.0/)).

## Installation

To run this project, you need to have Python 3.12 installed on your machine. You can check your Python version with:

```bash
python --version
```

Install dependencies

```bash
  pip install numpy pandas matplotlib 
  pip install heartpy
  pip install streamlit 
  pip install plotly 
  
```
## Authors

- [@Imaneelmissaoui](https://github.com/imaneelmissaoui)


## Demo
A demo can be visualized here : 
https://github.com/imaneelmissaoui/Real_time_Monitoring_Dashboard/blob/main/FinalDashboard_demo_video.mp4

The demo shows a clip of the real time dashboard streaming thats being updated while new data is being read from te the source csv file and written into the simulated csv file using the module CSVUpdateSimulator.py 


## Run Locally

Clone the project

```bash
  git clone https://github.com/imaneelmissaoui/Real_time_Monitoring_Dashboard/tree/main/Dashboard/FinalDashboard
```

Go to the project directory

```bash
  cd /CSV 
```

Start the server by running both the streamlit app and the 
CSVUpdateSimulator to visualize the dashboard updating in real time as new data comes in the simulated csv. 

```bash
  streamlit run CSVDashboard.py 
```

```bash
  Python CSVUpdateSimulator.py 
```

## Erros and Bugs
- Some Biometrics might not be calculated accurately and need more accurate implementations.  
- Reading and writing periodically into the same file causes conflicts in which data can't be accessed properly.
- The Timings in the CSV (Time column) aren't taken into consideration for a more accurate signal. Currently we rely on a constant sampling rate (500Hz).
- Streamlit "resets" when data is updated and redraws everything instead of just updating the already existing elements.
- Signal filtering can be improved later and adapted to each signal instead of a generic filtering on the type of the signal (PPG).
- Blood Oxygen also generates negative values, management of these aberrant values needs to be implemented later. 

## Screenshots

![App Screenshot](./FinalDashboard.png)


## Dashboard Workflow

The dashboard workflow can be visualized here : 

![Workflow preview](./FinalDashboard_Workflow.jpg)
