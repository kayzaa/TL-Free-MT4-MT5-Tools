<div align="center">

# ⚡ TL Weekly Pivot Pro

**Davit's weekly Fibonacci pivots as an EA — 38 / 61 / 78 ladder, PP target and basket stop.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_WeeklyPivotPro_post.png" alt="TL Weekly Pivot Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Weekly Pivot Pro.ex4`](MT4/TL%20Weekly%20Pivot%20Pro.ex4) |
| **MT5** | [`TL Weekly Pivot Pro.ex5`](MT5/TL%20Weekly%20Pivot%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Davit's weekly Fibonacci pivots** as a full EA for MT4 and MT5 — same levels as his pivot indicator, from the broker weekly candle.
- **Ladder entries** — sell at R38 / R61 / R78, buy at S38 / S61 / S78, each stage with its own switch and lot multiplier.
- **Pivot as target** — take profit at the weekly PP, with a hard stop beyond R138 / S138 and a trend exit at R100 / S100.
- **Basket stop** — close everything at a money or % loss, per symbol, per magic number or for the whole account.
- **Range / trend filter + multi-pair scanner** from completed weekly candles.
- **High-impact news filter** (Forex Factory feed or MT5 calendar).

## 🧠 Strategy rules

### The levels (broker weekly candle)

- **PP** = (High + Low + Close) / 3 of last week.
- **R / S** = PP ± 0.382 / 0.618 / 0.786 / 1.0 / 1.382 / 1.618 / 2.0 × last week's range.
- Pivot levels stay fixed for the whole week.
- If your pivots differ from Davit's chart, set **Week candle** = *Shifted week* + hour offset.

### Entries (ladder / position building)

| Side | Ladder stages |
|---|---|
| SELL | R38, R61, R78 |
| BUY | S38, S61, S78 |

- Each stage on / off, with its own lot multiplier.
- **Confirmation** (default = mizi123's rule): a closed H1 candle ends in the level zone → that stage is traded.
- Other confirmation modes: **Touch** (enter at the level) · **Rejection candle** · **TDI cross** (Davit, RSI 13 / 2 / 7).
- **Zone tolerance** (default 10 pips): pivots are zones, so the level counts N pips early.
- One ladder per side and week (option).

### Exits

- **Take profit** = the weekly pivot (or one level back towards the pivot).
- **Hard stop** per order beyond R138 / S138 (+5 pips) — or R100 / R161 / off.
- **Trend exit:** an H1 candle closes beyond R100 / S100 → that side is closed (Davit: *"smash 100 = trend"*).
- Optional half-way break-even / partial close.
- Friday close at 21:00 server time.

### Basket stop (mizi123's request)

- Close everything when the open loss reaches **X money** or **X % of the balance** (swap + commission included).
- **Scope:** this symbol · all symbols of this magic number · whole account (closes this EA's orders).
- **Default:** closes the orders and blocks new entries until next week.

### Range / trend filter + scanner (mizi123's request)

Three votes per pair and week, from the completed weekly candles:

1. Weekly ADX (Wilder 14) ≥ 25
2. ≥ 2 of the last 4 weeks traded beyond their own R100 / S100
3. Efficiency of the last 4 weekly closes ≥ 0.6 (net move / path)

**0 votes** = RANGING · **1** = MIXED · **2–3** = TRENDING.

- **Filter:** skip TRENDING (default), only RANGING, with the trend, or off.
- **Live:** price beyond R100 / S100 this week → no new counter-trend trades.
- **Scanner:** shows every pair of Davit's list — regime, ADX, zone touched this week (e.g. "touched R61"), distance to PP. Click a pair to open it.

### News filter

- No new entries 30 min before / after high-impact news (Forex Factory feed or MT5 calendar).

## 🛠️ Installation

1. Open `File → Open Data Folder`.
   - **MT4:** copy `MT4/TL Weekly Pivot Pro.ex4` into `MQL4 → Experts`.
   - **MT5:** copy `MT5/TL Weekly Pivot Pro.ex5` into `MQL5 → Experts`.
2. Refresh the Navigator. Attach the EA to **one chart per pair** you want to trade (M15 or H1 chart; any timeframe works).
3. Enable **Allow algo trading**.
4. For the Forex Factory news feed (and on MT4): add `https://nfs.faireconomy.media` under `Tools → Options → Expert Advisors → Allow WebRequest`.
5. Optional: enable **Allow DLL imports** — only used by the link buttons.

## 🙏 Credits

- Strategy: **Davit's** Forex Factory thread [Pivot Trading](https://www.forexfactory.com/thread/588764-pivot-trading).
- Confirmation rule, basket stop and range / trend filter requested by **mizi123**.

## ⚠️ Notes

- This is a **counter-trend system that adds to losing positions** (ladder stages). Exposure grows with each stage — use the hard stop and basket stop, and test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
