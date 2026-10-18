<div align="center">

# ⚡ TL WaveTrend Pro

**WaveTrend oscillator (LazyBear formula) with RHO-style rules and trailing — indicator + EA.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_WaveTrendPro_screenshot.png" alt="TL WaveTrend Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL WaveTrend Pro EA.ex4`](MT4/TL%20WaveTrend%20Pro%20EA.ex4) |
| **MT4** | [`TL WaveTrend Pro.ex4`](MT4/TL%20WaveTrend%20Pro.ex4) |
| **MT5** | [`TL WaveTrend Pro EA.ex5`](MT5/TL%20WaveTrend%20Pro%20EA.ex5) |
| **MT5** | [`TL WaveTrend Pro.ex5`](MT5/TL%20WaveTrend%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

with the conditions of TL RHO Pro: closed-bar signals, whipsaw filter, SL / TP1 / TP2 / break-even and a trailing stop - as an indicator AND as an EA that trades exactly the same signals.

## Files

- MT5\Indicators\TL WaveTrend Pro.ex5      MT5\Experts\TL WaveTrend Pro EA.ex5   (the EA has the indicator built in)
- MT4\Indicators\TL WaveTrend Pro.ex4      MT4\Experts\TL WaveTrend Pro EA.ex4

## Wavetrend

- ap = HLC/3, esa = EMA(ap, 10), d = EMA(|ap - esa|, 10), ci = (ap - esa) / (0.015 x d)
- WT1 = EMA(ci, 21), WT2 = SMA(WT1, 4) (signal line), levels +60 / +53 / -53 / -60
- Signal: WT1 crosses WT2 (classic) - or WT1 crosses zero, or WT2 crosses zero
- Optional OB/OS filter: BUY only after WT1 was below -X, SELL only after it was above +X (last 10 bars)

## The RHO Pro Conditions

- No repaint: signals are set when the bar closes and never move again
- Whipsaw filter: the cross must hold 3 closed bars, leave a noise zone of 40 % of the average distance, and there are at least 10 bars between a BUY and a SELL (1 / 0 / 1 = off)
- Min. span: only set-ups with at least 26 pips from the stop loss to TP2 (0 = off). The value is in pips - adapt it to the timeframe and the market (gold and small timeframes need other values)

## Trade Levels

- Entry = close of the signal bar
- Stop loss behind the swing of the last 5 bars + 0.2 ATR (or an ATR multiple), at least 0.5 ATR
- TP1 = 1R: 50 % closed, stop to break-even. TP2 = 2R
- Break-even also after 5 candles in a row completely beyond the entry
- NEW - trailing stop: from +0.5R in profit (also BEFORE TP1) the stop follows the best price at 0.5R distance. It moves with the closed candles only and never goes backwards. Inputs: on / off, start R, distance R.
- The next signal closes the trade. Stop and target inside one bar = stop first (conservative)

## On The Chart

BUY / SELL pills, position zones, stop line as a step line (red = original stop, gold = break-even, cyan = trailing), price tags for TP2 / TP1 / SL / BE / TRAIL / ENTRY, result badges (TP2, TP1+BE, TRAIL, TP1+TRAIL, BE, -1R), cyber WaveTrend window with OB / OS bands, dashboard (drag the header, X = small pill, hover = help).

## The EA

- Trades every signal of the indicator: market order at the next tick, SL and TP2 at the broker
- TP1 partial close + break-even, break-even after N clean candles, trailing stop - same rules as the indicator
- Risk % of the balance or fixed lots, max. lots, max. spread, BUY / SELL / both, magic number
- The next signal closes the open trade (input). No orders while the market is closed - a signal waits for the open
- Dashboard: WaveTrend, signal, position (live P/L, stop state), AUTO TRADING on / off button, CLOSE ALL (2 clicks)
- MT5: loads the WaveTrend window by itself. MT4: drop the indicator on the same chart if you want the window (set "Show the dashboard" = false there)

## Buffers (indicator, for your own EAs via iCustom)

0 WT1, 1 WT2, 2 WT1-WT2 >= 0, 3 WT1-WT2 < 0, 4 BUY marker, 5 SELL marker, 6 signal (+1 / -1), 7 trade stop (BE / trailing), 8 TP1, 9 TP2, 10 trade state (+-1 open, +-2 after TP1, +-3 BE before TP1, +-4 trailing),

## Install

- MT5: File -> Open Data Folder -> MQL5\Indicators (indicator) and MQL5\Experts (EA)
- MT4: File -> Open Data Folder -> MQL4\Indicators and MQL4\Experts Refresh the Navigator, drag the indicator / EA onto a chart. EA: Algo Trading / AutoTrading on.
- The dashboard buttons open links and need "Allow DLL imports" (Common tab). Everything else works without it.
- The chart colours change to the dashboard style and come back when you remove the tool.

- The dashboard statistics are calculated on your chart without spread and commission - a quick overview, not a backtest. Test the EA on a demo account first. Trading involves high risk.
- trader.lifestyle - Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
