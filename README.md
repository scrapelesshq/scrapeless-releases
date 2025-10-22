<h1 align="center">🔥 Browser Infra for Crawling, Automation, and AI Agents</h1>

<div align="center">
  <img src="static/image/logo-new.svg" style="width: 120px; height: 120px;" alt="logo">

  <h2 align="center">Cloud Browser | Proxies | Crawl | Scraping API | Enterprise Custom Solutions</h2>

  ![Static Badge](https://img.shields.io/badge/Browser-Headless_Cloud%20Browser-%2312A594)
  ![Static Badge](https://img.shields.io/badge/Proxy-195%20Countries%20%E2%80%93%200.5%24%2F1GB-%2312A594)
  ![Static Badge](https://img.shields.io/badge/Fingerprint-Customizable-%2312A594)
  ![Static Badge](https://img.shields.io/badge/Captcha-Beat%20Anti--Bots%20in%20Real%20Time-%2312A594)
  
  ![Static Badge](https://img.shields.io/badge/Serp-Deep%20SerpAPI-%2312A594)
  ![Static Badge](https://img.shields.io/badge/Unlocker-Universal%20Scraping%20API-%2312A594)
  
  <p align="center">
    <a href="https://www.youtube.com/@Scrapeless" target="_blank">
      <img src="https://img.shields.io/badge/Follow%20on%20YouTuBe-FF0033?style=for-the-badge&logo=youtube&logoColor=white" alt="Follow on YouTuBe" />
    </a>
    <a href="https://discord.com/invite/xBcTfGPjCQ" target="_blank">
      <img src="https://img.shields.io/badge/Join%20our%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Join our Discord" />
    </a>
    <a href="https://x.com/Scrapelessteam" target="_blank">
      <img src="https://img.shields.io/badge/Follow%20us%20on%20X-000000?style=for-the-badge&logo=x&logoColor=white" alt="Follow us on X" />
    </a>
    <a href="https://www.reddit.com/r/Scrapeless" target="_blank">
      <img src="https://img.shields.io/badge/Join%20us%20on%20Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white" alt="Join us on Reddit" />
    </a> 
    <a href="https://app.scrapeless.com/passport/register?utm_source=official&utm_term=githubopen" target="_blank">
      <img src="https://img.shields.io/badge/Official%20Website-12A594?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Official Website"/>
    </a>
  </p>

</div>

---

<h1 align="center">🚀 Select the product & get started</h2>

### First, install the SDK
```bash
# Install the official Scrapeless SDK
npm install @scrapeless-ai/sdk
```

### Click [here](https://app.scrapeless.com/passport/register?utm_source=official&utm_term=githubopen) to obtain your API-KEY

---

### Browser
A self-developed Chromium cloud browser, built for AI Agents and automated crawling — with strong customization, anti-detection, and extensibility.

#### Writing Code to Connect to Browser
You can connect using Puppeteer or Playwright adapters provided by the SDK.

**Puppeteer**
```javascript
import { Puppeteer } from '@scrapeless-ai/sdk';

const browser = await Puppeteer.connect({
  apiKey: 'YOUR_API_KEY',
  sessionName: 'sdk_test',
  sessionTTL: 180,
  proxyCountry: 'ANY',
  sessionRecording: true,
  defaultViewport: null,
});

const page = await browser.newPage();
await page.goto('https://www.scrapeless.com');
console.log(await page.title());
await browser.close();
```

**Playwright**
```javascript
import { Playwright } from '@scrapeless-ai/sdk';

const browser = await Playwright.connect({
  apiKey: 'YOUR_API_KEY',
  proxyCountry: 'ANY',
  sessionName: 'sdk_test',
  sessionRecording: true,
  sessionTTL: 180,
});

const context = browser.contexts()[0];
const page = await context.newPage();
await page.goto('https://www.scrapeless.com');
console.log(await page.title());
await browser.close();
```

---

### Universal Scraping API
Dynamic web scraping API with JS interaction and multi-format parsing—breaks through anti-scraping barriers to extract target information with precision. Supports multi-format data export (Markdown / JSON / Screenshot / HTML / Links).

**Capture Data via SDK Endpoint**
```javascript
import { Scrapeless } from '@scrapeless-ai/sdk';

const client = new Scrapeless({
  apiKey: 'YOUR_API_KEY'
});

client.universal.scrape({
   actor: "unlocker.webunlocker",
   input: {
      url: "https://httpbin.io/get",
      redirect: false,
      method: "GET",
   },
   proxy: {
      country: "ANY",
   }
}).then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.error('Error:', error);
  });
```

---

### Crawl
A crawling engine designed for recursive scraping of single pages and sub-pages. It automatically solves CAPTCHAs and supports multi-format data export, including Markdown, JSON, screenshots, HTML, and links.

**How to initiate a web scraping request through Scrapeless SDK**
```javascript
import { ScrapingCrawl } from '@scrapeless-ai/sdk';

// Initialize the client
const client = new ScrapingCrawl({
  apiKey: 'YOUR_API_KEY', // Get your API key from https://scrapeless.com
});

(async () => {
  const result = await client.scrapeUrl('https://example.com');
  console.log(result);
})();
```


### Browser Configurations
Scrapeless automatically handles common CAPTCHA types, including reCAPTCHA v2 and Cloudflare Turnstile/Challenge.

```javascript
import { ScrapingCrawl } from '@scrapeless-ai/sdk';

// Initialize the client
const client = new ScrapingCrawl({
  apiKey: 'YOUR_API_KEY',
});

(async () => {
  const result = await client.scrapeUrl('https://example.com', {
    browserOptions: {
      proxyCountry: 'ANY',
      sessionName: 'Crawl',
      sessionRecording: true,
      sessionTTL: 900,
    },
  });
  console.log(result);
})();
```


### Scrape Configurations
Provide optional parameters such as return formats, only returning main content, navigation timeout, etc.

```javascript
import { ScrapingCrawl } from '@scrapeless-ai/sdk';

const client = new ScrapingCrawl({
  apiKey: 'YOUR_API_KEY',
});

(async () => {
  const result = await client.scrapeUrl('https://example.com', {
    formats: ['markdown', 'html', 'links'],
    onlyMainContent: false,
    timeout: 15000,
  });
  console.log(result);
})();
```


### Batch Scrape
Batch scraping supports multiple URLs at once.

```javascript
import { ScrapingCrawl } from '@scrapeless-ai/sdk';

const client = new ScrapingCrawl({
  apiKey: 'YOUR_API_KEY',
});

(async () => {
  const result = await client.batchScrapeUrls(
    ['https://example.com', 'https://scrapeless.com'],
    {
      formats: ['markdown', 'html', 'links'],
      onlyMainContent: false,
      timeout: 15000,
      browserOptions: {
        proxyCountry: 'ANY',
        sessionName: 'Crawl',
        sessionRecording: true,
        sessionTTL: 900,
      },
    }
  );
  console.log(result);
})();
```

---

### Deep SerpApi
Google SERP API with fast response and cost-effective pricing—delivers real-time organic results, ads & snippets.

**Code Example: Extract search engine results**
```javascript
import { Scrapeless } from '@scrapeless-ai/sdk';

const client = new Scrapeless({
  apiKey: 'YOUR_API_KEY'
});

client.deepserp.createTask({
    actor: "scraper.google.search",
    input: {
        q: "Top news headlines",
        gl: "us",
        hl: "en",
        google_domain: "google.com"
    }
}).then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.error('Error:', error);
  });
```
---
