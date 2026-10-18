<div align="center">

# ⚡ TL Confluence Zones Pro

**Smart-money zones that are scored, not just painted: 9 confluence factors → 0–100 score, plan only after confirmation.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_ConfluenceZonesPro_screenshot.png" alt="TL Confluence Zones Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Confluence Zones Pro.ex4`](MT4/TL%20Confluence%20Zones%20Pro.ex4) |
| **MT5** | [`TL Confluence Zones Pro.ex5`](MT5/TL%20Confluence%20Zones%20Pro.ex5) |

> Compiled build only — source code is not published.

## What It Does

A smart-money zone indicator that does not just paint boxes - it scores every zone and only gives a plan after price confirms:

- WATCHZONE       the strongest zone close to price (blue frame) - attention, no trade yet
- CONFLUENCE      9 independent factors -> score 0-100, every factor visible in the panel
- BUY / SELL ZONE order blocks from the chart AND the higher timeframe, arm on the touch
- CONFIRMATION    a candle closes back out of the zone -> entry, invalidation, target

On the chart
- Buy / sell zones (order blocks) with volume + strength %, names like MAIN BUY, DEEP BUY, MAIN SELL, PREMIUM SELL, higher-timeframe zones with a thick frame
- Fair value gaps (with fill %), removed when filled
- Liquidity pools: equal highs (BSL - seller stops) / equal lows (SSL - buyer stops), xN = number of equal swings, "liquidity pocket" for 2+, sweeps marked
- BOS / CHoCH labels on the chart timeframe and the higher timeframe
- HTF key levels (blue): higher-timeframe swings, previous day / week high + low
- EMA ribbon 8 / 21 / 50 / 200
- Every historical plan with its result (+R / -1R) - nothing hidden
- The current plan: ENTRY, INVALIDATION, TARGET 1 (nearest liquidity), TARGET 2

Dashboard (drag it anywhere, X = small pill, click the pill to open it again)
- Market map: 15M / 1H / 4H / 1D structure, candle pattern, flow, EMA ribbon, decision (bias), nearest liquidity above / below in pips
- Watchzone: score ring + all 9 factors with their points
- Trade plan + position sizer (risk % -> lots for the stop distance)
- Layer buttons: zones, FVG, liquidity, levels, BOS / CHoCH, ribbon, signals
- Avoids other trader.lifestyle panels on the same chart automatically

## The 9 Confluence Factors (max 100)

HTF trend in the zone's direction ........ 20 (neutral 8) Premium / discount of the HTF range ...... 15 (half in 8) HTF key level inside the zone ............ 15 Fair value gap from the displacement ..... 10 Liquidity grab when the zone was built ... 10 Relative volume of the displacement ...... 10 (1.5x) / 5 (1.0x) Fresh zone (first touch) ................. 10 / 4 (second touch) EMA ribbon stacked ....................... 5 + 5 Higher-timeframe zone / stacked on one ... 10

## No Repaint

Everything is calculated on closed bars. Higher-timeframe data is only used after that HTF candle has closed. Plans never move after they appear.

FOR EAs (iCustom buffers) 0-3 EMA ribbon | 4 buy plan entry | 5 sell plan entry | 6 plan stop | 7 plan target 1 8 best watchzone score (last closed bar) | 9 chart trend +1/-1 | 10 HTF trend +1/-1

## Install

- MT5: File -> Open Data Folder -> MQL5\Indicators -> copy the .ex5 -> Navigator -> Refresh
- MT4: File -> Open Data Folder -> MQL4\Indicators -> copy the .ex4 -> Navigator -> Refresh Tick "Allow DLL imports" only if you want the link buttons to open your browser.

## Honest Note

The statistics box replays every plan of the loaded history bar by bar (stop first when stop and target are hit in the same bar, no spread / commission). It is there so you can judge the tool on facts, not on screenshots. Zones and confluence are an analysis framework - not a guarantee. Not financial advice.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
