# Automated NBA Data Pipeline & Summarisation Tool

A robust Python-based data pipeline designed to ingest, process, and summarize NBA game data, seamlessly integrating with external APIs to deliver automated updates.

## Features
* **Automated Data Ingestion:** Fetches up-to-date NBA statistics and game information via API integrations.
* **Data Summarisation:** Transforms raw JSON payloads into concise, readable summaries.
* **Secure Configuration:** Utilises environment variables to keep API keys and secrets entirely private.
* **Off-Season / Test Mode:** Includes a local mocking system to test pipeline transformations without hitting live endpoints—perfect for the NBA off-season or local debugging.

## Architecture
1. **Source:** Live APIs / Mock JSON Data
2. **Ingestion:** Python scripts fetch and load the payload.
3. **Transformation:** Data is cleaned, filtered, and aggregated.
4. **Output/Distribution:** Summarised data is generated and distributed (e.g., via Twitter API).

## Environment Setup

To run this project locally securely without exposing your credentials, you must configure your environment variables. 

1. Clone the repository to your local machine.
2. Locate the `.env.example` file in the root directory.
3. Create a duplicate of this file and rename it to exactly `.env`.
4. Open the `.env` file and insert your actual API keys:

```env
TWITTER_API_KEY=your_actual_api_key_here
TWITTER_API_SECRET=your_actual_api_secret_here
# Add any other required API keys below
```
*Note: The `.env` file is explicitly ignored in `.gitignore` to prevent sensitive keys from being tracked by Git.*

## Installation & Usage

1. Install the required Python dependencies (including `python-dotenv`):
```bash
pip install -r requirements.txt
```

2. **Running in Live Mode:**
To execute the pipeline and fetch live data during the active NBA season, run:
```bash
python main.py
```

3. **Running in Test Mode (Off-Season):**
To showcase the pipeline's functionality during the off-season, or to develop without consuming API rate limits, run the script in test mode. This will bypass the live API calls and instead process the sample responses stored locally in `mock_data.json`.
```bash
python main.py --test-mode
```

## Author 
Oluwamuretomiwa Oludoyi   
BSc (Hons), Economics and Econometrics, University of Bristol  
[LinkedIn](https://www.linkedin.com/in/oluwamuretomiwa-oludoyi-0742b0257/)  
[Email](mailto:toludoyi@outlook.com)
