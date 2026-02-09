# 🎬 Anime Video Downloader

Welcome to the **Anime Video Downloader** repository!  
This repository contains all the scripts, CSV files, and utilities used to **scrape and download anime videos** from [AnimePahe](https://animepahe.si).  
It is designed for anyone who wants to automate the download of anime episodes directly to their PC with full control over episode selection and video resolution.

---

## 🔗 Repository Link
Check out the full project here: [Anime Video Downloader](https://github.com/Ezee-Kits/ANIME-VIDEO-DOWNLOADER)

---

## 📂 Repository Contents

### 1️⃣ PYTHON FILES

#### `animepesi.py`
- Main scraping script to collect **episode download links** from AnimePahe.
- Features:
  - Uses **Playwright** to navigate and extract episode links.
  - Extracts **POST URLs**, **tokens**, and **cookies** for each episode.
  - Saves episode metadata into a CSV file (`MOVIES.csv`) and individual `.json` files for cookies.

#### `DOWNLOAD.py`
- Script to **download videos** listed in `MOVIES.csv`.
- Features:
  - Multi-threaded downloads using `ThreadPoolExecutor`.
  - Resumable downloads (supports partial file resume if interrupted).
  - Progress bars for each download with `tqdm`.
  - Automatic handling of cookies for download authentication.

#### `func.py`
- Utility functions used by both scraping and downloading scripts.
- Features:
  - `saving_files(data, path)` – Save data into CSV, appending if the file already exists.

---

### 2️⃣ CSV FILES

The `CSV_FILES` folder contains:
- `MOVIES.csv` – Master CSV file with all episode metadata for downloading.
- Individual `.json` files for each anime episode containing cookies required for download:
  - Example: `AnimePahe_Shingeki_no_Kyojin_Eng_Dub_-_43_BD_720p_MTBB.mp4.json`

---

### 3️⃣ How It Works

#### Step 1: Scrape Episodes
Run `animepesi.py` to:
- Navigate to an AnimePahe episode page.
- Extract all available episode links.
- Save metadata for each episode, including POST URL, token, and cookies.

```bash
python PY_FILES/animepesi.py
```

#### Step 2: Download Videos
Run `DOWNLOAD.py` to:
- Read `MOVIES.csv`.
- Download each episode using saved cookies for authentication.
- Show download progress with resumable support.

```bash
python PY_FILES/DOWNLOAD.py
```

---

### 4️⃣ Directory Structure
```
ANIME-VIDEO-DOWNLOADER/
│
├── PY_FILES/
│   ├── animepesi.py        # Scraping episodes
│   ├── DOWNLOAD.py         # Downloading episodes
│   └── func.py             # Utility functions
│
├── CSV_FILES/              # CSV and JSON files for episode metadata
│   ├── MOVIES.csv
│   ├── AnimePahe_Shingeki_no_Kyojin_Eng_Dub_-_43_BD_720p_MTBB.mp4.json
│   ├── AnimePahe_Shingeki_no_Kyojin_Eng_Dub_-_44_BD_720p_MTBB.mp4.json
│   └── ... 
│
└── README.md               # This file
```

---

### 5️⃣ Requirements

- Python 3.8+
- Playwright
- Requests
- BeautifulSoup4
- lxml
- tqdm

Install dependencies using:

```bash
pip install playwright requests beautifulsoup4 lxml tqdm
```

Install and initialize Playwright:

```bash
playwright install
```

---

### 6️⃣ Notes

- Make sure to **update paths** in `DOWNLOAD.py` and `animepesi.py` according to your system.
- The scraper uses Playwright in **headful mode** to allow manual inspection if needed.
- `MAX_WORKERS` in `DOWNLOAD.py` can be adjusted based on your bandwidth to speed up or slow down downloads.
- Always respect website terms of service when scraping content.

---

### 7️⃣ Author
**Peter**  
- GitHub: [Ezee-Kits](https://github.com/Ezee-Kits)  
- YouTube Channel: [Ezee Kits](https://www.youtube.com/@Ezee_Kits)

---

### ⚖️ License
This repository is **open-source** under the **MIT License**.  
You are free to use and modify the scripts for **personal and educational purposes**.

