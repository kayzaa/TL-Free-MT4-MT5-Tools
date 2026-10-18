<div align="center">

# ⚡ TL Triple Confluence Gold M5 Lab

**Trend-pullback analysis for gold M5: EMA 25/75/140 structure, ATR-based stops and clear signal pills. Indicator only.**

![version](https://img.shields.io/badge/version-v1.20-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/Screenshot_MT5.png" alt="TL Triple Confluence Gold M5 Lab" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Triple Confluence Gold M5 Lab.ex4`](MT4/TL%20Triple%20Confluence%20Gold%20M5%20Lab.ex4) |
| **MT5** | [`TL Triple Confluence Gold M5 Lab.ex5`](MT5/TL%20Triple%20Confluence%20Gold%20M5%20Lab.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Built for gold M5** — trend-pullback analysis on XAUUSD M5 with an EMA 25 / 75 / 140 structure.
- **Strict, mechanical trend gates** — EMA order, slope, ribbon width, signed efficiency and RSI, rechecked on every closed bar.
- **Pullback + stochastic trigger** — an EMA touch followed by a confirmation close and a K / D cross.
- **ATR-based swing stops, 2R target and a time exit** — every signal gets a complete, fixed plan.
- **Browse real historical signals** — PREVIOUS / NEXT jumps through the chart with TP, SL, TIME EXIT and more on each pill.
- **Indicator only** — no orders, no DLL, no account lock, no expiry.

## 💡 Purpose

Trend-pullback analysis for **Gold M5**. You decide whether a setup fits your own plan — there is no requirement to trade every signal, and the indicator places no orders. The concept comes from a Trader DNA video; the precise mechanical filters and exits below are our implementation additions.

## 🧠 Strategy rules

### Trend gates (rechecked on every close)

| Gate | BUY | SELL |
|---|---|---|
| EMA order | EMA25 > EMA75 > EMA140 | EMA25 < EMA75 < EMA140 |
| Slope | Middle and slow EMA each rise ≥ 0.08 ATR over 8 closed bars (fast EMA may flatten during the pullback) | Mirror |
| Ribbon width | Fast / slow separation ≥ 0.50 ATR | Same |
| Signed efficiency (30 bars) | ≥ 0.10 in the EMA direction | Same |
| RSI(75) | > 51 | < 49 |
| Price | Close beyond the slow EMA on the trend side | Mirror |

- Signed efficiency = `direction × (close − close[30]) / sum(abs(close changes), 30 bars)`.
- Two consecutive qualifying trend bars are required. There is no retained trend permission — any failed gate clears the pending EMA touch.

### Pullback & trigger

- An EMA must be touched within **8 bars**, with a **0.10 ATR** tolerance. The deepest touched EMA is tracked.
- **Confirmation:** a close beyond that EMA and beyond the prior close in the trend direction, with a matching bullish / bearish body and a **stochastic(14, 3, 3) K / D cross**.
- No requirement to close beyond the fast EMA when a deeper EMA was tested.
- **Classes:** A (extreme) and B (standard) are both enabled. **A** means both lines ≤ 20 for BUY or ≥ 80 for SELL on the cross bar or the preceding bar. Both classes target 2R.
- At least **6 bars** between decisions; the touch is consumed after an entry decision.

### Stop, target & time exit

- **BUY stop** = lowest low of the last 5 completed candles − 0.25 ATR. **SELL stop** = highest high of the last 5 candles + 0.25 ATR.
- Stop distance from the signal **close** must be at least 1 ATR (widened if needed); the setup is skipped if it exceeds 3 ATR. No future swing pivots are used.
- **Entry** at the next bar's open; the stop stays fixed. Next-open risk can differ from the close-based ATR bounds, especially at gaps — invalid next-open risk is marked **GAP SKIP**.
- **TP** = 2 × the initial entry-to-stop price risk. No trailing, break-even or partials.
- **TIME EXIT:** if neither SL nor TP is hit first, the signal exits at the close of the 36th completed holding bar (the entry bar counts as 1) — 180 trading minutes on M5, longer across market closures. A time exit can win or lose.

## 📊 Signal outcomes & cost model

The indicator tracks each historical signal as an independent, hypothetical OHLC simulation — these are **not** account returns or equity, and not guaranteed executable fills.

- **Spread:** the recorded spread of each historical bar is used by default, with `InpSpreadPoints = 30` as a fallback when missing (symbol points are not dollars). BUY entries add the entry bar's spread; SELL exits add each exit bar's spread. Bar spread does not reconstruct tick-by-tick ask quotes.
- **Commission:** an assumed round-turn commission of 7 account-currency units per lot — set your own costs.
- **Price-R** includes spread and excludes commission. **Money** deducts commission and uses the CURRENT tick value / size and the selected lots (default 0.10). No historical FX, swap or slippage reconstruction.
- If SL and TP both occur in one bar without an opening resolution, the signal shows **AMBIGUOUS** and is excluded from the settled totals. Unresolved signals show **OPEN** and are excluded from resolved totals.

## 🖥️ Dashboard & chart

- Large Canvas dashboard: drag the header, **X** collapses it, the pill reopens it, hover for explanations.
- **PREVIOUS / NEXT** selects a real historical signal. Selected risk / target guides and BUY / SELL pills show TP, SL, TIME EXIT, OPEN, AMBIGUOUS or GAP SKIP plus R / points.
- Current trend permission always refers to the latest completed bar, even while browsing history. Where pills would collide, small dots may be shown instead.
- **CSV export** to the local MQL Files folder overwrites the loaded window (default 5000 bars).
- Link buttons show their URLs — no DLL or browser automation required. Alerts / push are off by default.
- The chart theme is restored when the indicator is removed.

**Buffers**

| Buffer | Content |
|---|---|
| 0 / 1 / 2 | EMAs |
| 3 / 4 | BUY / SELL next-open entry |
| 5 | SL |
| 6 | TP |
| 7 | Outcome status: 0 OPEN, 1 TP, 2 SL, 3 AMBIGUOUS, 4 GAP SKIP, 5 TIME EXIT |

The outcome is retrospective and never an entry filter; forming candles are excluded from completed outcomes.

## 🛠️ Installation

1. Copy the file for your platform:
   - **MT5:** `TL Triple Confluence Gold M5 Lab.ex5` → **File → Open Data Folder → MQL5 → Indicators** (e.g. a `TripleConfluence` subfolder)
   - **MT4:** `TL Triple Confluence Gold M5 Lab.ex4` → **File → Open Data Folder → MQL4 → Indicators**
2. Refresh the Navigator and attach **Gold M5 Lab** to an **XAUUSD M5** chart, then use **Inputs → Reset**.
3. The default instance ID **G** avoids colliding with the older indicator's ID **A**. Prefer one theme-owning indicator per chart.

## ⚠️ Notes

- The outcome labels are hypothetical, overlapping signal simulations — not trading results.
- The screenshot illustrates the chart and individual signal labels only.

## 🙏 Credits

- Concept (EMA / RSI / stochastic): [Trader DNA on YouTube](https://www.youtube.com/watch?v=wf6s7HHUP_8). This edition adds the explicit trend conditions, swing stops, target and time-exit rules.
- [trader.lifestyle](https://trader.lifestyle)

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
