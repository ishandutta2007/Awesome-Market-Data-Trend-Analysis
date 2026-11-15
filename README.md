# Awesome-Market-Data-Trend-Analysis

# Awesome Market & Data Trend Analysis

> A curated list of top Market and Data Trend Analysis platforms — both SaaS/Hosted commercial solutions and open-source alternatives for discovering emerging trends, analyzing market data, and tracking competitive intelligence.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Google Trends](#google-trends)
  - [Exploding Topics](#exploding-topics)
  - [CB Insights](#cb-insights)
  - [PitchBook](#pitchbook)
  - [Crunchbase](#crunchbase)
  - [Similarweb](#similarweb)
  - [Semrush](#semrush)
- [Open-Source Software](#-open-source-software)
  - [TrendPulse](#trendpulse)
  - [TrendScout Radar](#trendscout-radar)
  - [Pre-Viral Tracker](#pre-viral-tracker)
  - [Capbase](#capbase)
  - [SerpBear](#serpbear)
  - [Alion (LangChain Toolkit)](#alion-langchain-toolkit)
  - [finasys](#finasys)
  - [pyita](#pyita)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Market and Data Trend Analysis platforms. These are not open-source but are included as reference points for feature comparison.

### Google Trends
**Type:** Search interest exploration and comparison
Google Trends is the canonical free tool for exploring search interest over time, comparing keywords, and identifying regional demand. It provides normalized 0–100 interest scores, related queries, and trending searches. **Trade-off:** Values are relative, not absolute volumes, and the UI lacks programmatic access without third-party wrappers.

### Exploding Topics
**Type:** Early trend discovery for emerging topics
Exploding Topics surfaces topics that are growing rapidly before they hit mainstream search volume. It is the primary commercial reference for open-source alternatives like Pre-Viral Tracker and TrendScout Radar, which explicitly position themselves as alternatives[citation:4][citation:10].

### CB Insights
**Type:** Market intelligence and startup data
CB Insights provides market maps, company profiles, funding data, and trend analysis for venture capital and corporate strategy teams. It is a premium commercial platform with no direct open-source equivalent, though Capbase offers a community-driven funding database alternative[citation:8].

### PitchBook
**Type:** Private capital market data
PitchBook provides comprehensive data on private companies, investors, fundings, and M&A activity. Like CB Insights, it is a premium commercial platform, with Capbase positioning itself as a free open-source alternative for funding data[citation:8].

### Crunchbase
**Type:** Startup and company intelligence
Crunchbase provides company profiles, funding rounds, investor data, and market trends. It is the most widely recognized startup database, with Capbase explicitly positioned as a free open-source alternative[citation:8].

### Similarweb
**Type:** Website traffic and competitive intelligence
Similarweb provides website traffic estimates, rankings, audience insights, and competitor analysis. It is the commercial benchmark for traffic intelligence, with open-source alternatives like SerpBear focusing on the SEO-driven estimation angle[citation:3][citation:13].

### Semrush
**Type:** SEO and competitive research
Semrush provides keyword research, competitor analysis, backlink data, and traffic estimates. SerpBear is positioned as the closest open-source alternative to its core keyword-ranking logic[citation:13].

---

## 🟩 Open-Source Software

Self-hosted, community-driven Market and Data Trend Analysis tools. The open-source ecosystem spans **multi-source trend aggregators**, **early-signal detection engines**, **community-driven funding databases**, **SEO traffic estimators**, **company intelligence toolkits**, and **financial data processing libraries**.

### TrendPulse
**Stack:** Python / SQLite / MCP | **License:** Open Source (PyPI)
TrendPulse is a global open-source agentic trend intelligence platform with **35+ sources**, a plugin system, vector search, trend clustering, lifecycle prediction, a 6-agent content factory, a web dashboard, and a **23-tool MCP server** . Key capabilities include:
- **Multi-source aggregation**: Google Trends, Hacker News, Mastodon, Bluesky, Wikipedia, GitHub, PyPI, Google News, Lobsters, dev.to, npm, CoinGecko, Docker Hub, Stack Overflow, arXiv, Product Hunt, Lemmy, Dcard, and PTT[citation:1][citation:12]
- **Velocity tracking**: With history data saved to SQLite, each trend includes direction (rising/stable/declining) and velocity score[citation:12]
- **Normalized scoring**: Each item has a 0–100 score for cross-source comparison[citation:1]
- **Custom sources**: Simple `TrendSource` subclasses return `list[TrendItem]`[citation:1]
- **MCP server**: 23 tools for AI agent integration[citation:12]

Deploys as a CLI (`trend-pulse trending --save`) with optional web dashboard. **Trade-off:** Source coverage varies by region and rate limits (e.g., Google Trends RSS is unlimited, PyPI Stats is 1 req/day)[citation:1].
**Best for:** Teams wanting a comprehensive, multi-source trend aggregation platform with velocity tracking and AI agent integration via MCP.

### TrendScout Radar
**Stack:** Python / GitHub Actions | **License:** Open Source (GitHub)
TrendScout Radar is an open-source trend radar that tracks what's trending on **TikTok, YouTube, Reddit, Google, X, and Hacker News** for your topics, pushing alerts to Telegram, Discord, Slack, or email . It is explicitly positioned as an **Exploding Topics alternative**[citation:4]. Key characteristics:
- **Topic-based alerts**: Each topic matches items by title keywords, with configurable alert channels and schedules
- **Breakout detection**: A term trending on 3+ platforms simultaneously is flagged as a breakout
- **Free tier**: Google Trends, Hacker News front page, and per-topic Google News/Hacker News search run without any API key
- **Paid tier (Scavio)**: TikTok, Reddit, X, YouTube require a Scavio key (~7 credits per scan)
- **Deployment**: Self-hosted or free on GitHub Actions

**Best for:** Marketers and creators wanting self-hosted trend monitoring with multi-platform breakout detection and alerting to messaging channels.

### Pre-Viral Tracker
**Stack:** Python / FastAPI | **License:** Open Source (GitHub)
Pre-Viral Tracker is a full-stack trend discovery engine that **detects accelerating niche topics before they hit mainstream** . It is explicitly positioned as an **Exploding Topics or Glimpse alternative** that runs locally[citation:10]. Key characteristics:
- **Velocity and acceleration signals**: Computes volume (0–100), velocity (first derivative), acceleration (second derivative), and R² confidence
- **Pre-Viral Score**: A composite 0–100 score combining all signals, with an exponential bonus (×1.3) for keywords fitting an exponential curve
- **Regional discovery**: Scans 8 regions including Global, US, UK, and EU Big 4
- **Mock data fallback**: Synthetic data fills gaps when APIs are rate-limited
- **Architecture**: FastAPI REST API with 13 endpoints

**Trade-off:** It is a locally-run application rather than a hosted service—you operate the FastAPI server and database yourself.
**Best for:** Analysts wanting a quantitative, locally-run early-signal detector with velocity/acceleration scoring and regional discovery.

### Capbase
**Stack:** Community-driven | **License:** Open Source
Capbase is an open-source alternative to **Crunchbase and PitchBook**, built as a community-filled funding database[citation:8]. Key characteristics:
- **Community-driven**: Share a funding round or fix a company's details, and once approved, every profile unlocks for 30 days free
- **Data sources**: Pulls from SEC filings, SBIR, Innovate UK, Companies House, and Wikidata
- **Positioning**: Explicitly addresses frustration with paying thousands a year just to see who funded a startup

**Trade-off:** It is a community database rather than a comprehensive intelligence platform—coverage depends on contributions and the listed public sources.
**Best for:** Founders, investors, and researchers wanting a free, community-maintained funding database without Crunchbase/PitchBook subscription costs.

### SerpBear
**Stack:** (Check repository) | **License:** Open Source
SerpBear is an open-source SEO rank tracker that estimates competitor traffic using the **"keyword ranking × search volume"** model, making it the closest open-source alternative to Semrush's core traffic estimation logic[citation:13]. It provides keyword rank tracking and traffic estimation based on search visibility. **Trade-off:** It estimates traffic from SEO signals rather than providing direct traffic measurement like Similarweb.
**Best for:** SEO teams and marketers wanting open-source keyword rank tracking with traffic estimation, particularly those frustrated with Semrush pricing.

### Alion (LangChain Toolkit)
**Stack:** Python / LangChain / MCP | **License:** Open Source (PyPI)
Alion provides LangChain tools for a **live graph of companies worldwide**, including what each one does, where it operates, tech stack, funding rounds and investors, hiring velocity, and pay statistics . It is positioned for agents that need prospect lists, company enrichment, lookalike discovery, investor research, and market pay data[citation:2]. Key capabilities:
- **Company search**: By industry, country, size, founding year, startup status, funding stage, recent rounds, investor, technology, ATS, hiring, and growth level
- **Lookalikes**: Find similar companies
- **Counterparty verification**: Check whether a domain, site, email, or agent is a real, active counterparty
- **Job and pay data**: Verified job postings and market pay percentiles
- **Free tier**: Company search, lookalikes, resolve, counterparty check, and job search work without an API key (300 calls/day)

**Trade-off:** It is a **toolkit for AI agents**, not a standalone dashboard—you integrate it into a LangChain or MCP workflow.
**Best for:** Developers building AI agents for market research, prospecting, or competitive intelligence who need structured company data via a free API.

### finasys
**Stack:** Python / Polars | **License:** Open Source (PyPI)
finasys is a financial data processing toolkit for **ML pipelines and AI agents**, explicitly designed to go from raw market data to ML-ready features in a few lines of code[citation:5]. Key capabilities:
- **Data loading**: Single `fs.load()` entry point for Yahoo Finance, CSV, and Parquet, with DuckDB-backed caching
- **Feature engineering**: 15+ technical indicators (RSI, MACD, Bollinger Bands, ATR, VWAP, OBV, Stochastic, ADX, CCI, Williams %R, MFI, ROC, Momentum), returns, rolling statistics, and lag features
- **Target engineering**: Forward returns, classification labels, triple-barrier labeling (Lopez de Prado method), and volatility-adjusted labels
- **Market regime features**: Volatility regimes, trend strength, and distribution features
- **Performance**: Polars-native, 10-100x faster than pandas-ta with zero C dependencies

**Trade-off:** It is a **data processing library** rather than a trend dashboard—you build the analysis and visualization on top.
**Best for:** Quant developers and data scientists wanting fast, dependency-free financial feature engineering for ML pipelines.

### pyita
**Stack:** Python | **License:** Open Source (PyPI)
pyita is a technical analysis library for calculating indicators from OHLCV data, with a simple `Quotes` object that can be constructed from numpy arrays, pandas DataFrames, CCXT exchange data, or dictionaries[citation:11]. Key indicators include:
- **Moving averages**: SMA, EMA, TEMA, VWMA, and a universal `ma()` function
- **Trend indicators**: ADX, Aroon, Parabolic SAR, Supertrend
- **Bollinger Bands**: With upper, middle, and lower lines

**Trade-off:** It is a calculation library, not a trend analysis platform—you supply the data and interpret the indicators.
**Best for:** Python developers wanting a lightweight, dependency-free technical analysis library for building custom market analysis tools.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Trend Discovery | Funding Data | Traffic Estimation | Self-Hosted | Best For |
|----------|---------|-------|-----------------|--------------|---------------------|-------------|----------|
| **Google Trends** | Proprietary | Cloud | ✅ | ❌ | ❌ | ❌ | Search interest baseline |
| **Exploding Topics** | Proprietary | Cloud | ✅ Early signals | ❌ | ❌ | ❌ | Emerging topic discovery |
| **CB Insights** | Proprietary | Cloud | ✅ | ✅ | ❌ | ❌ | Market intelligence |
| **PitchBook** | Proprietary | Cloud | ✅ | ✅ | ❌ | ❌ | Private capital data |
| **Crunchbase** | Proprietary | Cloud | ✅ | ✅ | ❌ | ❌ | Startup intelligence |
| **Similarweb** | Proprietary | Cloud | ❌ | ❌ | ✅ | ❌ | Website traffic intel |
| **Semrush** | Proprietary | Cloud | ❌ | ❌ | ✅ | ❌ | SEO competitive research |
| **TrendPulse** | Open Source | Python/SQLite | ✅ 35+ sources | ❌ | ❌ | ✅ | Multi-source aggregation + MCP |
| **TrendScout Radar** | Open Source | Python/Actions | ✅ Breakouts | ❌ | ❌ | ✅ | Topic alerts + multi-platform |
| **Pre-Viral Tracker** | Open Source | Python/FastAPI | ✅ Acceleration | ❌ | ❌ | ✅ | Early-signal scoring |
| **Capbase** | Open Source | Community | ❌ | ✅ | ❌ | ✅ | Free funding database |
| **SerpBear** | Open Source | (Check) | ❌ | ❌ | ✅ SEO-based | ✅ | Keyword rank + traffic estimate |
| **Alion** | Open Source | Python/LangChain | ❌ | ✅ (via API) | ❌ | ✅ (Toolkit) | AI agent company data |
| **finasys** | Open Source | Python/Polars | ❌ (Market data) | ❌ | ❌ | ✅ (Library) | ML-ready financial features |
| **pyita** | Open Source | Python | ❌ (Indicators) | ❌ | ❌ | ✅ (Library) | Technical analysis calc |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Market or Data Trend Analysis tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

**Note on the open-source ecosystem:** The open-source landscape for market and trend analysis is **fragmented across distinct layers** rather than unified platforms. For **trend discovery**, **TrendPulse** is the most comprehensive multi-source aggregator with 35+ sources and MCP support[citation:1][citation:12], while **TrendScout Radar** and **Pre-Viral Tracker** offer focused alternatives with breakout detection and acceleration scoring respectively[citation:4][citation:10]. For **company and funding data**, **Capbase** fills the Crunchbase/PitchBook gap with a community-driven model[citation:8], and **Alion** provides structured company intelligence as a toolkit for AI agents[citation:2]. For **traffic and SEO intelligence**, **SerpBear** offers keyword rank tracking with traffic estimation as a Semrush alternative[citation:13]. For **financial data processing**, **finasys** and **pyita** provide the computational foundation for market analysis[citation:5][citation:11]. No single open-source project replicates the full breadth of CB Insights or Similarweb, but these tools cover the core layers of trend discovery, company intelligence, and financial analysis for self-hosted workflows.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
