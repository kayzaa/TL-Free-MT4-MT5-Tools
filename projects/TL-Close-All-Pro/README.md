<div align="center">

# ⚡ TL Close All Pro

**One button closes every position of the chart symbol. Full panel, small pill or a tiny pixel-sized button.**

![version](https://img.shields.io/badge/version-v1.10-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_CloseAllPro_v110_sizes.png" alt="TL Close All Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Close All Pro.ex4`](MT4/TL%20Close%20All%20Pro.ex4) |
| **MT5** | [`TL Close All Pro.ex5`](MT5/TL%20Close%20All%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **One click, one symbol** — **CLOSE ALL TRADES** closes every position of the current chart symbol (buys and sells together). Other symbols are never touched.
- **Three sizes** — full panel, small pill, or a **tiny** button that is only the CLOSE ALL button, sized in pixels by you.
- **Safe dragging** — moving the pill / tiny button never closes anything; only a click without moving does.
- **Optional 2-click confirmation** and smart retries on requotes / busy servers.
- **Never opens trades** — works on hedging and netting accounts, any broker, any symbol.

## 🆕 New in v1.10

- Input **Panel size**: Full panel / Small pill / Tiny (only the CLOSE ALL button).
- Tiny button size in pixels — you choose width and height (e.g. 60 x 18 or 150 x 40).
- Fixed: "start as the small pill" did not work when the panel had been open before. The size input now wins every time the EA is loaded or its inputs are changed.
- The pill / tiny button can be dragged by the button itself.

## 🧠 How it works

- Click **CLOSE ALL TRADES** → all positions of the chart symbol are closed at market.
- The **Magic number filter** decides which positions count (all, manual only, or one EA's trades).
- Pending orders stay untouched unless you enable deleting them.

## 🖥️ Dashboard & chart

- The **full panel** shows positions, buy / sell count, lots, floating P/L and pending orders.
- **X** folds the panel to the small pill (or to the tiny button). Both keep a working CLOSE button.
- **Tiny button**: drag it by the grip (dots on the left) or by the button. Click the grip to open the full panel; X on the panel brings the tiny button back. It shows the number of open trades.
- The position is remembered per chart.
- If another trader.lifestyle panel is on the chart, the panel moves next to it.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Magic number filter | `-1` = all trades of the symbol (default) · `0` = only manual trades · any other number = only trades of that EA |
| Also delete the pending orders | `false` (default) = pending orders stay |
| 2-click confirmation | `false` (default) = one click closes everything · `true` = click, then click CONFIRM within 3 seconds |
| Max. slippage (points) | Default 30 |
| Close attempts per trade | Default 3 — requotes / a busy server get another try |
| Panel size | Full panel / Small pill / Tiny button |
| Tiny button width / height | Default 90 x 22 pixels (range 40–400 x 14–80) |
| Tiny button: show trade count | Default `true` |
| Show tooltips / Panel X / Panel Y / Sound | Display and sound options |

## 🛠️ Installation

1. Open `File → Open Data Folder`.
   - **MT4:** copy `MT4/TL Close All Pro.ex4` into `MQL4 → Experts`.
   - **MT5:** copy `MT5/TL Close All Pro.ex5` into `MQL5 → Experts`.
2. Restart the terminal, or right-click **Expert Advisors** in the Navigator → **Refresh**.
3. Drag the EA onto the chart of the symbol you want to close.
4. **Algo Trading / AutoTrading must be ON** — otherwise the button cannot close trades.
5. Optional: tick **Allow DLL imports** so the link buttons (YouTube, WhatsApp …) open your browser.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
