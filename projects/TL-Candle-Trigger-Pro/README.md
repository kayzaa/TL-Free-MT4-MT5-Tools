<div align="center">

# ⚡ TL Candle Trigger Pro

**The big candle decides the direction, the trigger candle times the entry — a simple price-action EA.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_CandleTriggerPro_screenshot.png" alt="TL Candle Trigger Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Candle Trigger Pro.ex4`](MT4/TL%20Candle%20Trigger%20Pro.ex4) |
| **MT5** | [`TL Candle Trigger Pro.ex5`](MT5/TL%20Candle%20Trigger%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **One clear idea** — the big candle decides which way you may trade, the small candle decides when momentum is strong enough to enter, and your trade limits decide whether the trade is allowed.
- **Three trigger approaches** — fixed points, % of the small candle range, or a multiple of ATR.
- **Every tick re-checked** — no condition "stays" true; if price falls back through the big candle open, the setup is gone.
- **Flexible timeframe pairs** — from M5+M1 up to H4+M15, or custom minutes, built from M1 bars (M2 / M3 / M10 work on MT4 too).
- **Live dashboard** — direction, timing and permission as a stepper, a checklist of every rule and why the EA is waiting.
- **Trigger lab** — MAE / MFE of the EA trades and the best / worst move after every first trigger.

## 🧠 Strategy rules

> **DIRECTION → TIMING → PERMISSION → TRADE**
> BUY rules shown — SELL is the exact mirror.

| Step | Rule |
|---|---|
| **1. DIRECTION** | Bid **above** the open of the running big candle = bullish, only BUY allowed. Bid below the open = bearish, only SELL. Bid exactly at the open = neither. Optional: big candle minimum age (minutes) and minimum movement from its open (points; Bid − open for BUY, open − Bid for SELL). |
| **2. TIMING** | The running small candle reaches the trigger distance from **its own** open in the same direction as the big candle. Optional: small candle minimum age (seconds). |
| **3. PERMISSION** | Checked **after** direction + trigger: max spread, trading hours, max trades per big candle, max trades per day, max open trades, one trade per small candle, broker trading session. |
| **4. TRADE** | A market order is sent only when **all** conditions are true at the same moment. Everything is re-checked on every tick. |

### Trigger approaches

- **A — Fixed points:** simple baseline, e.g. 20 points.
- **B — % of the small candle range:** average of the last N closed small candles (the running candle is still developing).
- **C — × ATR of the small timeframe:** adapts to volatility; start with 0.10 – 0.20.

### Timeframe combinations

Input **"Big + small candle"**: M5+M1, M10+M2, **M15+M3 (default)**, M15+M5, M30+M5, M30+M10, H1+M5, H1+M15, H4+M15 or CUSTOM minutes. The candles are built from M1 bars, so M2 / M3 / M10 work on MT4 too.

## 🎯 Exits

| Input | Options |
|---|---|
| **Stop loss** | Big candle open (= direction reversal), small candle open (+ buffer), × ATR, fixed points or none |
| **Take profit** | R multiple (default 1.5 R), fixed points, × ATR or none |
| **Big candle close** | Close the trade when the big candle ends (default on) |
| **Flip** | Optional: close when Bid crosses back through the big candle open |
| **Break-even** | Optional: stop to entry + X points after +Y points |

## 🖥️ Dashboard & chart

1. **DIRECTION** — big candle open, Bid, movement, age / time left (gold mark = minimum age).
2. **TIMING** — small candle open + move, trigger distance, BUY / SELL trigger levels, progress.
3. **ALL CONDITIONS AT ONCE** — the DIRECTION → TIMING → PERMISSION → TRADE stepper plus a BUY / SELL checklist of every rule and why the EA is waiting.
4. **MAE / MFE + TRIGGER LAB** — MAE / MFE of the EA trades, plus the best / worst move after every first trigger until the big candle ends (live + M1 history).
5. **POSITION** — open trade, stops, P/L, AUTO TRADING on / off, CLOSE ALL.

Drag the header to move it, **X** closes it to a pill, hover any line for an explanation. Link buttons: RoboForex, WhatsApp, YouTube, Forex Factory thread. The dashboard moves out of the way of other trader.lifestyle panels on the same chart.

**On the chart:** gold line = big candle open, cyan line = small candle open, green / red dotted lines = BUY / SELL trigger levels of the running small candle.

## 🔬 How to explore it

Keep the entry logic the same and change **one** thing at a time: first the timeframe combination, then the trigger distance (5 / 10 / 15 / 20 / 25 / 30 / 40 points) or the trigger approach. Watch MAE / MFE and how sensitive the outcome is to spread and slippage. Small trigger distances and tight stops react strongly to your broker's spread.

## 🛠️ Installation

1. In MetaTrader open **File → Open Data Folder**.
2. **MT4:** copy `TL Candle Trigger Pro.ex4` into `MQL4 → Experts`. **MT5:** copy `TL Candle Trigger Pro.ex5` into `MQL5 → Experts`.
3. Refresh the Navigator and drag the EA onto a chart — M1 is recommended to see the levels. In the MT4 Strategy Tester, use the M1 chart.
4. Enable **Algo / Auto Trading**. **"Allow DLL imports"** is only needed for the link buttons.

## ⚠️ Notes

No profit promise — trading involves high risk. Test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
