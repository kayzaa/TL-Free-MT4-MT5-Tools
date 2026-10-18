<div align="center">

# ⚡ TL Recovery Grid Quant

**Recovery-grid EA with daily equity trail, loss-pause guards and a full quant panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Recovery_Grid_Quant_view.png" alt="TL Recovery Grid Quant" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Recovery Grid Quant.ex5`](MT5/TL%20Recovery%20Grid%20Quant.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Grid & recovery basket EA for XAUUSD M3** — an independent rebuild of the system K2M RapidSync describes on Forex Factory.
- **Two-timeframe MACD score** — MACD 12/26/9 and 5/9/4 on M3 and M10, scored −10 … +10.
- **Adaptive grid** — ATR-based gaps that widen for deeper levels and hot markets, with a fixed lot ladder and level cap.
- **Realized + Floating basket logic** — every profitable position is trailed with a real stop; the basket closes on R + F targets.
- **Loss-pattern guards** — breakout exit, time window, trend, impulse, basket stop and time guards, all switchable.
- **Quant panel** — entry guard status, grid engine, basket R+F gauge, daily equity trail and guard status.

## 🧠 Strategy rules

> This is my own rebuild from the public description, the panel screenshots and a second-by-second read of the author's silent video. The original is closed source — this is **not** his code.

| Part | Rule |
|---|---|
| **Signal** | MACD 12/26/9 and MACD 5/9/4 on M3 and M10 (5 sub-signals per timeframe, score −10 … +10). Score >= 4 with M3 agreeing = **BUY basket**, <= −4 = **SELL basket** |
| **Entry guard — EDGE** | No new basket while price sits in the top / bottom 25 % of the H1 candle |
| **Entry guard — RES HOLD** | Max 4 baskets in a row in one direction, 3–5 s pause after a basket |
| **Grid gap** | ATR(M1, 14) × 0.50, wider for deeper levels and in hot markets (G PROTECT ×1.2 / ×1.35 / ×1.5), never below 3.30 $ + spread. From level 5 the gap grows ×1.6 per level (auto grid), max gap 40 $ |
| **Lot ladder** | 0.02, 0.02, 0.03, 0.03, 0.03, 0.04 … (as in the video), max 8 levels |
| **Profit trailing** | Every position in profit is trailed with a real stop loss (start 1.20 $, gap 0.50 $); that profit counts as **Realized (R)** for the basket |
| **Basket close** | On R + Floating: **ETC** at R+F >= +20 · **RFC trail** arms at +10, closes at peak − 1 |
| **Daily equity trail** | After +500 for the day a lock follows the peak (peak − 50) |

### Extra guards (not in the original)

Grid baskets tend to close small and often, but the rare losing basket can be very large. The pattern these guards target: a quiet range that **breaks out against the basket** in its first one to two hours.

| Guard | What it does |
|---|---|
| **BREAKOUT EXIT** | In the first 120 min: a directed move of >= 8 $ against the first entry (efficiency >= 0.25) → close the basket small, and no new basket against the breakout for 60 min |
| **TIME WINDOW** | New baskets only 12:00–16:00 server time |
| **TREND GUARD** | No basket against a strong H1 trend (ADX >= 28 + EMA50 slope) |
| **IMPULSE GUARD** | No new grid level while ATR(14) / ATR(120) on M1 >= 2.2 |
| **BASKET STOP** | Hard close at a floating loss of 6 % of balance + 4 h cooldown |
| **TIME GUARD** | No new basket in the first 2 hours of the week or on Friday after 19:00 |

All guards can be switched off to run the "original style" logic.

## 🖥️ Dashboard & chart

- **Panel blocks:** ENTRY GUARD STATUS · GRID ENGINE (final G, lot ladder) · BASKET R+F (ETC / RFC gauge) · DAILY EQUITY TRAIL · LOSS-PATTERN GUARDS · PERFORMANCE
- Hover any block for help.
- **Chart lines:** ETC target, RFC arm / lock, next grid level, day range and extension.

## 📋 Requirements

- A **hedging** account (several positions per symbol) — netting is not supported.
- Defaults are for gold with 2-digit prices; gaps and trailing are in price ($).
- Reference capital in the original thread: 30,000 USD for a 0.01–0.02 start lot.

## 🛠️ Installation

1. In MT5 choose **File → Open Data Folder → MQL5 → Experts** and copy `TL Recovery Grid Quant.ex5` there.
2. Refresh the Navigator and drag the EA onto an **XAUUSD M3** chart.
3. Enable **Algo Trading**.
4. Tick **Allow DLL imports** only if you want the 4 link buttons on the panel to work.

## 🙏 Credits

- Original concept: **K2M RapidSync** — Forex Factory thread "MT5 Grid and Recovery EA" (thread 1408891) and his tester video.

## ⚠️ Notes

- **This is a grid.** Exposure grows with every level, and it can lose a lot of money in a long one-way market — even with the guards switched on.
- The guards are meant to limit the worst baskets; they do not make the entry signal (my MACD approximation) predictive. Treat this EA as a study tool and framework, not a money machine.
- Test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
