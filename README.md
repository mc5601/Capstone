# Capstone (Fall 2025) — Environmental Data Analysis  
**Field measurements for air quality (PM2.5) and sound quality**

---

## 🧠 What this project does  
This project helps analyze **real field data** collected for air quality and noise levels along defined routes.  

- Connects to a **shared Google Drive folder** with UPAS device logs for **air quality (PM2.5)**.  
- Reads each log file, **cleans errors**, and extracts PM2.5 concentrations.  
- Combines all logs into one clean table for analysis.  
- Lets you **plot PM2.5 vs. time** (by date/hour) and later integrate **sound data**.  

The same structure will be used for **sound quality (noise)** so both datasets align by route and time.

---

## ⚙️ Setup

### 1️⃣ Install Python packages
    pip install pydrive2 oauth2client pandas numpy matplotlib

---

### 2️⃣ Get your Google Drive key
You’ll need a **Google Drive service-account JSON key** to connect to the shared folder.  
👉 **Ask Martin Celedón** for this file.

---

### 3️⃣ Save the key securely
Save the JSON file **outside this repository** (never upload it to GitHub):

- **Windows:**  
  `C:\Users\<you>\capstone_credentials.json`

- **macOS / Linux:**  
  `/Users/<you>/capstone_credentials.json`  
  (or `/home/<you>/capstone_credentials.json`)

---

### 4️⃣ Set the environment variable

**macOS / Linux:**
    export CAPSTONE_SA_JSON=~/capstone_credentials.json

**Windows (PowerShell):**
    $env:CAPSTONE_SA_JSON = "C:\Users\<you>\capstone_credentials.json"

---

## ▶️ How to Run

1. Open Jupyter Lab or Notebook:
    
        jupyter lab

2. In Jupyter, open **`AQ_2.ipynb`**.  
3. Click **Run All Cells**.

The notebook will:
- Connect to Google Drive using your service-account key.  
- Download all UPAS log files (`*_LOG_*.txt`).  
- Parse and clean the data.  
- Generate plots of **PM2.5 vs. time** and summarize by route (morning, afternoon, evening).

---

## 🗺️ Fieldwork Integration
Each team uploads their UPAS logs from defined sampling routes:

- **Morning (≈11 AM)**  
- **Afternoon (≈2 PM)**  
- **Evening (≈7 PM)**

By keeping consistent filenames and routes, all results can later be compared by **time of day**, **route**, and **pollution peaks**.

---

## 📂 Folder Structure
To keep everything organized, follow this structure inside the repository:

