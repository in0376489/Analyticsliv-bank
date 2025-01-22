# Google Ads Data Wrapper

This project provides a cloud function wrapper for fetching data from the Google Ads API, processing it, and sending it to BigQuery. The wrapper allows you to fetch reports like campaigns, ad groups, keywords, and ad performance, and upload the data to BigQuery for further analysis.

## Features

- Fetch Google Ads reports by campaign, ad group, keyword, or ad performance.
- Supports filtering data by date range.
- Handles multiple client accounts under a Google Ads manager account.
- Updates job status in real-time (e.g., `inProgress`, `success`, `failed`).
- Uploads processed data to BigQuery for analysis and reporting.

## Prerequisites

Before using this wrapper, make sure you have the following:

- A Google Cloud project with BigQuery enabled.
- A Google Ads API developer token, client ID, and client secret.
- A valid Google Ads refresh token for authentication.
- Python 3.8+ installed on your machine.
- The required Python libraries installed.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/google-ads-data-wrapper.git
    cd google-ads-data-wrapper
    ```

2. Set up a virtual environment and install dependencies:
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    pip install -r requirements.txt
    ```

3. Set up your environment variables for Google Ads API credentials:
    - `GOOGLE_ADS_DEVELOPER_TOKEN`
    - `GOOGLE_ADS_CLIENT_ID`
    - `GOOGLE_ADS_CLIENT_SECRET`
    - `GOOGLE_ADS_REFRESH_TOKEN`

4. (Optional) If you're testing locally, use a `.env` file to store these secrets securely.

## Usage

Once the environment is set up, you can deploy the function to Google Cloud Functions:

```bash
gcloud functions deploy google_ads_data_function \
  --runtime python310 \
  --trigger-http \
  --allow-unauthenticated
