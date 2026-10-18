<div align="center">

# ⚡ TL Big Bull Fire EA

**The BigBull System 2.0 chart setup rebuilt as a fully automated Expert Advisor with visual trade management.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_BigBullFireEA_screenshot.png" alt="TL Big Bull Fire EA" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Big Bull Fire EA.ex4`](MT4/TL%20Big%20Bull%20Fire%20EA.ex4) |
| **MT5** | [`TL Big Bull Fire EA.ex5`](MT5/TL%20Big%20Bull%20Fire%20EA.ex5) |

> Compiled build only — source code is not published.

## Overview

What it does An Expert Advisor built after the BigBull System 2.0 chart template. The EA calculates the whole system on every closed candle and trades its arrows:

- BUY arrow  = the yellow signal line turns up    -> close sell, open buy
- SELL arrow = the yellow signal line turns down  -> close buy, open sell
- Trend filter (ON by default): buys only above the magenta trend line, sells only below. An arrow against the trend still closes the open trade, but does not open a new one.

Arrows are calculated on closed candles only - they do not repaint.

The chart By default the chart stays clean: candles, BUY / SELL arrows and an animated 3D bull behind the chart that snorts fire from its nostrils. The system lines are calculated in the background either way. Switch them on in the settings if you want to see them:
- Show clouds / zones   (fast lime/yellow, mid purple/green, slow blue/salmon cloud)
- Show lines            (rainbow EMAs, yellow signal line, magenta trend line)
- Show histograms       (power + momentum histogram at the bottom)

trend state, candle countdown, performance of this EA, equity curve, settings, clock. Drag it by the header, "-" collapses it. On small chart windows it switches to a compact layout automatically. Hover any section for an English tooltip (can be off).

Main settings Yellow signal line period (80) . . . . arrows at its turns - higher = fewer arrows Magenta trend line period (200) Auto trading on arrows (true)  . . . . false = signals only Start behaviour  . . . . . . . . . . . wait for the next arrow / enter the current one Opposite arrow closes AND reverses (true) Trend filter (true), Cloud filter (false) Fixed lot or % risk (stop distance = Stop Loss, or 3 x ATR without a Stop Loss) Stop Loss / Take Profit in ATR (0 = exit on the opposite arrow), Break-even in ATR Max spread, magic number, comment Daily profit target (0 = off): stop for the day once it is reached (optionally closes the open trade) News filter (off by default): no new trades around high / medium impact news of the symbol currencies. MT5 uses the built-in calendar. MT4 loads the Forex Factory calendar - allow WebRequest for <https://nfs.faireconomy.media> (Tools > Options > Expert Advisors). Design: fire chart, 3D bull, zones, lines, histograms, panel, FPS, fire intensity, tooltips

Install MT5: copy the .ex5 to  File > Open Data Folder > MQL5 > Experts MT4: copy the .ex4 to  File > Open Data Folder > MQL4 > Experts Refresh the Navigator and drag the EA onto a chart. Enable "Allow Algo Trading". Enable "Allow DLL imports" only if you want the link buttons to open in your browser. Your own chart colours come back when you remove the EA.

Notes
- Any symbol, any timeframe. Default settings are made for XAUUSD M5-H1.
- Lower the Animation FPS if your PC gets slow (default 15).
- Free - no lock, no expiry.

Trading involves risk. Test on a demo account first. This is not investment advice.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
