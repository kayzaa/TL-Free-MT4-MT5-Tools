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

## Overview

swilliam's "Trendline Scalping System" (Forex Factory thread 912456, TMT = Trend - Momentum - Trendline) as one fully automatic EA. No extra indicators needed - everything is calculated inside the EA.

## Rules (post #1)                                   BUY                         SELL

1 Daily candle (current day)                     green                       red 2 RSI(8)                                         above 50                    below 50 3 MFI(14, tick volume)                           above 50                    below 50 4 Trend                                          EMA 7 above EMA 20          EMA 7 below EMA 20 5 Pullback into the EMA 7 / 20 zone              yes                         yes 6 Trendline from the highest / lowest swing      drawn automatically (max. 20 bars back, post #1605) 7 Break of the line + bar closed                 (or intrabar break, post #1597 - input) 8 Stop / target                                  10 - 30 pips, swing stop, 1:1 to start (post #1597)

The trendline: anchor = highest swing high (buy) / lowest swing low (sell) of the last 20 bars, the line is fitted along the following highs / lows (every bar since the swing is on or below / above the line). The first close beyond the line is the signal. A used line is never traded twice - a new swing is needed.

Options from the thread: day start hour for the daily candle (broker GMT), London / New York / Asia session, high-impact news filter (MT5 economic calendar, 30 min before / after), break-even after X pips (swilliam: 7), 2 trades with targets 1R + 2R and break-even after target 1 (RiskFighter), ATR stops / targets (Profitfusion), S/R swing target, time exit, max. spread, trades per day, cooldown, long / short only, daily profit target (e.g. 5 $ per day, then the EA pauses until the next day), optional martingale after losing trades (x2 per loss, max. 5 steps - HIGH RISK, off by default), hard breakout stop (SL at the broken trendline: out at once when price falls back under the breakout), stop + reverse (after a loss the opposite trade at once with the martingale lot), choppy-market filter (skip when the swing stop is closer than X x ATR(14) - best study value 1.5 on gold H1).

DASHBOARD: animated, drag the header, X closes it to a pill (click to reopen). TMT checklist with all 8 rules for buy + sell, trendline radar (mini chart with the live line), daily candle (change, range vs ADR, distance from high / low, swaps), RSI + MFI gauges, auto trade (ON/OFF, CLOSE), performance + equity curve. On the chart: EMA 7 + 20, live trendline (magenta = buy, orange = sell, grey dotted = filters not OK), past breaks with line + arrow, daily open line. Tooltips everywhere (can be switched off).

## Defaults (since v1.00 build 06.10.2026) = Gold H1 Preset: all day, target 1:2 (no pip clamp), break-even after 1R

(+5 pips locked), pullback may close beyond EMA 20, choppy-market filter 1.5 x ATR, 10 % risk per trade (compounding). For the original 10-30 pip M5 scalping rules set: session London+NY, target 1:1, pip clamp on, break-even off, pullback hold on, ATR filter 0.

INSTALL: MT5 -> MQL5\Experts, MT4 -> MQL4\Experts. Attach to M1, M5 or M15. Enable "Allow Algo Trading" and "Allow DLL imports" (only used for the link buttons). One chart = one magic number.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
