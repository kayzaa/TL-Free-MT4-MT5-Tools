<div align="center">

# ⚡ TL Small Matter Pro

**hayseed's top-down ladder system: D1 TSR bias, H4 ALMA trigger and a ladder basket.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Small_Matter_Pro_panel.png" alt="TL Small Matter Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Small Matter Pro.ex5`](MT5/TL%20Small%20Matter%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **hayseed's journal, automated.** Built after the Forex Factory trading journal "it's a small matter" and hayseed's own MT4 tools.
- **Top-down bias:** weekly TSR(89) Hull MA decides buys only or sells only.
- **H4 trigger:** ALMA colour change, confirmed by the H4 zigzag leg.
- **Ladder entry:** one market order plus a ladder of 5 limit orders, like his "send sell and sell limits" script.
- **Basket management:** per-order targets, target cut at 6 open orders, zigzag-based exits and a basket trailing stop.

## 🧠 Strategy rules

| Step | Rule |
|---|---|
| **1 Bias** | Weekly TSR(89) (Hull MA): lime → buys only, red → sells only |
| **2 Trigger** | ALMA(9, 6, 0.85) colour change on H4 in the bias direction |
| **3 Zigzag** | The current H4 zigzag(12,5,3) leg points the same way |
| **4 Entry** | 1 market order + a ladder of 5 limit orders beyond the price |
| **5 Exits** | See below |

**Exits**
- Target = 0.30 × weekly ATR per order.
- From 6 open orders, all targets are cut to 1/3 from the average price.
- Winners are closed when the H4 zigzag leg reaches 2× its average length.
- Basket trailing stop ("trailing account profit closeall").
- The basket is kept when the bias turns (hayseed: *"negative till the market resumes"*).
- **No stop loss per order** — a safety net closes the basket at −25 % of balance.

## 📋 Requirements

- **Hedging account** (the ladder holds several orders at once).
- One chart per pair (any timeframe — the EA works on H4 internally), one magic number per pair.

## 🛠️ Installation

1. In MT5 open **File → Open Data Folder** and copy `TL Small Matter Pro.ex5` to `MQL5 → Experts`.
2. Restart MT5 or refresh the Navigator.
3. Drag the EA onto one chart per pair and give each pair its own magic number.
4. Enable **"Algo Trading"**. Enable **"Allow DLL imports"** only for the link buttons (YouTube / RoboForex / WhatsApp / Myfxbook).

## 🙏 Credits

Built after the Forex Factory trading journal ["it's a small matter"](https://www.forexfactory.com/thread/462458-its-a-small-matter) by **hayseed** — his posts #27, #140, #237, #284, #338, #362, #366, #369, #432 and his own MT4 tools (TSR.mq4, alma.mq4, ZigZag w order alerts.mq4, send sell and sell limits.mq4).

## ⚠️ Notes

- **Averaging without a stop loss can lose the whole account.** The only hard limit is the basket safety net at −25 % of balance. Use a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
