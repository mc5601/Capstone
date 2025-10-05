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

### Install Python packages
```bash
pip install pydrive2 oauth2client pandas numpy matplotlib
Install the JSON key on your device
To participate, you need a Google Drive service-account JSON key.
👉 Ask MARTIN CELEDON for this file.

Once you receive it:

Save it outside the repository (never put it inside the GitHub repo).

Windows: C:\Users\<you>\capstone_credentials.json

macOS/Linux: /Users/<you>/capstone_credentials.json or /home/<you>/capstone_credentials.json

Set an environment variable pointing to the file:

macOS/Linux

bash
Copy code
export CAPSTONE_SA_JSON=~/capstone_credentials.json
Windows (PowerShell)

powershell
Copy code
$env:CAPSTONE_SA_JSON = "C:\Users\<you>\capstone_credentials.json"
How to run
Open AQ_2.ipynb in JupyterLab or Jupyter Notebook.

Run the cells from top to bottom.

The notebook will use your JSON key (CAPSTONE_SA_JSON) to connect to Google Drive.

It will automatically:

Find files matching PSP*_LOG_*UTC.txt

Parse and combine PM2.5 data

Show summary tables and graphs

