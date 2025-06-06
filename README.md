# scrapecsv

scrapecsv is a lightweight Python tool that uses Selenium and BeautifulSoup to scrape data from multiple web pages and export results to CSV.
Supports JavaScript-rendered sites and basic proxy configurations to reduce the risk of IP blocking.
## Features

- Works with JavaScript-rendered pages
- Works with un-authenticated proxies to avoid IP blocking
- Groups scraped tags by URL with option of writing data into a csv file
- Optional structured Python data return

## Proxy Support 
proxy = [http://ip:port]
```bash
proxy = [http://127.0.0.1:8000] 
```
Ensure the proxy type (http vs https) matches the protocol of the website you are scraping.
## Installation

```bash
pip install scrapecsv 
```
## Usage
```bash
from scrapecsv import scrape_to_csv

url = ["https://quotes.toscrape.com/"]
tag = ["div.quote span.text", "div.quote span small"]
proxy = ["http://127.0.0.1:8000"]  # Optional

scrape_to_csv(
    urls=url,
    tags=tag,
    write_to_csv=True,
    output_file="quotes.csv",
    return_structured_data=False,
    headless=True,
    proxies=proxy  # Add this parameter if using proxies
)
```
## Note
Support for authenticated proxies coming soon