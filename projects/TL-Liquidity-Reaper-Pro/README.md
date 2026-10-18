<div align="center">

# ⚡ TL Liquidity Reaper Pro

**Independent MetaTrader implementation of the published Liquidity Reaper [JOAT] rules — requested on Forex Factory.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Liquidity Reaper Pro.ex5`](MT5/TL%20Liquidity%20Reaper%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Published rules, brought to MT5** — an independent implementation of Liquidity Reaper [JOAT] by officialjackofalltrades, requested on Forex Factory.
- **Liquidity pools from confirmed pivots** — swing highs / lows become pools; crossing one opens a pending sweep.
- **Strict confirmation** — close back through the pool, minimum excursion and a volume check, on bars 1–3 after the sweep.
- **ATR stop + 1R / 2R / 3R targets** — all three drawn on the chart; you choose which one closes the full position.
- **Safe by default** — Auto Trading is OFF; signals, rails, zones and the dashboard work without placing a single order.
- **Closed-bar logic** — signals are handled once per closed bar; startup history never creates orders.

## 🧠 Strategy rules

### Liquidity pools & sweeps

- Confirmed swing highs / lows become **liquidity pools**. Default strength: **8 completed bars on each side** — a pivot is not known before its right-side bars close.
- Crossing a pool **consumes** it and opens a **pending sweep** for that side.
- A new sweep on a side replaces that side's pending one. When several pools are crossed together, the oldest crossed pool is kept (matching the public indicator's reverse traversal and overwrite behaviour).
- Active pool limit: **12 per side**. Swept zones stay on the chart for **120 bars** by default.

### Confirmation

Confirmation is allowed on **bars 1, 2 or 3 after the sweep** — never on the sweep bar itself.

| | Condition |
|---|---|
| **BUY** | Close above the swept low pool **and** above the confirmation candle's open |
| **SELL** | Close below the swept high pool **and** below the confirmation candle's open |
| **Excursion** | The maximum excursion beyond the pool must reach **25 %** of the ORIGINAL sweep candle's range (the extreme keeps updating while the sweep is pending) |
| **Volume** | Confirmation volume ≥ **1.1 ×** its 20-bar SMA (including the confirmation candle) |

### Stop, targets & execution

- **Stop:** Wilder ATR(14) × 1.5 from the signal close (alternative: a percentage of the signal close).
- **Targets:** TP1 / TP2 / TP3 = 1R / 2R / 3R, all shown on the chart. `InpExitTarget` selects a **full-position exit** at TP1, TP2 or TP3 (default TP3).
- No automatic partial exits, break-even or trailing.
- **One EA position per symbol / magic.** Opposite signals close and reverse by default; `InpReverse=false` ignores new signals while a position is open. Same-direction signals never add exposure.
- **Sizing:** 0.5 % of balance by default, using the actual quote-to-stop distance. `InpRiskPct=0` selects fixed lots. Lots are rounded down; undersized orders are skipped rather than increased to the broker minimum.
- Spread, lot cap, margin, tick size and stop distance are checked. SL and the selected TP are sent with the order. A failed request is logged and not retried on that signal.
- **CLOSE ALL** affects this EA's symbol / magic only. Foreign positions on an MT5 netting symbol prevent new orders. Use a distinct magic number for independent instances / timeframes.

## 🔄 Differences from the TradingView indicator

- Orders are submitted **after the confirmation candle closes**, at the next available quote — fill price, spread, slippage and broker rules apply.
- TradingView can show tentative intrabar signals; this EA waits for the bar close.
- Forex **tick volume** is used by default. `InpRealVolume` uses real volume only when the broker supplies it.
- Different feeds, sessions and bars can change signals — matching settings do not guarantee identical TradingView chart marks.
- The video's manually drawn trendlines are **not** an automatic trend filter.
- On restart, signal state is rebuilt from `InpWarmup` bars (default 3000). Raid counts refer to this loaded history, not to account results.

## 🖥️ Dashboard & chart

- Standard trader.lifestyle Canvas panel: drag the header, **X** minimizes to a pill, click the pill to reopen.
- Hover explanations, responsive columns, RoboForex / WhatsApp / YouTube / Forex Factory / IndicatorGenius buttons.
- Chart TP / SL graphics describe the **most recent signal**, including signals that were not traded; the **POSITION** block reports actual broker positions separately.
- The visual framework freezes once its stop or TP3 is touched and is replaced by the next signal. The chosen execution target does not alter signal history.
- Native time / price chart objects follow scrolling and zooming; deleted panel and overlay objects are recreated.
- No account lock and no expiry.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| `InpAutoTrade` | Enables order placement (OFF by default; also switchable from the panel) |
| `InpExitTarget` | Full-position exit at TP1, TP2 or TP3 (default TP3) |
| `InpReverse` | `true` = opposite signal closes and reverses; `false` = ignore new signals while a position is open |
| `InpRiskPct` | Risk % of balance per trade (default 0.5); `0` = fixed lots |
| `InpRealVolume` | Use real volume when the broker supplies it (default: tick volume) |
| `InpWarmup` | Bars used to rebuild signal state on restart (default 3000) |

## 🛠️ Installation

1. Copy `TL Liquidity Reaper Pro.ex5` into **File → Open Data Folder → MQL5 → Experts**.
2. Refresh the Navigator and attach the EA to a **standard candlestick chart** — the chart symbol and timeframe are used for signals.
3. Auto Trading is **OFF** by default. To place orders, enable `InpAutoTrade` (or the panel toggle) **and** MetaTrader's trading permissions.
4. Allow DLL imports only if you want the website buttons to open your browser (the imported Windows `shell32` function is used for these buttons only).

## ⚠️ Notes

- This is an independent implementation, **not an official JOAT product**.
- Signals do not guarantee profitable trades. Get familiar with the behaviour on a demo account first.

## 🙏 Credits

- Original indicator: [Liquidity Reaper [JOAT] on TradingView](https://www.tradingview.com/script/7J5v2QPQ-Liquidity-Reaper-JOAT/) by **officialjackofalltrades**
- Video: [Video on YouTube](https://www.youtube.com/watch?v=RJuGsIMTd1k)
- Request: [Xepo-fx, post #256 on Forex Factory](https://www.forexfactory.com/thread/post/15960735#post15960735)

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
