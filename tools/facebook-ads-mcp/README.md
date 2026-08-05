# Facebook Ads Library MCP (vendored)

Vendored from [RamsesAguirre777/facebook-ads-library-mcp](https://github.com/RamsesAguirre777/facebook-ads-library-mcp)
(MIT). Wraps Meta's public Ad Library API so agents can search competitor ads.

`README.upstream.md` is the original project README, kept for reference. Read
the caveats below before trusting its claims.

## Setup

```bash
cd tools/facebook-ads-mcp
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
```

Then get a token: [Graph API Explorer](https://developers.facebook.com/tools/explorer/)
→ generate a token with `ads_read` → optionally
[extend it to 60 days](https://developers.facebook.com/tools/debug/accesstoken/).

The repo root `.mcp.json` registers this server and reads the token from the
`FACEBOOK_ACCESS_TOKEN` environment variable, so export it before starting
Claude Code:

```bash
export FACEBOOK_ACCESS_TOKEN=your_token_here
```

Point `.mcp.json`'s `command` at `tools/facebook-ads-mcp/.venv/bin/python` if
your system `python3` doesn't have `fastmcp` installed.

The token is never committed. Keep it out of git.

## Tools that actually exist (7)

| Tool | What it does |
|---|---|
| `search_facebook_ads` | Keyword/brand search against the Ad Library |
| `discover_competitor_brands` | Groups search hits by page name, ranks by ad count |
| `analyze_ad_creative_elements` | Scrapes an ad snapshot URL, counts CTA/urgency words |
| `analyze_ad_performance_metrics` | Aggregates impressions/spend across a brand's ads |
| `competitive_ad_analysis` | Runs the search across several brands and compares |
| `generate_facebook_intelligence_report` | Bundles the above into one report |
| `export_facebook_ads_data` | Dumps results as JSON/CSV/Markdown |

## Changes made to upstream

1. **Fixed a startup crash.** Upstream imported `WebCrawler` from `crawl4ai` at
   module scope. That class was removed from crawl4ai long ago, so the import
   raised `ImportError` and the server could never boot — no tool was reachable.
   The import is now optional and uses the current `AsyncWebCrawler` API.
2. **Made `crawl4ai` optional.** It backs only `analyze_ad_creative_elements`.
   When it isn't installed, that one tool returns a clear message and the other
   six work normally.
3. **Trimmed `requirements.txt`** to what the module imports. Upstream listed
   selenium, pandas, numpy, beautifulsoup4, httpx, aiohttp, pytest, black and
   flake8; none are used.

## Caveats worth knowing

- **The README claims "15+ tools"; 7 exist.** `find_similar_advertisers`,
  `analyze_ad_targeting_insights`, `monitor_brand_ad_changes`,
  `track_ad_spend_estimation`, `benchmark_against_industry`,
  `identify_market_opportunities` and `predict_ad_performance` are advertised
  but not implemented. The "ML-powered performance prediction" is one of the
  missing ones — there is no ML anywhere in the codebase.
- **Spend and impressions are blank for ordinary commercial ads.** Meta only
  populates `spend`, `impressions`, `demographic_distribution` and
  `delivery_by_region` for political and issue ads. For competitors in the
  pregnancy/postpartum space, `analyze_ad_performance_metrics` will mostly
  report zeros. What you *can* reliably get is ad creative text, page name,
  run dates, platforms and snapshot URLs — which is the genuinely useful part
  for studying competitor messaging and hooks.
- **`discover_competitor_brands` doesn't know your industry.** It searches your
  keyword and tallies which pages show up most. Quality depends entirely on the
  keyword you give it.

## You may not need this

The Facebook connector already available in Claude has an `ads_library_search`
tool covering the core search, already authenticated, with no token setup. This
vendored server is worth running for the aggregation and export tools layered
on top; for plain "show me competitor ads," the built-in is less work.
