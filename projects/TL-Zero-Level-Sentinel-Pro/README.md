<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
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

## What It Is

Udine's "As simple as possible: 00 level trading" (Forex Factory thread 487923, 2014) plus the filters JibalaPasan and her team (Nathalia, Ron) described in about 680 posts for their private "WSD" dashboard and "Market Sentinel". Their tool was never released, so this is a rebuild from the posts, not a copy.

## The Rules (each one can be switched off)

Udine (post #1):
- D1 and H1 candle in the same colour (team: D1, H4, H1 and M15)
- Pending STOP order on the FIRST 00 level after the daily open
- Frankfurt hour: only .400 / .500 / .600 levels, London: all levels
- No long at .900, no short at .100, entry > 10 pips from the big round number
- No trading 1 h before / 30 min after red news on either currency
- Stop after 4 losses a day and after the daily target
- SL 10 pips, TP 5 pips (team: TP = 10 - spread - commission), 1 trade per hour per pair
Team extensions (dates of the posts in brackets):
- 7 pip buffer around the daily open (08/2014)
- Entry level 10..30 pips from the open, only level 1 or 2 (09/2014, 2020)
- ADR room: RmUp / RmDn must hold the TP + 3 pips (08/2014)
- Currency strength of all 28 pairs: buy the strong, sell the weak (gap), the currency you buy must beat the market strength (01/2015)
- Correlated pairs in sync (PsyLevel board, 08/2014)
- Momentum, no entry after an M15 bar that crossed 4 levels (2020)
- Optional RSI(2) 85/15 (10/2014), spread filter, break-even / trailing (Udine)

## Gold / Indices

Distance scaling AUTO: forex uses pips like the thread, gold and indices scale every distance (level step, SL, TP, buffers) with their ADR against a reference of 100 pips. The level step snaps to a round number (e.g. 5 USD on gold).

## The Dashboard

- Sentinel: status of the chart symbol (WAIT / READY / ARMED / IN TRADE) with the first failing rule, D1-H4-H1-M15 chips, level ladder, ADR room
- Rules checklist: all 20 rules live, hover a row for its source in the thread
- Currency strength of the 8 currencies + market strength
- WSD board: all 28 pairs (+ chart symbol), click a row to open its chart
- Today: trades, losses x/4, pips, P/L, target, next red news
- X closes it to a pill, drag the header to move it, MINI / FULL toggles the size

## Install

- MT5: copy "TL Zero Level Sentinel Pro.ex5" to MQL5\Experts, MT4: the .ex4 to MQL4\Experts. Attach it to ONE chart (any symbol, M15 recommended). Default scope = trade list (Jibala's 8 pairs) + the chart symbol, so one chart trades all of them. Red news: Tools > Options > Expert Advisors > Allow WebRequest for <https://nfs.faireconomy.media>  (MT5 falls back to its built-in calendar). Buttons (YouTube / RoboForex / WhatsApp / Forex Factory) need "Allow DLL imports". Your broker needs all 28 pairs in the symbol list for the strength filters (prefix / suffix are detected automatically).

- Test on demo first. Trading involves high risk. You trade at your own risk.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
