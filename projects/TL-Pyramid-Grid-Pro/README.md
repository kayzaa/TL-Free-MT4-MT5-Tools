<div align="center">

# ⚡ TL Pyramid Grid Pro

**Pyramid grid with stop orders on both sides — adds only while the market runs in that direction (anti-martingale).**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_PyramidGridPro_screenshot.png" alt="TL Pyramid Grid Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Pyramid Grid Pro.ex4`](MT4/TL%20Pyramid%20Grid%20Pro.ex4) |
| **MT5** | [`TL Pyramid Grid Pro.ex5`](MT5/TL%20Pyramid%20Grid%20Pro.ex5) |

> Compiled build only — source code is not published.

## What It Does

A pyramid grid with stop orders on BOTH sides of the price. Buy stops above, sell stops below. A new section of orders is added only while the market keeps running in that direction - the position grows with the trend (anti-martingale), never against it. Every order has its own stop loss, take profit and break even. The lot follows the capital of the EA up and down.

## Install

- MT5: copy "TL Pyramid Grid Pro.ex5" to  File > Open Data Folder > MQL5 > Experts
- MT4: copy "TL Pyramid Grid Pro.ex4" to  File > Open Data Folder > MQL4 > Experts Restart / refresh the Navigator, drag the EA onto any chart (timeframe does not matter).
- Enable "Algo Trading" / "AutoTrading". Enable "Allow DLL imports" only if you want the link buttons in the panel to open your browser - trading works without it.
- MT5 needs a HEDGING account (every order is its own position).

## First Steps

- Demo account first. Grid trading is high risk.
- Start lot: 0.01 per 1000 of account money is a sane start (0.01 per 100 is aggressive).
- Pick a preset or use CUSTOM (default = Classic: 3 orders, gap 10, step 40, SL 30, TP 200, BE 40/30).
- Optional: set a cycle profit target and a cycle loss limit, a trading window (e.g. 09:00-19:00), the MA direction filter and a kill switch.

## Input Groups

0 Preset      - Custom, Classic, Aggressive (no SL), One by one, Scalper, Mega grid, Long term, Tight hedge, Gold. A preset overrides groups 1, 2 and 4. 1 Grid        - sides on/off, orders per section, gap, section step, start gap (no-trade zone), hedge follows price, SL, TP, bundle stops, max positions per side. 2 Break even  - BE start + lock (lock can be negative), 2nd BE step, trailing stop. 3 Lot         - start lot, lot follows capital, dynamic lot jump, max lot, capital, resize pendings. 4 After SL    - delete pendings after a real stop loss, restart: breakout / next candle / instantly. 5 Cycle       - unit % or money, profit target, loss limit, loss recovery, profit lock, reset on TP, pause after target, close above / below price. 6 Protection  - daily profit target, daily loss limit, kill switch, max spread. 7 Time/filter - trading window, close at window end, Friday close, MA direction filter. 8 Display     - panel, position, tooltips (hover boxes), next-section lines, colours, alerts. 9 Other       - start paused, magic number, comment, slippage, pip size override.

## Panel

Drag the header to move it, X closes it to a small pill, click the pill to open it again. Hover over any row for an explanation. PAUSE / RESUME and CLOSE ALL buttons.

## Risk

No profit promise. Trending markets favour the grid, sideways markets produce series of small stop losses. Test every setting on a demo account and on your broker first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
