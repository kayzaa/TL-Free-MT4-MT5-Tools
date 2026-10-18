<div align="center">

# ⚡ TL Bulk SL TP Pro

**Drag ONE line and every open position gets the same stop loss or take profit — without closing anything.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_BulkSLTPPro_screenshot.png" alt="TL Bulk SL TP Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Bulk SL TP Pro.ex5`](MT5/TL%20Bulk%20SL%20TP%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **One line, every position** — drag a BUY SL / BUY TP / SELL SL / SELL TP line and all matching positions get that exact price.
- **Quick actions** — set SL / TP a number of pips from each entry, move to breakeven (with offset), remove SL or TP, close all.
- **UNDO** — restores the SL / TP from before the last bulk change.
- **Smart filters** — this symbol or all symbols, buys and/or sells, all positions / manual only / one magic number.
- **Nothing changes silently** — invalid levels are rejected and counted instead of being half-applied.
- **Management only** — the EA never opens a trade.

## 🧠 How it works

### Drag lines (chart symbol)

BUY SL, BUY TP, SELL SL and SELL TP lines appear as soon as there are buy or sell positions. Drag a line, release it, and every matching position gets that exact price as its stop loss or take profit.

Each line label shows:

- the price
- how many positions sit on the line
- pips from the average entry
- the money result if price reaches the line (swap included, commission not)

With **AUTO APPLY OFF** you move the lines first and then press **APPLY LINES** — until then the label reads `NOT APPLIED`.

Levels on the wrong side of the price, or inside the broker's stops level, are rejected and counted — nothing is half-changed silently.

### Quick actions (chart symbol or all symbols)

| Button | What it does |
|---|---|
| **SET SL / SET TP** | Places SL or TP x pips from each entry (adjust with the − / + buttons) |
| **BREAKEVEN** | Moves stops to the entry price, plus an optional offset |
| **REMOVE SL / REMOVE TP** | Clears the stop loss or take profit |
| **UNDO** | Restores the SL / TP from before the last bulk change |
| **CLOSE ALL** | Closes the filtered positions (asks for confirmation) |

### Filters

- **Symbol:** ONLY &lt;symbol&gt; or ALL SYMBOLS
- **Side:** BUYS + SELLS, BUYS ONLY or SELLS ONLY
- **Input:** all positions, manual positions only, or one magic number

## 🖥️ Dashboard & chart

Click **X** to shrink the dashboard to a small pill, drag the header to move it. Settings are kept per chart.

## 🛠️ Installation

1. In MT5 choose **File → Open Data Folder → MQL5 → Experts** and copy `TL Bulk SL TP Pro.ex5` there.
2. Refresh the Navigator and drag the EA onto a chart of the symbol you trade.
3. Enable **Algo Trading** — the EA needs it to modify SL / TP.
4. Tick **Allow DLL imports** only if you want the link buttons to work.

## ⚠️ Notes

- The EA modifies stops and targets of existing positions and can close them on request (CLOSE ALL) — it never opens a trade.
- Try it on a demo account first so you know exactly which positions the filters include.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
