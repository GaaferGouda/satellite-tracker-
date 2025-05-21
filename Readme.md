#  ISS Satellite Tracker with AI (Streamlit App)

This project is a simple and interactive web app built with **Streamlit** that tracks the **International Space Station (ISS)** in real time and uses **AI (Linear Regression)** to predict where the ISS will be in the 24th hour.

---

##  What This App Does

This app combines real satellite data and basic machine learning to:

- Fetch live TLE (Two-Line Element) data for the ISS
- Calculate the satellite’s position over the next 24 hours
- Display the data in a table
- Train a simple AI model to predict where the ISS will be in hour 24
- Show the predicted location on a map

---

##  Code Breakdown

###  1. Fetching TLE Data
```python
url = "https://celestrak.org/NORAD/elements/gp.php?CATNR=25544&FORMAT=tle"
response = requests.get(url)
tle_data = response.text.strip().split("\n")
```
- Downloads TLE data for the ISS from **CelesTrak**
- TLE lines are used to calculate satellite orbits

---

###  2. Compute Satellite Positions
```python
sat = EarthSatellite(line1, line2, name, ts)
times = [ts.utc(2025, 2, 16, h) for h in range(24)]
positions = [sat.at(t).subpoint() for t in times]
```
- Uses **Skyfield** to calculate the ISS's position for every hour (0–23) on a chosen day
- Converts these into latitude, longitude, and altitude
- Stores the positions in a DataFrame and displays them

---

###  3. Train AI Model
```python
X = np.array(hours[:-1]).reshape(-1, 1)
y_lat = np.array(lats[1:])
y_lon = np.array(lons[1:])
```
- Prepares training data using the last 23 hours
- Trains two **Linear Regression** models:
  - One for predicting **latitude**
  - One for predicting **longitude**

---

###  4. Predict Hour 24 Location
```python
next_hour = np.array([[23]])
pred_lat = model_lat.predict(next_hour)[0]
pred_lon = model_lon.predict(next_hour)[0]
```
- Predicts the ISS's position in hour 24 using the trained models
- Displays the predicted point on a map using `st.map`

---

##  Final Output

- A clean map with the predicted satellite position at hour 24
- A table of hourly ISS positions (lat, lon, altitude)

---

##  How to Run

###  Requirements

Install required packages:

```bash
pip install streamlit skyfield scikit-learn pandas requests
```

###  Run the App

```bash
streamlit run app.py
```

---

##  Technologies Used

- Python 
- Streamlit 
- Skyfield 
- Scikit-learn 
- Pandas & NumPy 

---

##  Why It's Useful

- Learn how real satellite data is tracked and modeled
- Great example of combining **space tech + AI**
- Simple enough for beginners, powerful enough for demos

---

