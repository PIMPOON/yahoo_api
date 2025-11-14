# Yahoo API — Historical Price Data

Simple Python wrapper to fetch **historical market data** directly from Yahoo Finance.

---

## 🌐 Features
- Retrieve one or multiple Yahoo tickers (e.g. `['AAPL', 'XIU.TO', '^GSPC']`)
- Customizable intervals: `'1m','2m','5m','15m','30m','60m','90m','1h','1d','5d','1wk','1mo','3mo'`
- Choose range period (e.g. `'1y'`, `'5y'`), if range is empty it returns all data available
- Fetch one or many metrics: `'open', 'high', 'low', 'close', 'volume', 'adjclose', 'splits', 'dividends'`
- `adjclose` and `close` automatically return **two DataFrames** each: price data and returns
- Optional CSV export for quick saving

---

## ⚙️ Install dependencies

```bash
pip install aiohttp tenacity pandas numpy requests numpy
```

## ⚙️ Package installation
macOS/Windows
```
pip install --index-url https://test.pypi.org/simple/ --extra-index-url https://pypi.org/simple yahoo-finance-api-po --upgrade
```

---

## 🚀 Quick Start
```bash
from yahoo_api import YahooAPI

api = YahooAPI()

tickers = ['CAD=X', '^SPX', 'DOL.TO']
results = api.get_yahoo_data(
    tickers=tickers,
    interval="1d",                 # default value is "1d"
    metric=['adjclose', 'volume'], # request multiple metrics
    #range_val="1y",               # I recommend not using this parameter to show all data available
    csv_output=True                # save results to CSV if True, default value is False
)

# Unpack results (adjclose returns two DataFrames: data and returns)
df_adjclose, df_returns, df_volume = results
```

---

## 🧠 more examples
```bash
metric=['adjclose', 'volume']
→ returns = (df_adjclose, df_adjclose_returns, df_volume)

metric=['open','close','dividends']
→ returns = (df_open, df_close, df_close_returns, df_dividends)
