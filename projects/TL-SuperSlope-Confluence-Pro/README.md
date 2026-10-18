<div align="center">

# ⚡ TL SuperSlope Confluence Pro

**Improved Baluda SuperSlope v2.2 — currency slope confluence across pairs and timeframes.**

![version](https://img.shields.io/badge/version-v3.0-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL%20SuperSlope%20Confluence%20Pro.png" alt="TL SuperSlope Confluence Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL SuperSlope Confluence Pro.ex4`](MT4/TL%20SuperSlope%20Confluence%20Pro.ex4) |

> Compiled build only — source code is not published.

## ✨ Highlights

- 🔒 **Repaint fixed** — every bar uses the price that was known when that bar closed ("point in time").
- 🏹 **Arrows only on CLOSED bars** — an arrow never disappears or moves.
- 🧮 **Confluence score** — up to 8 switchable filters must agree before an arrow appears.
- ⚪ **Filtered signals stay visible** — a grey dot marks a slope flip without enough confluence.
- ✅ **Live checklist panel** — click the header to collapse.
- 🔌 **iCustom buffers for EAs** — slope, mirror, buy / sell score and signal.

## 🩹 Why the old version repainted

With `timeFrame = D1` on an intraday chart, v2.2 used the FINAL D1 close for every intraday bar of that day. History therefore showed slope values and arrows that were never on the chart live — especially on the first bars of a new day.

## 🧠 How it works

**Slope modes**
- **Point in time** (no repaint) — every bar uses the price known when that bar closed. The live value is identical to v2.2.
- **Last CLOSED higher-TF bar** — 100 % stable, but one D1 bar slower.
- **Original** — the old v2.2 behaviour, for comparison.

**Confluence score** — each filter can be switched on/off in the inputs. The base D1 slope direction is always required.

| Filter | Condition |
|---|---|
| **F1** | Extra TF 1 (W1) slope agrees |
| **F2** | Extra TF 2 (MN) slope agrees |
| **F3** | Chart-TF slope agrees (timing) |
| **F4** | Base slope gaining strength |
| **F5** | Close above / below EMA 50 |
| **F6** | ADX ≥ 20 and +DI / -DI agree |
| **F7** | RSI above / below 50 |
| **F8** | Not overextended (inside ± level) |

> An arrow appears only when the score reaches **MinConfluence** (default 5 of 7 active filters). A **grey dot** = the slope flipped but confluence was too low (filtered signal).

**Alerts** — popup / push / e-mail, only on closed bars.

## 🔌 Buffers for EAs (iCustom)

| Buffer | Value |
|---|---|
| 0 | Slope |
| 1 | Mirror |
| 2 | Buy score |
| 3 | Sell score |
| 4 | Signal (+1 buy / -1 sell on the signal bar) |

## 🛠️ Installation

1. Copy the `.ex4` to `File → Open Data Folder → MQL4 → Indicators`.
2. Restart MT4, or right-click "Indicators" in the Navigator → **Refresh**.
3. Drag the indicator onto the chart.
4. Tick **Allow DLL imports** only if you want the panel link buttons to work.

## ⚠️ Notes

- MT4 only.
- "Original" mode reproduces the old repainting behaviour on purpose — use it for comparison only.
- Indicators help with timing; they do not guarantee profits. Test on demo first.

## 🙏 Credits

- Based on **Baluda's SuperSlope v2.2**, with the arrows / MTF table by **gprince66** and the all-pairs fix by **VirtualFM**.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
