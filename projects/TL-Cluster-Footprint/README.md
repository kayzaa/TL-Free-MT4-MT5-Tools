<div align="center">

# ⚡ TL Cluster Footprint

**Cluster / footprint chart for MetaTrader: bid × ask volume per price level inside every candle.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Cluster_Footprint_MT5_XAUUSD_M5.png" alt="TL Cluster Footprint" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL_Cluster_Footprint.ex4`](MT4/TL_Cluster_Footprint.ex4) |
| **MT5** | [`TL_Cluster_Footprint.ex5`](MT5/TL_Cluster_Footprint.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Real footprint window** in the style of ClusterDelta — Bid × Ask volume per price row for every bar.
- **Bar volume, delta and cumulative delta** in the header of each bar.
- **Bar POC** marked with a red frame, **diagonal imbalances** as green / red boxes (ratio and minimum volume adjustable).
- **Session or visible volume profile** with Volume, Delta and Price columns, POC and value area.
- **Full-screen mode**, row zoom, history scrolling and a one-click trading panel toggle.
- **MT4 and MT5** — runs on your broker's own data, no external feed needed.

## 🧠 How it works

The indicator splits the volume of every candle into price rows and shows who traded where:

- **MT5** uses the broker's real tick history. Buy / sell is split by the bid tick rule; exchange symbols with trade flags use the real trade volume.
- **MT4** has no tick history, so older bars are approximated from M1 bars. Every bar that forms while the indicator is running is built from live ticks.
- **Forex / CFD volume is tick volume**, not central exchange volume.

## 🖥️ Dashboard & chart

| Control | What it does |
|---|---|
| **Bid x Ask / VP** | Switches the cells between Bid x Ask, Volume and Delta. |
| **− / +** | Row size (multiples of the base step). |
| **Up / Down** | Scroll the rows (MT5 also by mouse wheel); the dot button re-centres on price. |
| **< / > / >\|** | Scroll through history / jump back to the live bar. |
| **Full screen** | Footprint over the whole chart and back (key **F** does the same). |
| **Trade** | Shows / hides MetaTrader's one-click trading panel (SELL \| lot \| BUY); the window keeps that corner free. |
| **Click a price row** | Marks that level. |

## 🛠️ Installation

1. Open `File → Open Data Folder`.
2. **MT5:** copy `TL_Cluster_Footprint.ex5` to `MQL5 → Indicators`. **MT4:** copy `TL_Cluster_Footprint.ex4` to `MQL4 → Indicators`.
3. Restart the terminal or refresh the Navigator, then drag the indicator onto a chart — **M1 to H1** works best.
4. Optional: enable **Allow DLL imports** only if you want the link buttons to open your browser; otherwise the URL is shown.

## ⚠️ Notes

- This is **not ClusterDelta itself**. ClusterDelta is a commercial product with CME futures data — get it at [clusterdelta.com](https://clusterdelta.com). This indicator uses your broker's data.
- On MT4, history bars are an approximation from M1 data; only bars built while the indicator runs use live ticks.
- Indicators cannot send orders — the **Trade** button only toggles MetaTrader's own one-click panel.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
