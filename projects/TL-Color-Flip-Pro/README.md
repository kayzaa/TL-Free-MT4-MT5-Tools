<div align="center">

# ⚡ TL Color Flip Pro

**The GJ "Holygrail" colour-flip indicator turned into a one-file EA with an animated 3D coin dashboard.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/screenshot.png" alt="TL Color Flip Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Color Flip Pro.ex5`](MT5/TL%20Color%20Flip%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **"MY HOLYGRAIL SYSTEM" automated** — the GJ indicator (GBPJPY M5) rebuilt as an Expert Advisor, following the original Forex Factory post rule by rule.
- **One file** — the GJ indicator window and the 3D logo are built in. No GJ.mq4 or any other indicator needed.
- **Repaint-aware** — the EA only acts on the final colour at candle close.
- **Basket logic** — alternating orders, smallest-profit closing and an equity target, exactly as the post describes.
- **Optional safety layer** — emergency stop, max lot, spread filter and Friday close, all switchable.
- **Animated 3D coin panel** — flips blue / red on every confirmed colour change.

## 🧠 Strategy rules

The indicator has two colours: **BLUE = long, RED = short.**

1. **Wait for the close.** The indicator repaints, so after a colour change the EA waits until the candle closes.
2. **Alternate orders.** On the next candle it places an order in the new colour with the **same lot size** (buy, sell, buy, sell …).
3. **Trim the basket.** With 4 or more open positions, on the next colour change the EA looks at the positions **opposite** to the new order, closes the one with the **smallest profit**, then places the new order.
4. **Equity target.** This repeats until the whole basket reaches **+X % equity** → close all.
5. **Trend end.** … or until the trend ends (colour change + candle close): if the basket is in profit at a colour change, everything is closed (input **"TREND END rule"**).

> **Interpretation of rule 5:** the post is ambiguous here. Closing everything on every colour change would make rule 3 impossible, so the default closes all only when the basket is in profit — matching the indicator's own notes ("close-all when the accumulated profit is positive"). Other options: **every colour change** or **off**.

### Indicator math (1:1 from Gj.mq4)

> MA = (LWMA 14 of typical price + LWMA 14 of open) / 2
>
> Colour of bar i = **BLUE** if MA(i-1) >= MA(i), else **RED**

Because of the −1 shift in the original, the last closed bar depends on the running candle — that is the repaint. The EA only uses the final colour at candle close.

### Safety (not part of the original idea, can be switched off)

- Emergency stop at −20 % of the cycle start balance
- Max lot
- Spread filter
- Optional Friday close

## 🖥️ Dashboard & chart

- Animated 3D coin that turns blue / red on every confirmed colour change
- GJ colour strip, including the repainting bar
- Basket list in historical order — **gold** marks the position that will be closed next
- Equity target and the 5 rules with their live state
- Hover over any box for an explanation
- The panel always fits the chart and splits into columns on small charts

## 🛠️ Installation

1. In MT5 choose **File → Open Data Folder → MQL5 → Experts** and copy `TL Color Flip Pro.ex5` there.
2. Restart MT5, or right-click **Expert Advisors** in the Navigator → **Refresh**.
3. Drag the EA onto a chart (original setup: **GBPJPY M5**) and enable **Allow Algo Trading**.
4. Tick **Allow DLL imports** only if you want the YouTube / RoboForex / WhatsApp buttons to work.

## 📋 Requirements

- A **hedging** account — buy and sell positions are open at the same time.

## 🙏 Credits

- Original idea: "MY HOLYGRAIL SYSTEM" by **richest** on Forex Factory (13 May 2009) — [original post](https://www.forexfactory.com/thread/post/2731571#post2731571)

## ⚠️ Notes

- The basket keeps adding same-size positions in both directions until the equity target or the trend-end rule closes it, so exposure can grow quickly — test on demo first.
- The underlying indicator repaints; the EA deliberately acts only on closed candles.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
