# Yahoo API — Historical Price Data

Simple Python wrapper to fetch **historical market data** directly from Yahoo Finance.

---

## 🌐 Features
- Retrieve one or multiple Yahoo tickers (e.g. `['AAPL', 'XIU.TO', '^GSPC']`)
- Customizable intervals:  
  `'1m','2m','5m','15m','30m','60m','90m','1h','1d','5d','1wk','1mo','3mo'`
- Choose range period (e.g. `'1y'`, `'5y'`, `'max'`)
- Fetch one or many metrics:  
  `'open', 'high', 'low', 'close', 'volume', 'adjclose', 'splits', 'dividends'`
- `adjclose` and `close` automatically return **two DataFrames** each: price data and returns
- Optional CSV export for quick saving

---

## ⚙️ Installation

```bash
pip install --index-url https://test.pypi.org/simple/ \
            --extra-index-url https://pypi.org/simple \
            yahoo-finance-api-po \
            --upgrade \
            --force-reinstall \
            --no-deps
