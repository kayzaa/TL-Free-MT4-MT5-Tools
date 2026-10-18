<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Renko Range Bars Pro

**Real Renko and range-bar charts for MT4 and MT5, rebuilt from history automatically.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_RenkoRangeBarsPro_Panel.png" alt="TL Renko Range Bars Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Renko Range Bars Pro.ex4`](MT4/TL%20Renko%20Range%20Bars%20Pro.ex4) |
| **MT5** | [`TL Renko Range Bars Pro.ex5`](MT5/TL%20Renko%20Range%20Bars%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Real Renko and Range bar charts built from real price data and fed live with every tick. They open as normal charts, so indicators, drawing tools and EAs work on them.

## Files

- **MT5:** — Experts\TL Renko Range Bars Pro.ex5 MT4:  Experts\TL Renko Range Bars Pro.ex4

## Install

- File -> Open Data Folder -> MQL5 (MQL4) -> Experts. Copy the file there.
- Navigator -> right click -> Refresh (no terminal restart needed).
- Drag "TL Renko Range Bars Pro" onto any chart of the symbol (any timeframe). Tick "Allow DLL imports" (link buttons; MT4 also needs it for the live refresh of the offline charts).
- Click a button in the panel (R100 = Renko 100 points, RB500 = Range bars 500 points) -> the chart opens. Keep the EA running on its chart. It feeds all Renko / Range charts of that symbol.

## Renko

- Uniform bricks on a fixed price grid (multiples of the box size)
- A new brick in the same direction needs 1 box. A reversal needs "Reversal" boxes from the last close (2 = classic Renko). The first reversal brick opens one box away from the last close.
- Wicks (on/off): the furthest the price went against the brick while it was forming
- Optional alert when the Renko color changes (popup / sound / push)

## Range Bars

- Every bar spans exactly the set size from high to low
- A bar closes at its high or low as soon as the price moves one tick beyond the range
- The next bar opens at that close (no gaps between bars)

## Inputs

Renko box sizes ............ list, e.g. "100,200,500" (up to 12 buttons) Range bar sizes ............ list, e.g. "200,500,1000" Size unit .................. Points / Pips / Price (e.g. Price 1.0 = 1 dollar on gold) Reversal ................... Renko reversal in boxes (2 = classic) Wicks ...................... Renko wicks on / off Open on start .............. charts that open automatically, e.g. "R100,RB500" History days ............... how far back the chart is built (default 5 days) History source ............. MT5: real ticks (exact) or M1 bars (faster, longer history). MT4 always uses M1. Max bars ................... bars kept per chart (default 20,000) Price ...................... Bid / Ask / Mid / Last Colors ..................... dark quant, classic, or your terminal colors Alerts ..................... Renko color change: popup, sound, push

## Panel

Renko and Range buttons (a green dot = chart open), status of every chart (live / building / bars), current settings and ticks per second. X closes the panel to a small pill, click the pill to open it again, drag the header to move it. The panel moves out of the way of other TL panels on the chart.

## How It Works

MT5: every chart is a custom symbol (e.g. XAUUSD_RNK100 = Renko 100 points, XAUUSD_RNG500 = Range 500). Each bar is one M1 bar of that symbol on a synthetic minute clock starting 1990.01.01, so standard indicators, drawings and EAs (OnTick) run on it. The date scale is hidden because these dates are not real times. The forming bar receives every live tick. MT4: every chart is an offline chart (symbol, M24001, M24002 ...) written as a .hst file and refreshed live. EAs on the offline charts receive ticks. The period number of each Renko / Range size is kept by the EA, so the same size always opens the same offline chart.

## How It Was Tested

MT5 (XAUUSD, live broker ticks): Renko 20 + 50 points and Range 50 + 100 points over 2 days of history, then 150 seconds live. Every bar was compared with a separate calculation straight from the raw ticks: about 55,000 bars, 0 differences in open / high / low / close and tick volume, 0 rule breaks (Renko body = one box on the grid, Range high-low = size, every bar opens at the previous close). MT4: offline charts written from M1 history and fed live, .hst files read back and checked: 0 rule breaks, charts grow live. Panel buttons, close / reopen tested in running terminals.

## Notes

- An EA running on an MT5 Renko chart sees the custom symbol (XAUUSD_RNK100). To trade, it must send its orders to the real symbol (XAUUSD).
- The charts are rebuilt from history every time the EA starts. Drawings on the Renko / Range charts are not moved with the bars after a rebuild.
- Custom symbols / offline files stay after removing the EA. To delete them: MT5 Symbols window -> Custom -> TL Renko Range; MT4 history folder files <symbol>24xxx.hst.
- Renko and Range charts are a different view of price. They are not a trading signal by themselves.

Free tool by trader.lifestyle - YouTube @traderlifestyle - Forex Factory thread: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

## 🖼️ More screenshots

<img src="screenshots/TL_RenkoRangeBarsPro_MT4_Range50.png" width="49%">
<img src="screenshots/TL_RenkoRangeBarsPro_MT5_Renko50.png" width="49%">
<img src="screenshots/TL_RenkoRangeBarsPro_MT5_Range100.png" width="49%">

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
