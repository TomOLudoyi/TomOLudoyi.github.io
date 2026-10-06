# Automated NBA Data Pipeline & Summarisation Tool

A robust Python-based data pipeline designed to ingest, process, and summarize NBA game data, seamlessly integrating with external APIs to deliver automated updates.

## Features
* **Automated Data Ingestion:** Fetches up-to-date NBA statistics and game information via API integrations.

* **Exponential Backoff & Error Handling:** Gracefully manages server timeouts and API rate limits by implementing an exponential backoff retry loop, ensuring the pipeline remains robust in production environments.

* **Platform-Constrained Summarisation:** Transforms raw API payloads into concise, readable summaries strictly formatted to adhere to X's, Twitter, 280-character limit, complete with dynamic franchise hashtags.

* **Off-Season / Test Mode:** Includes a local mocking system to test pipeline transformations without hitting live endpoints.  
Perfect for the NBA off-season or local debugging.

## Architecture
1. **Source:** Live `stats.nba.com` APIs endpoints / Mock `pandas` Data

2. **Ingestion:** Python scripts fetch and load the payload.

3. **Transformation:** Data is cleaned, filtered, and aggregated.

4. **Output/Distribution:** Summarised data is generated and distributed, via Twitter API.

## Installation & Usage

1. Install the required Python dependencies:
```bash
pip install pandas requests nba_api
```

2. **Running the Pipeline:**  

Open the Jupyter Notebook or execute the Python script.  

To guarantee the code successfully outputs a demonstration without failing due to NBA API rate limits, it is currently configured to run in Test Mode.

To switch between live API extraction and the mock data environment, simply modify the boolean flag in the execution block at the bottom of the script:

```python
if __name__ == "__main__":
    # Set to False to fetch live data, True for local mock data
    extract_stats(is_test_mode=True)#
```
## Extraction 
To view the core extraction logic and mock-data architecture, open [NBA_Pipeline](Cl_NBA_pipeline.ipynb).

## Author 
Oluwamuretomiwa Oludoyi   
BSc (Hons), Economics and Econometrics, University of Bristol  
[LinkedIn](https://www.linkedin.com/in/oluwamuretomiwa-oludoyi-0742b0257/)  
[Email](mailto:toludoyi@outlook.com)
