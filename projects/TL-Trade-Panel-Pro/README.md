<div align="center">

# ⚡ TL Trade Panel Pro

**One-click order panel: risk-based lots, SL / TP lines, pending orders and partial closes.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Trade_Panel_Pro_XAUUSD_tlv_8_final.png" alt="TL Trade Panel Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Trade Panel Pro.ex4`](MT4/TL%20Trade%20Panel%20Pro.ex4) |
| **MT5** | [`TL Trade Panel Pro.ex5`](MT5/TL%20Trade%20Panel%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **One-click BUY / SELL** with automatic SL and TP.
- **Risk-based lot sizing** — fixed lot, risk % of balance or equity, or a fixed money risk, always rounded down.
- **Drag-and-drop LINES mode** — move ENTRY / SL / TP lines on the chart and the lot follows the SL.
- **Pending orders in a click** — buy / sell limit and stop, with optional expiry.
- **Full position manager** — partial close, break-even, reverse, close buys / sells / profit / loss, plus auto rules.
- **Works everywhere** — hedging, netting and ECN accounts on MT4 and MT5.

## 🎫 Order ticket

- One-click **BUY / SELL** at market with automatic SL and TP.
- **Lot size modes:** FIXED LOT, RISK % of BALANCE, RISK % of EQUITY, RISK fixed MONEY. Risk modes calculate the lot from the stop-loss distance, so the money lost at the SL = your risk.
- Lots are always rounded **down** to the broker lot step — the risk never grows. If the risk is too small for the minimum lot, the order is refused (an input lets you trade the minimum lot anyway).
- **Stop loss** in pips, **take profit** in pips or as an R:R multiple (2 = 1:2). 0 = none.
- **Live preview:** lot, margin, money at risk (and % of balance), reward and R:R.
- **LINES mode:** ENTRY / SL / TP lines on the chart. Drag them and the lot is calculated from the SL line. Drag the ENTRY line and SL / TP move with it. **FLIP** mirrors long ↔ short, **RESET** puts the lines back at the price.
- Every value can be typed (click the box, type, Enter) or changed with − / +.

## ⏳ Pending orders

- Single-click **BUY LIMIT, SELL LIMIT, BUY STOP, SELL STOP**.
- Entry = price ± distance in pips, or the ENTRY line in lines mode.
- Wrong side is refused with a message (e.g. a buy limit above the price).
- Optional expiry in hours (GTC if the broker has no expiry). **DELETE ALL** pending orders.

## 🧰 Position manager

- **Buttons:** CLOSE 50 % (any %), BREAKEVEN, REVERSE, CLOSE BUYS, CLOSE SELLS, CLOSE ALL, CLOSE PROFIT, CLOSE LOSS, DEL PENDING.
- **SCOPE:** this symbol or ALL symbols. **TRADES:** all trades (manual + other EAs) or only this panel's.
- **Auto rules (this symbol):** break-even at X pips (+ lock pips), partial close at X pips (once per trade), trailing stop (start / distance / step), basket close at +money / −money.
- Close / reverse buttons use a 2-click confirmation (input); market orders are one click.
- Works on hedging and netting accounts and ECN accounts (MT4: stops are set after the fill).

## 🖥️ Dashboard & chart

- **Exposure view:** buys / sells, floating P/L and pips, money at SL / TP, pending orders, closed P/L today, balance, equity, margin, free margin, margin level and the last action.
- Animated quant panel: **X** closes it to a pill, click the pill to reopen, drag the header to move it.
- Settings, position and lines are kept per chart (also across timeframe changes). Tooltips can be switched off.
- Several trader.lifestyle panels on one chart never cover each other: the new one moves next to the old one; if the chart has no room it folds to its pill. The panel you work with stays open.

## 🛠️ Installation

1. Copy the file for your platform:
   - **MT5:** `TL Trade Panel Pro.ex5` → **File → Open Data Folder → MQL5 → Experts**
   - **MT4:** `TL Trade Panel Pro.ex4` → **File → Open Data Folder → MQL4 → Experts**
2. Refresh the Navigator and drag the EA onto a chart.
3. Tick **"Allow Algo Trading"** (MT4: **"Allow live trading"**) and switch on **AutoTrading / Algo Trading**.
4. **"Allow DLL imports"** is only needed for the link buttons.

## ⚠️ Notes

- Auto rules (break-even, partial close, trailing, basket close) act on your positions automatically once enabled — check the settings on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
