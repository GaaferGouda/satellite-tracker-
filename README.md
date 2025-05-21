# 🛰️ Satellite Tracker with AI (ISS Prediction)

This Streamlit web app tracks the International Space Station (ISS) in real time using live TLE data from CelesTrak and predicts its future location using a lightweight AI model (Linear Regression from scikit-learn).

---

## 🌍 Features

- 📡 Fetches real-time Two-Line Element (TLE) data of the ISS
- 📈 Calculates satellite's location over a 24-hour period using Skyfield
- 🤖 Trains a simple AI model to predict the satellite’s next (24th hour) position
- 🗺️ Displays the predicted location on an interactive map
- ⚡ Built with **Streamlit** and **Scikit-learn** (no heavy dependencies like TensorFlow)

---

## 📦 Requirements

Install the required packages using pip:

```bash
pip install -r requirements.txt
```

---

## 🚀 How to Run

Clone the repository and launch the app with Streamlit:

```bash
git clone https://github.com/yourusername/satellite-tracker.git
cd satellite-tracker
streamlit run app.py
```

> Make sure your main Python file is named `app.py` or adjust accordingly.

---

## 🧠 AI Model

This app uses a **Linear Regression** model trained on 23 hourly satellite positions (latitude and longitude) to predict the 24th hour's location. This approach is fast, simple, and fully compatible with Python 3.13 and lightweight environments like Streamlit Cloud.

---

## ☁️ Deployment

To deploy this app to [Streamlit Cloud](https://streamlit.io/cloud):

1. Push your code to a GitHub repository
2. Go to [streamlit.io/cloud](https://streamlit.io/cloud)
3. Click "New app" and connect your GitHub repo
4. Set the entry point to `app.py` (or `testpy.py` if unchanged)
5. Click **Deploy**

---

## 📄 License

MIT License. Feel free to use and modify this project for your own satellite tracking or learning purposes!

---

## ✨ Demo Screenshot

![ISS AI Tracker](https://user-images.githubusercontent.com/your-screenshot.png)

---

Made with 💻 by [Your Name]