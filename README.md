# Contact Details Scraper: Contact Details Scraper API for Python & Node.js (2026)

Extract emails, phone numbers and social media links from any website. Crawl contact pages in bulk for lead generation. Export to JSON, CSV or Excel.

**[▶ Try the Contact Details Scraper free on Scrapely](https://scrape.ly/store/cornerledger/contact-info-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Contact Details data with the [Contact Details Scraper](https://scrape.ly/store/cornerledger/contact-info-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the contact details scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Contact Details scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/cornerledger/contact-info-scraper) or from your code with the SDK.
- **Structured contact details data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $2.00 per 1,000 scraped page results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Contact Details changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Contact Details data can you extract?

Extract emails, phone numbers and social media links from any website. Crawl contact pages in bulk for lead generation. Export to JSON, CSV or Excel.

| Output field |
|---|
| `originalStartUrl` |
| `url` |
| `domain` |
| `emails` |
| `phones` |
| `phonesUncertain` |
| `linkedIns` |
| `twitters` |
| `instagrams` |
| `facebooks` |
| `youtubes` |
| `tiktoks` |
| `error` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('cornerledger/contact-info-scraper').call({"startUrls": [{"url": "https://kde.org/"}], "maxRequestsPerStartUrl": 10, "maxDepth": 2, "maxRequests": 100, "sameDomain": true, "mergeContacts": true, "considerChildFrames": true, "useBrowser": false, "waitUntil": "domcontentloaded", "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('cornerledger/contact-info-scraper').call(run_input={ "startUrls": [ { "url": "https://kde.org/" } ], "maxRequestsPerStartUrl": 10, "maxDepth": 2, "maxRequests": 100, "sameDomain": True, "mergeContacts": True, "considerChildFrames": True, "useBrowser": False, "waitUntil": "domcontentloaded", "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/cornerledger~contact-info-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "startUrls": [
    {
      "url": "https://kde.org/"
    }
  ],
  "maxRequestsPerStartUrl": 10,
  "maxDepth": 2,
  "maxRequests": 100,
  "sameDomain": true,
  "mergeContacts": true,
  "considerChildFrames": true,
  "useBrowser": false,
  "waitUntil": "domcontentloaded",
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [Contact Details Scraper page](https://scrape.ly/store/cornerledger/contact-info-scraper).

## Pricing

**$2.00 per 1,000 scraped page results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/cornerledger/contact-info-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Contact Details with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Contact Details with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a contact details scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/cornerledger~contact-info-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Contact Details legal?** This scraper collects publicly available data. Check Contact Details's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** contact details scraper, contact details scraper, contact details scraper api, contact details scraper python, contact details scraper node.js,
scrape contact details, contact details data extraction, contact details crawler, contact details api, export contact details data to csv, contact-info-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/cornerledger/contact-info-scraper).
