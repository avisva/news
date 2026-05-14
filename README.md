# News SPA

Simple single-page HTML site that fetches news via a small proxy server to keep the NewsAPI key on the server.

Setup

1. Copy your NewsAPI API key into an environment variable named `NEWSAPI_KEY`.
2. Install dependencies and start the server:

```bash
npm install
SET NEWSAPI_KEY=your_key_here   # Windows cmd
# or
export NEWSAPI_KEY=your_key_here # macOS / Linux
npm start
```

Open http://localhost:3000 in your browser.

Notes
- The server proxies requests to newsapi.org; do not put the API key in client-side code.
- Free NewsAPI accounts have rate limits and usage rules; see https://newsapi.org
