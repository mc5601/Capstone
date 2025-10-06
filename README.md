# Capstone (Fall 2025) — Environmental Data Analysis
**Field measurements for air quality (PM2.5) and sound quality**

Analyze **real field data** collected along defined routes.  
The pipeline pulls **air-quality logs** (UPAS text files) from Google Drive, cleans them, merges everything into a tidy table, and plots **PM2.5 vs time**. The same structure will be mirrored for **noise (sound)** so both datasets align by **route** and **time**.

---

## 0) Clone the public repository (GitHub)

1. Open the repository’s public page on GitHub.
2. Click **Code** → copy the HTTPS or SSH URL.
3. **Clone** (choose one):

   **HTTPS**
   
       git clone https://github.com/<org-or-user>/<repo-name>.git
       cd <repo-name>

   **SSH**
   
       # Add your SSH key to GitHub first (Settings → SSH and GPG keys)
       git clone git@github.com:<org-or-user>/<repo-name>.git
       cd <repo-name>

4. *(Recommended)* Create & activate a virtual environment:

   **macOS/Linux**
   
       python3 -m venv .venv
       source .venv/bin/activate

   **Windows (PowerShell)**
   
       py -3 -m venv .venv
       .\.venv\Scripts\Activate.ps1

> 🔒 **Never commit secrets.** Keep credentials **outside** the repo. A `.gitignore` entry helps, but do not add keys to Git, ever.

---

## 1) Install Python packages

    pip install pydrive2 oauth2client pandas numpy matplotlib

---

## 2) Get your Google Drive key

You’ll need a **Google Drive service-account JSON key** to connect to the shared folder.  
👉 Ask **Martin Celedón** for this file.

---

## 3) Save the key securely (outside the repo)

**Windows**

    C:\Users\<you>\capstone_credentials.json

**macOS / Linux**

    /Users/<you>/capstone_credentials.json
    # or
    /home/<you>/capstone_credentials.json

---

## 4) Set the environment variable

**macOS / Linux**

    export CAPSTONE_SA_JSON=~/capstone_credentials.json

**Windows (PowerShell)**

    $env:CAPSTONE_SA_JSON = "C:\Users\<you>\capstone_credentials.json"

*(Tip: add that line to your shell profile so it’s set automatically next time.)*

---

## ▶️ Run the notebook

1. Start Jupyter:
   
       jupyter lab

2. Open **`notebooks/AQ_2.ipynb`**.  
3. Click **Run All**.

The notebook will:
- Authenticate with Google Drive via your service-account key.  
- Download all **air-quality log** files (`*_LOG_*.txt`) to a local cache.  
- Parse, clean, and merge the data.  
- Plot **PM2.5 vs time** and produce summaries by route (morning / afternoon / evening).

---

## 🗺️ Fieldwork integration (routes & timing)

Teams should upload their **air-quality logs** (UPAS text files) from the defined sampling routes:

- **Morning (≈ 11:00)**
- **Afternoon (≈ 14:00)**
- **Evening (≈ 19:00)**

Keeping **consistent filenames** and **fixed routes** lets us compare by **time of day**, **route**, and **pollution peaks**.
