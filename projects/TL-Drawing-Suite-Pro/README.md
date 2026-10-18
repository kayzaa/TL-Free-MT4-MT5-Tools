<div align="center">

# ⚡ TL Drawing Suite Pro

**A drawing toolbar for MetaTrader — 30 tools, undo / redo, works on every symbol and timeframe.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_DrawingSuitePro_screenshot.png" alt="TL Drawing Suite Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Drawing Suite Pro.ex4`](MT4/TL%20Drawing%20Suite%20Pro.ex4) |
| **MT5** | [`TL Drawing Suite Pro.ex5`](MT5/TL%20Drawing%20Suite%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **30 drawing tools** — lines, channels, Fibonacci, Gann, Elliott waves, text, measure, long / short position tools and alert lines.
- **Hotkeys for everything** — press T, H, F, L … and draw; hotkeys work even while the toolbar is closed.
- **Undo / redo** — Ctrl+Z / Ctrl+Y, 200 steps, survives a timeframe change.
- **Copy, save, load** — copy drawings to every chart of the same symbol, save / load sets shared by all your MT4 + MT5 terminals on this PC.
- **Full styling** — 12 colours, 5 widths, 5 line styles, fill, ray, magnet, lock and timeframe visibility.
- **Plain chart objects** — drawings stay on every timeframe and are saved with the chart / template.

## 🧰 30 tools (click the icon or press the hotkey)

| Group | Tools (hotkey) |
|---|---|
| **Basics** | Cursor (Esc) · Trend line (T) · Ray (R) · Horizontal line (H) · Horizontal ray (J) · Vertical line (V) |
| **Shapes** | Rectangle (B) · Zone, auto-extended to the right (Z) · Triangle (G) · Brush / freehand (W) |
| **Fibonacci** | Fibo retracement with prices (F) · Fibo extension (E) · Fibo time zones · Fibo fan · Fibo channel |
| **Channels & Gann** | Parallel channel (C) · Regression channel · StdDev channel · Pitchfork (P) · Gann fan |
| **Annotation** | Text in any language (X) · Price label (Q) · Arrow up (U) · Arrow down (D) · Elliott wave 0–5 (K) |
| **Trading** | Measure: pips, %, bars, time (M) · Long position (L) · Short position (S) — R:R + lot size |
| **Alerts & time** | Alert line — popup / sound / push / e-mail when price crosses (A) · Cycle lines |

## 🧠 How it works

### Drawing

- **2-point tools:** click, move (live preview), click. **Esc** cancels.
- **Text:** click the chart, type into the box, press **Enter** (or click the chart). Click an existing text with the Text tool to edit it.
- **Position tool:** click the entry, click the stop — the target is set by the R:R input. Drag the entry / stop / target line and all boxes and labels update.

### Style

- 12 colours (the last one is your own colour from the inputs), width 1–5, 5 line styles
- **FILL**, **RAY** (extend right), **MAGNET** (snap to open / high / low / close), **BACK**, **LOCK**, **KEEP** tool
- **TF visibility:** all timeframes / only this one / this and lower
- Select drawings (double-click) and click a colour / width / style to change them

### Actions

| Action | What it does |
|---|---|
| **UNDO / REDO** | Ctrl+Z / Ctrl+Y, 200 steps, survives a timeframe change |
| **DELETE** | Removes the selected drawings |
| **CLEAR** | Removes all drawings (2 clicks, can be undone) |
| **HIDE / SHOW** | Toggles all drawings |
| **COPY** | Copies drawings to every chart of the same symbol |
| **SAVE / LOAD** | Shared by all your MT4 + MT5 terminals on this PC |

## 🖥️ Dashboard & chart

- Drag the header to move the toolbar.
- **X** closes it to a small pill; click the pill to open it again.
- **−** switches to a compact toolbar, **?** turns tooltips on / off.
- Hotkeys keep working while the toolbar is closed.
- Position and settings are remembered per chart.

## 🛠️ Installation

1. Choose **File → Open Data Folder**.
2. Copy the file for your platform:
   - **MT4:** `TL Drawing Suite Pro.ex4` → **MQL4 → Indicators**
   - **MT5:** `TL Drawing Suite Pro.ex5` → **MQL5 → Indicators**
3. Refresh the Navigator and drag the indicator onto a chart.
4. Tick **Allow DLL imports** only for the link buttons (YouTube / RoboForex / WhatsApp / Forex Factory) — drawing works without it.

## ⚠️ Notes

- The indicator switches **"Chart on foreground"** off so the toolbar stays on top of the candles; the setting is restored when you remove it.
- MT4 stores object text in the Windows code page: Chinese / Japanese / Korean text works on a Windows system set to that language. MT5 supports every language everywhere.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
