# Stock Price Alert with Twilio & News API

This project tracks the stock price of a specified company and sends relevant news articles via SMS using the Twilio API if the stock price changes by a certain percentage. It utilizes the Alpha Vantage API for stock data and NewsAPI for news articles.

## Features
- Tracks daily stock prices using the [Alpha Vantage API](https://www.alphavantage.co/documentation/).
- Retrieves news articles related to the company using the [NewsAPI](https://newsapi.org/).
- Sends SMS alerts with the latest stock performance and news using [Twilio](https://www.twilio.com/).

## Technologies Used
- Python
- Requests library for making API calls
- Twilio API for sending SMS
- Alpha Vantage API for stock price data
- NewsAPI for fetching relevant news

## Setup Instructions

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    ```

2. Install dependencies:
    ```bash
    pip install requests twilio python-dotenv
    ```

3. Create a `.env` file in the root directory with the following contents:
    ```bash
    VIRTUAL_TWILIO_NUMBER=your_twilio_virtual_number
    VERIFIED_NUMBER=your_verified_number
    STOCK_API_KEY=your_alpha_vantage_api_key
    NEWS_API_KEY=your_news_api_key
    TWILIO_SID=your_twilio_account_sid
    TWILIO_AUTH_TOKEN=your_twilio_auth_token
    ```

4. Run the script:
    ```bash
    python stock_alert.py
    ```

## How It Works
1. Fetches the stock price of a specified company (e.g., Tesla Inc.) using Alpha Vantage API.
2. Calculates the percentage difference between the closing prices of the last two days.
3. If the price difference is above the threshold, it fetches the top 3 news articles about the company from NewsAPI.
4. Sends the articles as SMS alerts using Twilio to a verified phone number.

## Customization
- You can change the stock symbol and company name in the script to track any publicly traded company by modifying the `STOCK_NAME` and `COMPANY_NAME` variables.

## Example Output
- SMS example:
  ```
  TSLA: 🔺5%
  Headline: Tesla Stock Surges.
  Brief: Tesla shares saw a significant rise after the latest earnings report.
  ```

## API Documentation
- Alpha Vantage: https://www.alphavantage.co/documentation/
- NewsAPI: https://newsapi.org/docs/get-started
- Twilio: https://www.twilio.com/docs/usage/api

## Credits
- A Udemy course "100 days of python code" by Dr. Angela Yu.
