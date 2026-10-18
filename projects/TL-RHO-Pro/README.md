<div align="center">

# ⚡ TL RHO Pro

**Rebuild of the "RHO" dual-MACD indicator with SwingMan's extra options — plus EA.**

![version](https://img.shields.io/badge/version-v7.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_RHO_Pro_screenshot.png" alt="TL RHO Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL RHO Pro.ex4`](MT4/TL%20RHO%20Pro.ex4) |
| **MT5** | [`TL RHO Pro.ex5`](MT5/TL%20RHO%20Pro.ex5) |

> Compiled build only — source code is not published.

## What It Shows

- Fast MACD = MA 5 - MA 10 and slow MACD = MA 11 - MA 13, both in pips (EMA of the close by default)
- BUY / SELL signal when the fast line crosses zero (or: fast line x slow line, slow line x zero)
- BUY / SELL pills on the price chart, cyber-style indicator window, dashboard
- Trade levels for every signal: entry, stop loss, TP1, TP2, break-even

## No Repaint

Signals are set when the bar closes and never move again (the old live-bar modes are still available).

## Whipsaw Filter (new - removes the quick BUY/SELL flip-flops)

- Hold: the cross must hold 3 closed bars
- Noise zone: the line must leave a zone of 40 % of its average distance
- Gap: at least 10 bars between a BUY and a SELL
All three filters can be switched off (1 / 0 / 1) to get the original RHO signals.

## Min. Span Filter (new)

Only signals whose trade span stop loss -> TP2 is at least 26 pips are shown (input "Min. span SL -> TP2", 0 = off). Smaller set-ups are skipped completely (no pill, no trade, no alert, buffer 7 = 0). The value is in pips, so adapt it to the timeframe and the market (26 pips fits EURUSD M15 / H1; on M5 or on gold use other values).

## Trade Levels

- Entry = close of the signal bar
- Stop loss behind the swing of the last 5 bars + 0.2 ATR (or an ATR multiple), at least 0.5 ATR
- TP1 = 1R (50 % closed), TP2 = 2R
- Break-even: the stop goes to the entry after TP1, and also after 5 candles in a row that stay completely beyond the entry (BUY: low above the entry, SELL: high below the entry)
- The next signal closes the trade. Stop and target inside one bar = stop first (conservative).
- Alerts for TP1 / break-even / TP2 / stop (popup, sound, push, e-mail)
your chart. Win = closed with profit in R (TP2, TP1 + break-even, or closed in profit by the next signal); a loss resets the streak, a 0R break-even is neutral. That is a quick quality check without spread or commission - not a backtest and not a promise of profit.

## Buffers (for EAs via iCustom)

0 fast MACD, 1 slow MACD >= 0, 2 slow MACD < 0, 3 fast line, 4 slow line, 5 BUY marker, 6 SELL marker, 7 signal (+1 buy / -1 sell), 8 trade stop (break-even after the move), 9 TP1, 10 TP2, 11 trade state (+-1 open, +-2 after TP1, +-3 stop at break-even before TP1), 12 win streak (closed trades), 13 net result in R of the statistics window (newest bar)

## Install

- MT5: copy "TL RHO Pro.ex5" to  File -> Open Data Folder -> MQL5\Indicators
- MT4: copy "TL RHO Pro.ex4" to  File -> Open Data Folder -> MQL4\Indicators Restart the terminal (or refresh the Navigator) and drag the indicator onto a chart.
- The buttons in the dashboard open links and need "Allow DLL imports" (indicator properties -> Common).
- The chart colours are set to the dashboard style and restored when you remove the indicator (input "Chart in the dashboard style" = false keeps your colours).

- Trading involves high risk. This indicator is a tool, not financial advice.
- trader.lifestyle - Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
