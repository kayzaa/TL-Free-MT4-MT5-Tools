<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Hurst Envelope Pro

**7iv3's Hurst cycle method: centred-MA envelopes, Murrey math levels and Gann 1×1 in one EA.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Hurst_Envelope_Pro_XAUUSD_M5_hep_shot.png" alt="TL Hurst Envelope Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Hurst Envelope Pro.ex4`](MT4/TL%20Hurst%20Envelope%20Pro.ex4) |
| **MT5** | [`TL Hurst Envelope Pro.ex5`](MT5/TL%20Hurst%20Envelope%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

An EA built on the method of 7iv3 in the Forex Factory thread 709088 "Analysis and Trading based on Envelopes, Waves, Cycles" (started by parisboy, indicators by Terry Pascoe):

- J.M. Hurst centered moving averages 32 / 64 / 128 / 256 / 512 with fixed-width envelopes (edge band / mid band)
- Murrey Math octave 0/8 .. 8/8
- Gann 1X1 and 2X1 angles in Murrey units (1/8 of price per 1/8 of the frame)

## Install

- **MT5: copy "TL Hurst Envelope Pro.ex5" to** — File > Open Data Folder > MQL5\Experts MT4: copy "TL Hurst Envelope Pro.ex4" to  File > Open Data Folder > MQL4\Experts Refresh the Navigator, drag the EA onto a chart (recommended: XAUUSD or BTCUSD, M5). Tick "Allow Algo Trading" (MT4: "Allow live trading"). "Allow DLL imports" is only needed for the link buttons on the dashboard.

## Setups (each can be switched on / off - default: only S1 is On)

- S1 1X1 BREAK (7iv3 core) A swing low at 0/8-2/8 (or outside the 128 envelope). A bar closes above the descending 1X1 angle AND the VTL ("action signal"). The EA waits for the retest of the broken 1X1 / 50 % of the new move and buys. Targets 6/8 and 7/8. Optional (off by default): exit when price closes back below the ascending 2X1. Short = mirror. S2 EDGE BAND (Hurst) In a flat (cyclic) market: a bar outside the 128 envelope, the next bar closes back inside -> trade back to the CMA (mid band). S3 MID BAND / 2X1 PULLBACK 3+ CMAs point in one direction. Pullback to the 2X1 angle / 50 % of the move -> targets: the high of the move and the focal-point doubling.

- Every setup is opened as two orders: half closes at target 1, the other half runs to target 2 with the stop at break-even. H1 filter ("reverb"): trades only in the direction of the H1 CMA 128.

## No Lookahead

Centered moving averages need future bars - every indicator that draws them repaints. This EA only uses closed bars. The missing right end is estimated on every bar (default: truncated TMA = "LWMA bridge" of Terry Pascoe; alternatives: shift 16 of parisboy, linear). The estimated part is drawn dotted on the chart.

## Important Inputs

Risk per setup (% of balance), min. / max. stop (in 1/8 of the Murrey octave), min. reward / risk, envelope mode (auto % / CW points / octave), Murrey frame (0 = auto), H1 filter, optional cycle filter, trading window, max. setups.

## Backtest (honest, RoboForex real ticks, Jan-Sep 2026, 0.5 % risk, default inputs, S1 only)

only gold M5 Jun-Sep was positive (1.12 / 1.16) - so they are OFF by default. In short: the price part of the method is automated faithfully, but it showed NO stable edge in these tests. The timing part of 7iv3 (astronomy, cycle composites) cannot be automated. Use it as a study / signal tool and on demo first.

## Free Edition - no lock, no expiry. Trading involves high risk. No profit promise.

Test on a demo account first. Past results do not guarantee future results.

YouTube   <https://www.youtube.com/@traderlifestyle> Forum     <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4> Source    <https://www.forexfactory.com/thread/709088-analysis-and-trading-based-on-envelopes-waves-cycles>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
