# Capstone (Fall 2025) — Environmental Data Analysis

Field measurements for **air quality (PM2.5)** and **sound quality**.

---

## What this project does

- Connects to a shared Google Drive folder with UPAS log files.  
- Reads each log, cleans errors, and extracts **PM2.5**.  
- Combines everything into a single table for analysis.  
- Lets you plot **PM2.5 vs time** by date/hour.  

---

## Setup

### 1) Install Python packages
```bash
pip install pydrive2 oauth2client pandas numpy matplotlib
2) Get the JSON key
To participate, you need a Google Drive service-account JSON key.
👉 Ask MARTIN CELEDON for this file.

Once you receive it:

Save it outside the repository (never put it inside GitHub).

Windows: C:\Users\<you>\capstone_credentials.json

macOS/Linux: /Users/<you>/capstone_credentials.json

3) Set the environment variable
macOS/Linux

bash
Copy code
export CAPSTONE_SA_JSON=~/capstone_credentials.json
Windows (PowerShell)

powershell
Copy code
$env:CAPSTONE_SA_JSON = "C:\Users\<you>\capstone_credentials.json"
4) Run the notebook
Open AQ_2.ipynb in JupyterLab/Notebook.

Run all cells in order.

The notebook will use your JSON key to connect to Google Drive and load the data.
