# Insider Trade Extractor & Analysis Toolkit

This Python project helps investors make more informed decisions by leveraging recent insider trading activity. It streamlines the workflow for traders and analysts seeking actionable insights from insider transactions across the S&P 500 (or custom companies) and provides tools for in-depth data processing and statistical analysis.

---

## Features

### 1. **Interactive Insider Trade Extraction (`fetch_insider_trades.py`)**
- **GUI-based workflow:** Select companies by rank (market cap) or manual selection.
- **Finnhub API Integration:** Fetches the latest insider trades (up to 90 days back) for selected tickers.
- **Time Window Filters:** Specify custom periods (e.g., last 3 business days).
- **Company Filters:** Pull trades for S&P 500 or custom tickers.
- **Trade Type Filters:** Optionally focus on purchases, sales, or all activity.
- **Efficient Caching:** Stores results locally to minimize repeated API calls and speed up future queries.
- **Progress Feedback:** Real-time status updates and error handling.

### 2. **Insider Trade Data Processing (`analyze_insider_trades.py`)**
- **Cleans & Formats Extracted Data:** Removes invalid/missing trades, computes trade value, and performs feature engineering.
- **Descriptive Statistics:** 
    - Overall stats: trade counts, average shares/values, max/min, median, etc.
    - Per-company summaries: number of trades, unique insiders, avg price/shares, total trade value, sentiment (% buys).
- **Top Movers:** Quickly identify companies with the most insider purchases or sales.
- **Output:** Generates an easy-to-read summary for further analysis, integration, or reporting.

---

## Typical Workflow

1. **Extract Trades**
    - Run `fetch_insider_trades.py`
    - Use the GUI to select:
        - Date to rank S&P 500
        - Number of top companies (or manual list)
        - Days back to pull trades
    - Export insider trade data to CSV.

2. **Analyze Trades**
    - Run `analyze_insider_trades.py`
    - The script automatically loads the latest insider trade CSV from your Desktop.
    - Outputs overall stats and per-company summaries.
    - Use the clean data for further trading strategies or analytics.

---

## Requirements

- Python 3.8+
- `pandas`, `yfinance`, `finnhub-python`, `tkinter`, `tqdm`
    - Install dependencies:  
      `pip install pandas yfinance finnhub-python tqdm`
    - `tkinter` is included with standard Python distributions.

- **Finnhub API Key:**  
  Update `api_key` in `fetch_insider_trades.py` with your own Finnhub API key for production use.

---

## File Structure

```
.
├── fetch_insider_trades.py        # GUI app for trade extraction (Finnhub API)
├── analyze_insider_trades.py      # Data cleaning, stats, and summary
├── sp500_cached.json              # Locally cached S&P 500 ticker list
├── Top 500 Insider Trades <DATE>.csv  # Example exported trade file
```

---

## Customization

- **Add/Remove Companies:** Use manual mode in the GUI or edit ticker lists.
- **Change Export Location:** By default, all files are saved to your Desktop under "Insider Trades Extracts".
- **Analysis Tweaks:** Edit `analyze_insider_trades.py` for custom filters, grouping, or stats.

---

## Use Case

This toolkit is ideal for:
- **Equity analysts** tracking insider sentiment for specific stocks.
- **Quantitative researchers** integrating insider activity into trading signals.
- **Portfolio managers** monitoring large, recent insider trades for compliance or alpha generation.

---

## License

MIT License. See [LICENSE](LICENSE) for details.

---

## Disclaimer

This tool is for research and informational purposes only. Insider trading data is subject to regulatory disclosures and reporting delays. Do your own due diligence before making investment decisions.

---
