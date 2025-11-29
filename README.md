 data-scraping-repo
template to scrape data
```import requests
from bs4 import BeautifulSoup
import pandas as pd
import time

url = "https://worldpopulationreview.com/country-rankings/best-healthcare-in-the-world"

headers = {
    "User-Agent": "Mozilla/5.0 (compatible; JosephHealthBudgetScraper/1.0; +https://github.com/youngjon2001)"
}

page = requests.get(url, headers=headers)
time.sleep(1)

soup = BeautifulSoup(page.text, "html.parser")
```

 Correct table extraction
table = soup.find("table")

df = pd.read_html(str(table))[0]

print(df.head())
