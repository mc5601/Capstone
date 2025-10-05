# Capstone (Fall 2025) — Environmental Data Analysis

Field measurements for **air quality (PM2.5)** and **sound quality**.

## What this project does
- Connects to a shared Google Drive folder with UPAS log files.  
- Reads each log, cleans errors, and extracts **PM2.5**.  
- Combines everything into a single table for analysis.  
- Lets you plot **PM2.5 vs time** by date/hour.  

---

# Setup

### 1) Install & configure (copy–paste this)
```bash
# 1) Install Python packages
pip install pydrive2 oauth2client pandas numpy matplotlib

# 2) Get the JSON key
# You need a Google Drive service-account JSON key.
# 👉 Ask MARTIN CELEDON for this file.

# Save it OUTSIDE the repository (never in GitHub):
#   Windows:       C:\Users\<you>\capstone_credentials.json
#   macOS/Linux:   /Users/<you>/capstone_credentials.json   (or /home/<you>/capstone_credentials.json)

# 3) Set the environment variable (macOS/Linux)
export CAPSTONE_SA_JSON=~/capstone_credentials.json

# 3b) Windows (PowerShell) — run this in PowerShell, not in bash:
# $env:CAPSTONE_SA_JSON = "C:\Users\<you>\capstone_credentials.json"

# 4) How to run
# Start Jupyter and open the notebook:
jupyter lab   # or: jupyter notebook
# In Jupyter, open AQ_2.ipynb and run all cells in order.
# The notebook uses CAPSTONE_SA_JSON to connect to Google Drive and load the data.
