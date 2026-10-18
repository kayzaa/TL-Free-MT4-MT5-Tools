<div align="center">

# ⚡ TL Wyckoff Mitigation Pro

**Wyckoff distribution schematic + two-candle system: SA → UT / spring → flip → entry, with phase tracker. EA or indicator mode.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_WyckoffMitigationPro_screenshot.png" alt="TL Wyckoff Mitigation Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Wyckoff Mitigation Pro Indicator.ex4`](MT4/TL%20Wyckoff%20Mitigation%20Pro%20Indicator.ex4) |
| **MT4** | [`TL Wyckoff Mitigation Pro.ex4`](MT4/TL%20Wyckoff%20Mitigation%20Pro.ex4) |
| **MT5** | [`TL Wyckoff Mitigation Pro Indicator.ex5`](MT5/TL%20Wyckoff%20Mitigation%20Pro%20Indicator.ex5) |
| **MT5** | [`TL Wyckoff Mitigation Pro.ex5`](MT5/TL%20Wyckoff%20Mitigation%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Built after the public IMPACT FX YouTube video "How to spot mitigation before it happens" (Wyckoff distribution schematic #2 + the two-candle system). Independent build of the rules shown in the video.

## Files

- **MT5/Experts/TL Wyckoff Mitigation Pro.ex5** — EA (trades) - set "Mode" to Indicator mode for signals only MT5/Indicators/TL Wyckoff Mitigation Pro Indicator.ex5   same model as a pure indicator (never trades) MT4/Experts/TL Wyckoff Mitigation Pro.ex4 MT4/Indicators/TL Wyckoff Mitigation Pro Indicator.ex4 Copy them into File -> Open Data Folder -> MQL5 (or MQL4) -> Experts / Indicators, then refresh the Navigator. Enable "Allow DLL imports" - only needed for the link buttons in the dashboard.

## The Model (closed bars only, no repaint)

- **2CS origin** — last opposite candle before the newest leg high / low (inside bars do not count) SA          first CLOSE through the 2CS origin = sign of weakness (sell) / strength (buy) UT / SPRING after the SA price runs the high (sell) / low (buy) from before the SA FLIP        close through the last candle of the UT / spring leg = new two-candle break -> flip zone ENTRY       limit at the flip zone edge (or middle, or market at the flip close) STOP        beyond the UT / spring + ATR buffer (or fixed points - the video uses 15 NAS points) TARGET      origin of the leg (the mitigation), min. reward / risk filter MANAGEMENT  partial (default 50 %) when the SA level runs + stop to break-even, early exit when price closes back beyond the flip zone ("the high runs") FILTERS     optional higher timeframe 2CS leg in the trade direction, session hours, direction

## On The Chart

2CS origin box, SA / UT / SPRING labels, grey FLIP zone, red risk + blue reward box per setup with the result in R. Dashboard: two-candle system, distribution + accumulation phase tracker (SA -> UT -> FLIP -> ENTRY), trade plan, virtual results of the loaded history (bar OHLC, stop first, no spread), position / alerts. X closes the dashboard to a pill, drag the header to move it, it avoids other trader.lifestyle panels.

## Notes

The video trades NAS100 on M1 (and 5-second charts). In our tests the rules worked best on XAUUSD M5 / M15; M1 and the forex majors were negative after spread. Test on demo first. Trading involves high risk.

trader.lifestyle - Forex Factory thread: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
