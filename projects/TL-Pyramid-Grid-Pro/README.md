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

## ✨ Highlights

- **Pyramids with the trend, never against it.** Buy stops above, sell stops below — new sections are added only while the market keeps running in that direction (anti-martingale).
- **Every order protected.** Each order has its own stop loss, take profit and break-even.
- **Lot follows the capital** of the EA, up and down.
- **Nine presets** — from Classic to Gold — or full CUSTOM control.
- **Cycle, daily and kill-switch protection** plus trading window and MA direction filter.
- **MT4 + MT5**, with a draggable panel and one-click PAUSE / CLOSE ALL.

## 🧠 How it works

The EA places stop orders on **both sides** of the price: **buy stops above, sell stops below**. When price runs in one direction, it triggers that side's orders and the next section of orders is added further along — the position grows *with* the move. Every order carries its own SL, TP and break-even, and the lot size scales with the EA's capital.

> **Default (Classic preset):** 3 orders, gap 10, step 40, SL 30, TP 200, BE 40/30.

## ⚙️ Key inputs

| Group | What it does |
|---|---|
| **0 Preset** | Custom, Classic, Aggressive (no SL), One by one, Scalper, Mega grid, Long term, Tight hedge, Gold. A preset overrides groups 1, 2 and 4. |
| **1 Grid** | Sides on/off, orders per section, gap, section step, start gap (no-trade zone), hedge follows price, SL, TP, bundle stops, max positions per side |
| **2 Break even** | BE start + lock (lock can be negative), 2nd BE step, trailing stop |
| **3 Lot** | Start lot, lot follows capital, dynamic lot jump, max lot, capital, resize pendings |
| **4 After SL** | Delete pendings after a real stop loss; restart: breakout / next candle / instantly |
| **5 Cycle** | Unit % or money, profit target, loss limit, loss recovery, profit lock, reset on TP, pause after target, close above / below price |
| **6 Protection** | Daily profit target, daily loss limit, kill switch, max spread |
| **7 Time / filter** | Trading window, close at window end, Friday close, MA direction filter |
| **8 Display** | Panel, position, tooltips (hover boxes), next-section lines, colours, alerts |
| **9 Other** | Start paused, magic number, comment, slippage, pip size override |

## 🖥️ Dashboard & chart

Drag the header to move the panel, **X** closes it to a small pill, click the pill to open it again. Hover over any row for an explanation. **PAUSE / RESUME** and **CLOSE ALL** buttons are always at hand.

## 🚀 First steps

1. **Demo account first** — grid trading is high risk.
2. Start lot: **0.01 per 1000** of account money is a sane start (0.01 per 100 is aggressive).
3. Pick a preset or use CUSTOM (default = Classic).
4. Optional: set a cycle profit target and a cycle loss limit, a trading window (e.g. 09:00–19:00), the MA direction filter and a kill switch.

## 📋 Requirements

- **MT5 needs a hedging account** (every order is its own position).
- Any symbol, any timeframe.

## 🛠️ Installation

1. In your terminal open **File → Open Data Folder**.
2. **MT4:** copy `TL Pyramid Grid Pro.ex4` to `MQL4 → Experts`. **MT5:** copy `TL Pyramid Grid Pro.ex5` to `MQL5 → Experts`.
3. Restart or refresh the Navigator and drag the EA onto any chart (the timeframe does not matter).
4. Enable **"AutoTrading"** (MT4) / **"Algo Trading"** (MT5).
5. Optional: enable **"Allow DLL imports"** only if you want the panel's link buttons to open your browser — trading works without it.

## ⚠️ Notes

- No profit promise. Trending markets suit the grid; sideways markets produce series of small stop losses.
- Grid exposure can grow quickly — test every setting on a demo account and with your broker first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
