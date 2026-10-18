<div align="center">

# ⚡ TL HA Wickless Pro

**Wickless Heikin Ashi candles + EMA 200 on M5, with Forex Factory red-folder news filter.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_HA_Wickless_Pro_panel.png" alt="TL HA Wickless Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL HA Wickless Pro.ex4`](MT4/TL%20HA%20Wickless%20Pro.ex4) |
| **MT5** | [`TL HA Wickless Pro.ex5`](MT5/TL%20HA%20Wickless%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Vicky224's Heiken Ashi + EMA 200 idea** from Forex Factory, coded as an EA for **MT4 and MT5** — same rules, same panel.
- **Closed-candle signals** — first wickless HA candle on the right side of the EMA 200.
- **Swing-based stop + balance-% risk sizing** — lot calculated from the SL distance.
- **Red-folder news filter** using the Forex Factory weekly calendar feed (MT5 calendar as fallback).
- **Futures-aware** (MT5) — exchange futures detected automatically, SL on the tick grid.
- **Full chart visuals** — HA candles, EMA 200, signal arrows and the simulated trades of the chart history.

## 🧠 Strategy rules

| | BUY | SELL |
|---|---|---|
| **Signal** | First bullish HA candle **without a lower wick** | First bearish HA candle **without an upper wick** |
| **Trend filter** | Close **above** the EMA 200 | Close **below** the EMA 200 |
| **Stop loss** | 2 pips below the previous swing low | 2 pips above the previous swing high |
| **Take profit** | At the end of the 3rd consecutive HA candle | At the end of the 3rd consecutive HA candle |

- Heiken Ashi, confirmed on **closed** candles, timeframe **M5** (other timeframes selectable).
- **Risk 0.50 % of the balance** per trade (lot size from the SL distance).
- No break-even, no partial close, no trailing stop, no daily limits, all trading hours.
- **News filter:** no new trade 5 minutes before and after red-folder news.
- One trade at a time per pair. Several pairs = several charts (one EA per chart).

## 🔍 How the EA reads the rules

- **"First"** = the first wickless candle of the current HA run (since the last HA colour change) that is on the right side of the EMA. Input **Which wickless candle**: FIRST OF THE RUN (default) / ONLY RIGHT AFTER A COLOUR CHANGE / EVERY wickless candle.
- **Entry** at the open of the next candle, right after the signal candle has closed.
- **Swing low / high** = lowest low / highest high with 2 candles on each side (fractal) — the most recent one below (buy) / above (sell) the entry price, max. 100 candles back.
- **Timeframe:** input **Trading timeframe** (M5 by default). Anything from M1 to D1 works; "current" = the chart timeframe. Put the chart on the same timeframe to see the HA candles and arrows the EA uses.
- **Pip:** 10 points on 5/3-digit symbols, 0.1 on gold (input **Points per pip** to override).
- If even the minimum lot would risk more than 0.5 %, the trade is skipped (input).

### Take profit — two switches, use one or both

| Setting | Behaviour |
|---|---|
| **TP 1** "close after X consecutive HA candles" | Closes when the X-th HA candle after the entry has closed (X = 3 by default) |
| **TP 2** "close when an HA candle closes in the opposite colour" | Closes on the first opposite-colour HA candle |
| Both ON (default) | Close after 3 candles, or earlier if the HA colour changes |
| Only TP 1 | Always hold exactly X candles |
| Only TP 2 | Hold until the HA colour changes (can be many candles) |
| Both OFF | Only the stop loss closes the trade (the EA warns you in the log) |

Input **the signal candle counts as candle #1** if you count it differently.

## 📰 News filter (red folder)

- **Source AUTO:** the Forex Factory weekly calendar feed (the real red folders). Add `https://nfs.faireconomy.media` once under `Tools → Options → Expert Advisors → Allow WebRequest for listed URL`.
- **MT5:** without the URL the EA falls back to the MT5 economic calendar (high importance).
- **MT4:** has no built-in calendar, so the URL is needed for the news filter.
- Checks the base and the quote currency of the pair (EURUSD: EUR + USD, XAUUSD: USD).
- Optional: orange-folder news too, and closing an open trade before the news.
- The panel shows the next red-folder event with a countdown.
- The Strategy Tester has no news data, so the filter is inactive there.

## 🪙 Futures (MT5, e.g. AMP Global: MGCZ26 micro gold, GCEZ26 gold)

- Detected automatically from the symbol settings (exchange futures).
- 1 pip = 1 tick (0.1 on gold futures), so "2 pips" = 2 ticks behind the swing.
- Whole contracts; the SL is placed exactly on the tick grid.
- Position size: 1 micro gold contract with a typical M5 swing stop risks about 30–150 USD. At 0.5 % risk that needs roughly 20,000 USD or more — otherwise most signals are skipped. Set **Skip the trade if even the min. lot risks more** = `false` to always trade 1 contract (the risk per trade is then higher than 0.5 %).
- Netting accounts: one position per symbol — do not trade the same contract by hand.
- Contract roll: when MGCZ26 expires, put the EA on the next contract (MGCG27).

## 🖥️ Dashboard & chart

- Heiken Ashi candles on the chart, wickless candles in bright green / red, EMA 200 (on MT4 the EA draws them itself — keep the chart on M5). The normal candles are hidden behind them while the EA runs and restored on removal.
- Arrows at every signal + the simulated trades of the chart history (dotted line from entry to exit, green / red by outcome; hover for entry + SL).
- **Panel:** position, candle count (1 of 3), SL, HA mini chart, news filter, results, TRADING ON / PAUSE, CLOSE ALL, link buttons.
- **Alerts:** popup, sound, push, e-mail.

## 🛠️ Installation

1. Open `File → Open Data Folder`.
   - **MT4:** copy `MT4\TL HA Wickless Pro.ex4` into `MQL4 → Experts`.
   - **MT5:** copy `MT5\TL HA Wickless Pro.ex5` into `MQL5 → Experts`.
2. In the Navigator right-click **Expert Advisors → Refresh**.
3. Open an **M5 chart per pair** and drag the EA onto it. Enable **Allow Algo Trading**.
4. Add `https://nfs.faireconomy.media` to the WebRequest list (see News filter).
5. Optional: enable **Allow DLL imports** only if you want the link buttons (YouTube / RoboForex / WhatsApp / Myfxbook) to open your browser.

## 🙏 Credits

- Strategy idea by **Vicky224** — Forex Factory thread "I will code your EAs and Indicators for no charge", [post #83,260 (Sep 2026)](https://www.forexfactory.com/thread/post/15931316#post15931316).

## ⚠️ Notes

- The chart's simulated history trades and panel results are a visual overview only — no profit promise. Test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
