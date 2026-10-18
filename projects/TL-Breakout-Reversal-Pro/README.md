<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Breakout Reversal Pro

**"All you need to know about trading" as an EA — small losses, running winners, position size = risk / stop.**

![version](https://img.shields.io/badge/version-v1.10-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Breakout_Reversal_Pro_XAUUSD_H1_brp_shot.png" alt="TL Breakout Reversal Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Breakout Reversal Pro.ex4`](MT4/TL%20Breakout%20Reversal%20Pro.ex4) |
| **MT5** | [`TL Breakout Reversal Pro.ex5`](MT5/TL%20Breakout%20Reversal%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

"All you need to know about trading" - as an EA. Nothing else is in it.

- Price either goes up or down. No one knows what will happen next.
- Keep losses small and let winners run.
- POSITION SIZE = RISK / STOP LOSS.
- You control the size of your loss (skill), not the size of your win (luck).
- Know when to pick up your chips and cash them in.
- Expectancy = P(win) x average win - P(loss) x average loss. The only part you control is the average loss.

## Price Action (price action rules quoted from H. Rearden on Forex Factory)

- Price breaks out of the high, the low or both of the previous bar
- Price does not break out of the previous bar
- Price closes above a level (line) or not It happens on every time frame.

## Entering A Trade - your Only 3 options (inputs or dashboard buttons)

- WAIT      - no trade (open trades are still managed)
- BREAKOUT  - price breaks the previous high -> BUY, the previous low -> SELL stop = the other end of the previous bar
- REVERSAL  - price makes a new high and comes back below the previous high -> SELL (new low, back above the previous low -> BUY) stop = beyond the new extreme

## Timeframe

Default: D1 = the previous DAY's high / low (works on any chart time frame, the lines are drawn on lower charts too). Any time frame can be set - but the smaller the bars, the more of every stop is eaten by the spread (see the cost guard below).

## Trigger

- **BREAK OF THE BAR** — - the trade opens the moment price breaks the line (tick by tick) CLOSE BEYOND LINE   - decided at the bar close: closed beyond the line = breakout, broke out but closed back inside = reversal One trade at a time, max. one entry per bar. A CLOSE signal that falls into a session break (e.g. gold at the day change) is executed at the first tick after the market opens.

## Position Size = Risk / Stop Loss

Risk per trade in % of balance or a fixed amount. The lot size is calculated from the stop distance: wide stop = small size, tight stop = bigger size - the loss stays the same. If even the minimum lot would risk more than twice the allowed amount, the trade is skipped.

## Cost Guard (keep losses small)

The spread is part of every loss. If the spread costs more than 10 % of the stop (input, 0 = off), the trade is skipped - a stop that is mostly spread is not a trade. The dashboard shows the spread cost of the next BUY / SELL stop live.

## Let Winners Run - Cash In Your Chips

No fixed target by default. At every bar close the stop trails behind the lowest low (BUY) / highest high (SELL) of the last 3 bars (input), starting after +1R. Optional take profit as an R multiple. CLOSE ALL button in the dashboard.

## Chart

Lines: previous bar high / low. Marks on every bar: green / red arrow = broke the previous high / low and closed beyond it (breakout)
- **orange arrow** — = broke out but closed back inside (reversal) grey dot          = inside bar, no breakout

## Dashboard

Price action of the forming bar, the 3 option buttons + trigger, next BUY / SELL line, live position size (risk / stop = lots), expectancy of the closed trades, position, CLOSE ALL. Drag the header to move it, X closes it to a pill, click the pill to reopen.

## Install

- **MT5: copy MT5/Experts/TL Breakout Reversal Pro.ex5 to** — File > Open Data Folder > MQL5/Experts MT4: copy MT4/Experts/TL Breakout Reversal Pro.ex4 to  File > Open Data Folder > MQL4/Experts Refresh the Navigator, drag the EA onto a chart, allow Algo Trading. The link buttons need "Allow DLL imports". One magic number per chart.

## Risk Warning

Trading involves a high risk of loss. Test on a demo account first. No profit is promised - no one knows what will happen next.

trader.lifestyle  -  <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
