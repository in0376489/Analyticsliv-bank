# Facebook Ads Data Fetching and BigQuery Integration

This project provides a solution for fetching data from the Facebook Ads API, processing it, and uploading it to Google BigQuery. It is designed to be deployed as a Cloud Function on Google Cloud Platform (GCP). The main functionalities include fetching daily insights, processing the data using Pandas, and uploading it to a specified BigQuery table.

## Features
- Fetch Facebook Ads data using the Facebook Marketing API.
- Supports different levels of data (ad, campaign, adset).
- Allows multiple breakdowns like age, gender, country.
- Processes and formats the data using Pandas.
- Uploads the processed data to Google BigQuery.
- Provides job status updates (inProgress, success, failed).
- Optimized for parallel execution using `ThreadPoolExecutor`.

## Requirements
- Python 3.8 or higher
- Flask
- `google-cloud-bigquery` for BigQuery interactions
- `facebook-business` for Facebook Ads API
- `pandas` for data processing
- `requests` for making API requests
- `concurrent.futures` for parallel data fetching

You can install the required dependencies with:

```bash
pip install -r requirements.txt
