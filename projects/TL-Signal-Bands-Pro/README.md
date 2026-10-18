<div align="center">

# ⚡ TL Signal Bands Pro

**Centred TMA signal bands with band-touch signals, band ladder and an optional companion EA.**

![version](https://img.shields.io/badge/version-v1.10-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Signal_Bands_Pro_tlsbp_shot_M5_s1.png" alt="TL Signal Bands Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Signal Bands EA.ex5`](MT5/TL%20Signal%20Bands%20EA.ex5) |
| **MT5** | [`TL Signal Bands Pro.ex5`](MT5/TL%20Signal%20Bands%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Triangular MA signal bands** — TMA (half-length 60, typical price) with three ATR bands per side.
- **Closed-bar circles** — buy (green) / sell (red) signals on the closed bar that never move or disappear.
- **v1.10 signal logic** — less noise, circles really at the bands: band touch + rejection candle + slope filter.
- **Two band modes** — *Centered* (video look) or *Real-time* (never changes).
- **Companion EA** that trades every circle — and carries the indicator inside, so it also works alone.
- **Collapsible dashboard** with band ladder, live signal check and EA / martingale state.

## 🧠 How it works

### Indicator

- **Centre line:** triangular moving average (TMA, half-length 60, typical price).
- **Bands:** TMA ± ATR(100, shifted 10 bars) × **2.4** (dotted) / **3.0** / **3.6**.
- **Signals (v1.10):**
  - the signal bar itself must reach the middle band (3.0 × ATR) of that bar,
  - a rejection candle (opposite colour, close back inside) must follow within 2 bars of the touch,
  - buy and sell alternate, and there is no signal against a steep TMA (> 0.30 ATR per 10 bars).
- **Band mode:** *Centered* (video look) recalculates the last 60 bars of the **bands**. *Real-time* never changes.

### EA rules

> **Entry:** a trade on every circle, at the bar close.
> **Exit:** price touches the opposite inner band (2.4 × ATR) **or** the next (opposite) circle closes and reverses the trade.
> **Martingale (optional, default ON):** after a losing trade the lot is multiplied (× 2) until a trade closes in profit — max 6 steps, max lot 1.00.
> **Optional protection:** hard stop (× ATR) and equity stop (%).

## 🖥️ Dashboard & chart

- Collapsible dashboard — click the title or **MIN**.
- Shows signal state, band ladder, market, live signal check, band scope, a historical check of the EA rule (0.01 lot) and the live EA / martingale state.

## 🛠️ Installation

1. In MT5 open `File → Open Data Folder`.
   - Copy `TL Signal Bands Pro.ex5` (indicator) into `MQL5 → Indicators`.
   - Copy `TL Signal Bands EA.ex5` (EA) into `MQL5 → Experts`.
2. Refresh the Navigator and drag the indicator or the EA onto a chart. The EA carries the indicator inside — it works alone as well.
3. For the EA, enable **Algo Trading**.
4. Optional: enable **Allow DLL imports** only if you want the RoboForex / WhatsApp / YouTube / FF buttons to open links.

## ⚠️ Notes

- **No stop loss by default** (like the original video). Combined with the martingale, losses can grow very quickly and can wipe out an account — consider enabling the hard stop and equity stop, and always test on a demo account first.
- In *Centered* band mode the last 60 bars of the bands are recalculated, so the bands on recent bars can change. The signal circles themselves are set on closed bars and do not move.
- The dashboard's historical check is a quick overview on your chart, not a promise for the future.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
