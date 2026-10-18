<div align="center">

# ⚡ TL Zero Level Sentinel Pro

**Udine's "00 level trading" (FF 487923) plus the WSD / Market Sentinel filters from ~680 thread posts — rebuilt as a tool.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_ZeroLevelSentinelPro_screenshot.png" alt="TL Zero Level Sentinel Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Zero Level Sentinel Pro.ex4`](MT4/TL%20Zero%20Level%20Sentinel%20Pro.ex4) |
| **MT5** | [`TL Zero Level Sentinel Pro.ex5`](MT5/TL%20Zero%20Level%20Sentinel%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Udine's "00 level trading"** from Forex Factory, rebuilt as an EA — pending stop orders on the first round level after the daily open.
- **Plus the WSD / Market Sentinel filters** JibalaPasan and her team described across about 680 posts — a tool that was never released, rebuilt from the posts.
- **20 rules, live** — every rule can be switched off, and you can hover each one to see its source in the thread.
- **28-pair WSD board + currency strength** of all 8 currencies and the overall market strength.
- **One chart trades the whole list** — Jibala's 8 pairs plus the chart symbol by default.
- **Gold and indices supported** — every distance scales automatically with the symbol's ADR.

## 🧠 Strategy rules

Every rule below can be switched off.

**Udine (post #1)**

- D1 and H1 candle in the same colour (team: D1, H4, H1 and M15).
- **Pending STOP order on the FIRST 00 level** after the daily open.
- Frankfurt hour: only .400 / .500 / .600 levels; London: all levels.
- No long at .900, no short at .100; entry more than 10 pips from the big round number.
- No trading 1 h before / 30 min after red news on either currency.
- Stop for the day after 4 losses and after the daily target.
- **SL 10 pips, TP 5 pips** (team: TP = 10 − spread − commission), 1 trade per hour per pair.

**Team extensions** (post dates in brackets)

- 7-pip buffer around the daily open (08/2014).
- Entry level 10–30 pips from the open, only level 1 or 2 (09/2014, 2020).
- ADR room: RmUp / RmDn must hold the TP + 3 pips (08/2014).
- Currency strength of all 28 pairs: buy the strong, sell the weak (gap); the currency you buy must beat the market strength (01/2015).
- Correlated pairs in sync (PsyLevel board, 08/2014).
- Momentum: no entry after an M15 bar that crossed 4 levels (2020).
- Optional RSI(2) 85 / 15 (10/2014), spread filter, break-even / trailing (Udine).

### Gold / indices

Distance scaling **AUTO**: forex uses pips like the thread; gold and indices scale every distance (level step, SL, TP, buffers) with their ADR against a reference of 100 pips. The level step snaps to a round number (e.g. 5 USD on gold).

## 🖥️ Dashboard & chart

| Panel | What it shows |
|---|---|
| **Sentinel** | Status of the chart symbol (WAIT / READY / ARMED / IN TRADE) with the first failing rule, D1-H4-H1-M15 chips, level ladder, ADR room. |
| **Rules checklist** | All 20 rules live — hover a row for its source in the thread. |
| **Currency strength** | The 8 currencies + market strength. |
| **WSD board** | All 28 pairs (+ chart symbol); click a row to open its chart. |
| **Today** | Trades, losses x/4, pips, P/L, target, next red news. |

**X** closes the dashboard to a pill, drag the header to move it, and **MINI / FULL** toggles the size.

## 📋 Requirements

- Your broker needs **all 28 pairs** in the symbol list for the strength filters (prefix / suffix are detected automatically).
- Red-news filter: allow WebRequest for `https://nfs.faireconomy.media` (MT5 falls back to its built-in calendar).

## 🛠️ Installation

1. Open `File → Open Data Folder`. **MT5:** copy `TL Zero Level Sentinel Pro.ex5` to `MQL5 → Experts`. **MT4:** copy `TL Zero Level Sentinel Pro.ex4` to `MQL4 → Experts`.
2. Refresh the Navigator and attach the EA to **one** chart (any symbol, **M15 recommended**). The default scope is the trade list (Jibala's 8 pairs) plus the chart symbol, so one chart trades all of them.
3. For red news: `Tools → Options → Expert Advisors → Allow WebRequest` for `https://nfs.faireconomy.media`.
4. Enable **Allow DLL imports** only if you want the link buttons (YouTube / RoboForex / WhatsApp / Forex Factory) to open your browser.

## 🙏 Credits

- **Udine** — "As simple as possible: 00 level trading", Forex Factory thread 487923 (2014).
- **JibalaPasan** and her team (**Nathalia**, **Ron**) — the WSD dashboard and Market Sentinel filters described in the thread. Their tool was never released; this is a rebuild from the posts, not a copy.

## ⚠️ Notes

- With a 10-pip stop and a 5-pip target, spread and commission weigh heavily — test on a demo account first.
- Trading involves high risk. You trade at your own risk.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
