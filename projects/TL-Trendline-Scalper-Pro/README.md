<div align="center">

# ⚡ TL Trendline Scalper Pro

**swilliam's TMT trendline scalping — auto tangent lines with the used-line rule.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Trendline_Scalper_Pro_XAUUSD_M5_tsp_shot.png" alt="TL Trendline Scalper Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Trendline Scalper Pro.ex4`](MT4/TL%20Trendline%20Scalper%20Pro.ex4) |
| **MT5** | [`TL Trendline Scalper Pro.ex5`](MT5/TL%20Trendline%20Scalper%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **swilliam's TMT system, fully automatic.** Trend – Momentum – Trendline from Forex Factory thread 912456, in one EA.
- **No extra indicators needed** — everything is calculated inside the EA.
- **Auto-drawn trendlines** from the highest / lowest swing, with the used-line rule: a line is never traded twice.
- **Every option from the thread:** sessions, news filter, break-even, 1R + 2R split, ATR stops, choppy-market filter and more.
- **Animated dashboard** with an 8-rule TMT checklist, trendline radar and RSI / MFI gauges.
- **MT4 + MT5.**

## 🧠 Strategy rules (post #1)

| # | Rule | BUY | SELL |
|---|---|---|---|
| 1 | Daily candle (current day) | Green | Red |
| 2 | RSI(8) | Above 50 | Below 50 |
| 3 | MFI(14, tick volume) | Above 50 | Below 50 |
| 4 | Trend | EMA 7 above EMA 20 | EMA 7 below EMA 20 |
| 5 | Pullback into the EMA 7 / 20 zone | Yes | Yes |
| 6 | Trendline from the highest / lowest swing | Drawn automatically (max. 20 bars back, post #1605) | ← same |
| 7 | Break of the line + bar closed | Or intrabar break (post #1597 — input) | ← same |
| 8 | Stop / target | 10–30 pips, swing stop, 1:1 to start (post #1597) | ← same |

**The trendline:** the anchor is the highest swing high (buy) / lowest swing low (sell) of the last 20 bars. The line is fitted along the following highs / lows, so every bar since the swing is on or below / above the line. The first close beyond the line is the signal. A used line is never traded twice — a new swing is needed.

### 🧩 Options from the thread

- Day start hour for the daily candle (broker GMT).
- London / New York / Asia session.
- High-impact news filter (MT5 economic calendar, 30 min before / after).
- Break-even after X pips (swilliam: 7).
- 2 trades with targets 1R + 2R and break-even after target 1 (RiskFighter).
- ATR stops / targets (Profitfusion), S/R swing target, time exit.
- Max. spread, trades per day, cooldown, long / short only.
- Daily profit target (e.g. 5 $ per day, then the EA pauses until the next day).
- **Hard breakout stop:** SL at the broken trendline — out at once when price falls back under the breakout.
- **Choppy-market filter:** skip when the swing stop is closer than X × ATR(14).
- Optional **martingale** after losing trades (×2 per loss, max. 5 steps — high risk, off by default) and **stop + reverse** (after a loss, the opposite trade at once with the martingale lot).

### 🎛️ Defaults = Gold H1 preset (since v1.00 build 06.10.2026)

> All day, target 1:2 (no pip clamp), break-even after 1R (+5 pips locked), pullback may close beyond EMA 20, choppy-market filter 1.5 × ATR, 10 % risk per trade (compounding).

**For the original 10–30 pip M5 scalping rules**, set: session London + NY, target 1:1, pip clamp on, break-even off, pullback hold on, ATR filter 0.

## 🖥️ Dashboard & chart

- **Dashboard:** animated; drag the header, **X** closes it to a pill (click to reopen). TMT checklist with all 8 rules for buy and sell, trendline radar (mini chart with the live line), daily candle (change, range vs ADR, distance from high / low, swaps), RSI + MFI gauges, auto trade (ON/OFF, CLOSE), performance + equity curve.
- **On the chart:** EMA 7 + 20, live trendline (magenta = buy, orange = sell, grey dotted = filters not OK), past breaks with line + arrow, daily open line.
- Tooltips everywhere (can be switched off).

## 🛠️ Installation

1. In your terminal open **File → Open Data Folder**.
2. **MT4:** copy `TL Trendline Scalper Pro.ex4` to `MQL4 → Experts`. **MT5:** copy `TL Trendline Scalper Pro.ex5` to `MQL5 → Experts`.
3. Refresh the Navigator and attach the EA to a chart — the default preset is built for gold H1; the original scalping rules use M1, M5 or M15.
4. Enable **"Allow Algo Trading"**. Enable **"Allow DLL imports"** only for the link buttons.
5. One chart = one magic number.

## 🙏 Credits

**swilliam's** "Trendline Scalping System" — Forex Factory thread 912456 — with options contributed in the thread by **RiskFighter** and **Profitfusion**.

## ⚠️ Notes

- The default preset risks 10 % per trade with compounding — that is aggressive. Lower it for live use.
- Martingale and stop + reverse increase lot size after losses; exposure can grow quickly. Test on demo first.
- The news filter uses the MT5 economic calendar.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
