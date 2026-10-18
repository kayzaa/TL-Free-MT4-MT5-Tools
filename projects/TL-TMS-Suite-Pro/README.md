<div align="center">

# ⚡ TL TMS Suite Pro

**Trading Made Simple suite — Big E's 5-method, arbinka's monitor and Seller9 tools on one screen.**

![version](https://img.shields.io/badge/version-v1.10-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_TMS_Suite_Pro_m30_real_c3_grab_1.png" alt="TL TMS Suite Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL TMS Suite Pro.ex4`](MT4/TL%20TMS%20Suite%20Pro.ex4) |
| **MT5** | [`TL TMS Suite Pro.ex5`](MT5/TL%20TMS%20Suite%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **The whole Trading Made Simple world in one EA** — 28-pair monitor, signals, Big E rule check, alerts, signal tracker and trade manager, MT4 + MT5.
- **28 pairs × 8 timeframes on one chart** — no indicator files, no external dashboard, broker prefix / suffix detected automatically.
- **Big E's rules, checked live** — real TDI cross, candle 1 or 2, the "Big E clock" angle, plus a 14-line animated rule check per pair.
- **19 one-click filters** — and when a filter says no, you see **BLOCKED** plus the filter's name.
- **Pair inspector** — Heiken Ashi chart with the 5 EMA, TMA channel, your trend lines, candle numbers and every TDI cross, plus the full TDI window.
- **Monitor first, trader second** — auto trading is OFF by default; manual buttons always need a confirming second click.

## 🧠 How it works

### The Big E rules the suite checks

- **Green crosses red** on the TDI — a real cross, not just a touch ("a setup is NOT green touching red").
- **Enter at the beginning of candle 1 or 2** of the new Heiken Ashi color. Candle 3 or more: too late, find another trade.
- **Angle**: green at 12–2 o'clock for a long, 4–6 o'clock for a short. 2–4 o'clock is weak — pass.
- **Bounce**: green comes close to red and turns away again — lower odds, but part of the method.
- **Before you click**, look at the basics: does the stochastic confirm, how close are you to 68 / 32, the previous high / low, the trend, small candles, consolidation.
- **Exit**: green goes flat, hooks over or makes a check-mark reversal.

### The building blocks

| Component | Calculation |
|---|---|
| **TDI** (as in "TDI Red Green") | RSI 13 of the close; green = SMA 2 of the RSI, red = SMA 7, yellow market base line = SMA 34; volatility band = base line ± 1.6185 × std. dev. (34); levels 32 / 50 / 68. |
| **Candles** | Heiken Ashi (= Average Price Bars), optionally Heiken Ashi Smoothed or normal candles. |
| **Stochastic** | 8, 3, 3 — direction only. |
| **5 EMA** | Typical price, shift 2 (Big E used shift 3 — both possible). |

### Signal states

| State | Meaning |
|---|---|
| **STRONG BUY / SELL** (pulsing) | Big E entry + all active filters pass + slope 4 or more + the candle crossed the 5 EMA on candle 1–2 + the TDI of the higher timeframe agrees. |
| **BUY / SELL** | Big E entry: green crossed red on the last 1–2 candles, the current candle has the new color, candle 1 or 2, all active filters pass. |
| **BOUNCE BUY / SELL** | Green stayed on one side for 3+ candles, came within 2 points of red and turned away again, fresh candle color, filters pass. |
| **BLOCKED** | An entry pattern is there, but a filter says no — the cell names it (e.g. "BLOCK STOCH"). |
| **LATE** | Same side, but candle 3 or more — Big E: find another trade. |
| **SETUP** | Green crossed red, but the candle color has not changed yet — wait for it. |
| **FORMING** | The live candle is crossing right now. In closed-candle mode the signal comes with the candle close (no flicker). |
| **WAIT** | Nothing to do. |

Signals already present when you start the EA are shown, but not alerted, tracked or traded. Each signal fires once per candle and direction.

### The 19 filters

Click a chip in the filter bar to switch it; start values come from the inputs and your clicks are saved per chart. A filter only blocks BUY / SELL / BOUNCE signals. **ON at start:** SLOPE, ZONE, STOCH, SPREAD, T-LINE, STRENGTH.

| Filter | Rule |
|---|---|
| **SLOPE** | Green slope at the signal at least 2 RSI points per bar (12–2 / 4–6 o'clock). |
| **ZONE** | No long when green is above 68, no short when green is below 32 (Seller9 V13). |
| **STOCH** | Stochastic 8,3,3 moves in the signal direction and is between 20 and 80. |
| **5 EMA** | Last closed candle closed above (long) / below (short) the 5 EMA shift 2 — the original setup candle of the 5-method. |
| **HTF TDI** | Green on the same side of red on the next higher timeframe. |
| **HTF HA** | Candle color of the next higher timeframe agrees. |
| **MBL** | Green above (long) / below (short) the yellow market base line. |
| **PATTERN** | Seller9's candle patterns (post #2627): #1 = 3 opposite + 3 same-color closed candles, #2 = 3 opposite + 1 same, #3 = 3 opposite + 2 same, and the current candle beyond its open. |
| **ADR** | Today used at most 80 % of the average daily range (room left to run). |
| **SPREAD** | Spread at most 3 pips. |
| **WINDOW** | Only in the first 20 minutes of the new trigger candle (Seller9's Candle2TradeWindow). |
| **NEWS** | No signal 30 minutes before / after high-impact news of the two currencies (MT5 economic calendar; in MT4 the filter always passes). |
| **TMA** | TMA zone (TmaTrue as in Seller9's EA): middle = LWMA 56 of the close, band = middle ± 2 × ATR 100. With zone 50 % a long needs price half a band below the middle, a short half a band above — buy the pullback, not the top. Zone 0 = just below / above the middle. |
| **ADX** | ADX 14 (Wilder) at least 25 and +DI / −DI in the signal direction (Seller9 V17). |
| **CCI** | CCI 14 above +50 for a long, below −50 for a short. |
| **T-LINE** | Your own trend lines: a long only after the "TMS BUY" line is broken, a short only after "TMS SELL" is broken (by candle close or price). No line drawn = pass. |
| **2/8 TREND** | EMA 2 / EMA 8 on D1, last closed day: green = buyer, red = seller, blue = confused (no trade). Seller9's AutoBuySell / Buyer-Seller step. |
| **STRENGTH** | Currency strength (Hanover style, own maths): the currency you buy must be at least 10 points stronger than the one you sell (0–100 scale). Optional: base at least 60 and quote at most 40. |
| **HOURS** | Only inside your trading hours (server time, e.g. 07:00–11:00, 13:00–17:00). Also blocks auto trading outside the hours. |

### Exit rules

One exit rule drives the exit warning, the tracker and the trade manager, always checked on the **closed** candle:

- **Big E** (default) — green goes flat (slope below 1 after a move), hooks over (slope turns against the trade) or crosses back over red.
- **Cross** — green crosses back over red.
- **Color** — the candle changes color.
- **5 EMA** — the candle closes back over the 5 EMA.

With an open trade on a pair (manual or from the suite), an orange **EXIT** badge appears in the monitor and you get an exit-warning alert once per candle.

## 🖥️ Dashboard & chart

**Layout** — 28-pair TMS monitor on the left, cards on the right (best setup, Big E rule check, pair inspector, signal tracker, currency strength), filter bar on top, live ticker at the bottom. The layout adapts to the chart size (2 columns × 3 rows of cards on big charts, two blocks of 14 pairs on small ones) — nothing overlaps or gets cut off.

**Header** — animated logo (green and red TDI lines crossing); trigger-timeframe tabs **M5 M15 M30 H1 H4 D1** to switch the signal timeframe live (the suite also shows the timeframe below and above, the choice is saved per chart); LIVE dot, server time and cross mode; link buttons and **X** to fold the suite into a small draggable pill.

**TMS monitor columns**

| Column | What it shows |
|---|---|
| **PAIR** | Blue = spread OK, grey = too wide. Dot = open trade on the pair; small line = trend lines drawn (green / red when broken). The row pulses on a STRONG signal. Click = inspect. |
| **SPR** | Spread in pips, red above the maximum. |
| **ADR 5d** | Average daily range of the last 5 days, with a bar for the % used today. |
| **HEIKEN ASHI MN W1 D1 H4 H1** | Current candle color on the 5 big timeframes; a ring = color changed on this candle. Click = open that chart. |
| **TDI MN W1 D1 H4 H1** | Green above / below red, arrow = direction of the green line, ring = cross on this candle. |
| **B1 / B0** | Green over / under red on the last closed (B1) and live (B0) candle of the trigger timeframe. |
| **SLOPE 1 / 0** | Change of the green line per bar, one decimal. Bright = strong (4+), normal = minimum (2), grey = too flat. |
| **ANG** | The Big E clock — the green line as a clock hand; yellow hand = flat. |
| **CDL** | Candle number of the current color: 1 and 2 are entry candles, 3+ = too late. |
| **EMA** | Candle close crossing the 5 EMA (like arbinka's HA / 5-EMA column). |
| **STOCH** | Stochastic value as a bar with dots at 20 / 80, green rising / red falling. |
| **32-50-68** | Where green and red sit between 0 and 100. |
| **TMA ZONE** | Price position inside the TMA channel with the long / short pullback zones. |
| **D1 2/8** | The 2/8 daily trend of the last 5 days. |
| **STR gap** | Strength of base minus quote currency (0–100 scale). |
| **LOWER** | TDI side and slope one timeframe below the trigger (the post #408 wish). |
| **TMS SIGNAL** | The signal state, plus the EXIT badge for open trades. |
| **TRADE B S C** | Buy, sell, close the suite trades of the pair — each needs a second click within 3 seconds. |

A **SORT** button switches between A–Z and SIGNAL (STRONG first, then BUY / SELL, BOUNCE, then the TMS score).

**The cards**

- **Best setup now** — the pair with the highest TMS score: state, candle number, slope, clock position, COUNTER TREND tag, TDI chips for all timeframes, an animated score gauge, entry price, Big E stop (high / low of the last 2 candles + offset), ATR, stochastic and currency strength. **TMS score 0–100:** 25 slope, 10 candle 1 (7 candle 2), 20 strength gap, 10 higher-timeframe TDI, 10 stochastic, 10 candle beyond the 5 EMA, 5 TMA side, 10 room to the 68 / 32 level.
- **Big E rule check** — 14 animated checks for the selected pair: cross · candle 1 or 2 · angle · stochastic · not stretched · currency strength · TMA pullback zone · higher timeframe · 2/8 daily trend · candle beyond the 5 EMA · ADX / CCI · trend line · spread / ADR / hours · lower timeframe. Green = OK, red = a core rule is missing, yellow = warning.
- **Pair inspector** — CHART (opens the pair with your "TMS" template), 4 CHARTS (lower, trigger, higher timeframe and D1 at once), + LINES / DEL LINES, BUY / SELL. Heiken Ashi chart with the yellow 5 EMA, TMA channel, trend lines, TDI-cross markers and candle numbers, plus the full TDI window.
- **Signal tracker** — follows every new BUY / STRONG / BOUNCE signal in virtual pips (spread included) until EXIT, STOP or END, saved per account for 7 days, plus your own trades of today, limit status and the alert log. It shows what the signals did since you started the EA — not a trade history and not a promise.
- **Currency strength** — the 8 currencies ranked on a 0–100 scale with momentum arrows (position of the close inside the range of the last 20 bars, averaged over the 7 pairs of each currency), plus the trigger-candle countdown and entry-window / trading-hours status.

**Comfort** — hover boxes explain every cell, chip and button (can be switched off). While the suite is open, chart scrolling and scales are paused under it and restored when you close it; if a template reload deletes the suite, it rebuilds itself within a second.

## 🔔 Alerts

- Popup, sound, push notification and e-mail (each on / off).
- Level: STRONG only / BUY and STRONG (default) / everything incl. BOUNCE.
- Text: state, pair, timeframe, candle number, slope, price.
- Exit warnings for open trades and trend-line break alerts.
- Once per candle and direction — switching a filter or the trigger timeframe does not cause an alert storm.

## 💼 Trading & trade manager

Auto trading is **OFF by default**. The suite is a monitor first — like Big E traded: look, check, click.

- **Manual trading** — B / S / C in every row and BUY / SELL in the inspector, always with a confirming second click.
- **Auto trading** — opens a trade on every new signal of the chosen level (STRONG by default); one position per pair and direction, a max-trades cap for the whole suite, an opposite signal closes the old trade first, no orders while the market is closed or outside your hours (HOURS filter on).
- **Stop loss** — Big E (high / low of the last 2 candles + offset), last fractal + offset, ATR × multiplier, or none.
- **Take profit** — none (exit by the TDI, Big E style), ATR × multiplier, or risk-reward × stop distance.
- **Counter trend** — signals against the 2/8 daily trend get their own take-profit multiplier and lot factor.
- **Lot size** — fixed lots or risk % of the balance.
- **Exit by the exit rule** — closes the trade when the rule fires on a candle that closed after the entry.
- **Break even**, **partial close at N R** (then stop to break even), **candlestick trailing stop** (Seller9 / Hopwood), **jumping stop**.
- **Hidden SL / TP** — the EA watches the levels itself; the broker only gets an optional emergency stop further away.
- **Friday close** and **daily limits** for new trades, winners and losers — for all pairs and per pair.
- **Magic number** — the suite only manages its own trades; exit warnings are shown for all trades on the pair.

## ⚙️ Key inputs

| Group | What you can set |
|---|---|
| **Signal** | Trigger timeframe, TDI cross on closed (default) or live candle, enter only on candle 1..N (2), minimum slope (2.0) and strong slope (4.0), bounce trades and bounce gap (2.0). |
| **Filters** | One start switch per filter plus its settings: zone levels (68 / 32), max ADR used (80 %), max spread (3 pips), window minutes (20), news minutes (30), TMA middle (56) / ATR (100) / band (2.0) / zone (50 %), ADX (14, min 25), CCI (14, level 50), trend-line break mode, 2/8 EMAs (2 / 8), strength timeframe, bars (20), gap (10) and thresholds, trading hours. |
| **TDI, candles, EMA, stochastic, ADR** | RSI period (13) and price, green (2), red (7), band / base line (34), candle type, 5 EMA period (5), shift (2), method and price, stochastic 8 / 3 / 3, ADR days (5). |
| **Exit** | Exit rule (Big E / cross / color / 5 EMA) and flat level (1.0). |
| **Alerts & tracker** | Tracker on / off, alert level, popup, sound, push, e-mail, exit warnings. |
| **Trading** | Buttons on / off, auto trading and level, lots (0.01), risk %, stop mode and offset (2 pips), ATR stop multiplier (1.5), take-profit mode and multiplier (2.0), exit by rule, candlestick trailing (2 candles, start 10 pips), break even (15 pips), max trades (5), counter-trend multipliers, partial close, jumping stop, hidden SL / TP with emergency stop (25 pips), Friday close hour, magic number, slippage (3 pips). |
| **Limits** | Max trades / winners / losers per day, for all pairs and per pair (0 = off). |
| **Symbols** | Pairs to show (empty = all 28), automatic or manual prefix / suffix. |
| **Display** | Click action on a pair, template for opened charts ("TMS"), refresh interval (1000 ms), pill position, tooltips on / off. |

## 🛠️ Installation

1. Open `File → Open Data Folder`. **MT5:** copy `TL TMS Suite Pro.ex5` to `MQL5 → Experts`. **MT4:** copy `TL TMS Suite Pro.ex4` to `MQL4 → Experts`. Refresh the Navigator.
2. Drag the EA onto **one** chart (any symbol) and maximise it. The chart timeframe becomes the trigger timeframe at start.
3. Tick **Allow DLL imports** only for the link buttons (they open your browser). For auto trading, also allow algo trading.
4. First start: the history of 28 pairs × 8 timeframes is loaded (progress bar). No indicator files are needed.

**Tips**

- Save your TMS chart layout as a template named **TMS** — every chart the suite opens uses it.
- Trend lines: rename any trend line or horizontal line on a chart of the pair to exactly **TMS BUY** or **TMS SELL** — or use **+ LINES**. The suite reads them every few seconds.
- Fewer pairs = a calmer screen: use the input "pairs to show".
- More filters ON = fewer but stronger signals. Start with the defaults, then switch filters and watch the BLOCKED reasons.
- Hidden SL / TP needs the terminal to stay online — keep the emergency stop on.

## 🚀 What's better than the original tools

**Compared with arbinka's monitor / TmsDash**

- The timeframe below the trigger as its own column — promised in post #408, never released.
- No indicator files needed — everything is calculated inside the EA (the originals needed exactly named "TDI Red Green" and "Heiken Ashi" files).
- The candle number (1, 2, 3+), the Big E clock, and the slope with decimals.
- Stochastic column, TDI zone 32-50-68, spread, ADR with % used today, TMA zone, 2/8 trend and currency strength.
- MN added (Heiken Ashi + TDI on MN W1 D1 H4 H1), push alerts back, plus exit warnings.
- Broker prefix / suffix detected automatically; 28 pairs × 8 timeframes on one chart; MT4 and MT5.

**Compared with Seller9's TMS EA (V19 / V22)**

- All 28 pairs on one chart — no one-chart-per-pair setup and no separate VB6 dashboard program.
- Filters switch with one click instead of editing dozens of inputs, and you see **why** there is no trade.
- Currency strength calculated internally — no external "Recent Strength" indicator.
- Trend lines on any chart of the pair, with a break alert; partial close at N R and per-pair limits.
- Fixed: the dynamic TDI "flicker" (closed candle by default), a TDI exit can no longer close a trade on its entry candle, an opposite signal closes the old trade first, no orders while the market is closed, and the old thread bugs (zone multiplier, slope colors, double orders, fractal stop errors) — rebuilt from the rules and the V19 manual.

**New in this suite**

- The 14-line Big E rule check, BOUNCE detection, the pair inspector, the signal tracker, the TMS score ranking and COUNTER TREND marking.
- TMA zone and strength-filter defaults chosen from historical H1 data across the 28 pairs.

## 🙏 Credits

This suite would not exist without the work of many traders and coders. Thank you all.

- **eelfranz (Big E, RIP)** — creator of [Trading Made Simple](https://www.forexfactory.com/thread/291622-trading-made-simple) (thread 291622), the biggest system thread on Forex Factory. Heiken Ashi, the TDI for entries and exits, the stochastic as confirmation, few rules — and a lot of patience to teach it. Every rule in this suite comes from his posts.
- **Dean Malone (CompassFX)** — inventor of the Traders Dynamic Index and the Synergy Average Price Bars that TMS is built on.
- **arbinka** — [Monitor for the TMS system](https://www.forexfactory.com/thread/303347-monitor-for-trading-made-simple-system) (thread 303347). His TmsMonitor (2011) and TmsDash (2017–2019) inspired the suite's monitor and layout.
- **Seller9** — the TMS EA versions V2 to V22 in [Trading Made Simple EA by Guess Whom](https://www.forexfactory.com/thread/292301-trading-made-simple-ea-by-guess-whom) (thread 292301). The trade manager and most filters follow his EA and his V19 manual.
- **Steve Hopwood** — started the EA thread with the first open-source TMS robot and its trade management module.
- **Numb3rs** — collected Big E's rules into the first rules PDF (thread 292285).
- **Xaphod** (TMS-Osc), **gspe** (Lawgirl's Trend Display), the Hanover currency strength idea and every coder who shared TMS tools.
- The members whose wishes in the arbinka thread are now built in: mahavir (#408 — a timeframe below the trigger; auto trading), jusiur (slope with decimals, bounce angle, candle countdown), thechad and jay280584 (stochastic column, push alerts, spread), Forethan (TDI crossing in the 32 / 68 area), aud (flat green line — the yellow clock hand), falanca (orders from the dash), and everyone who asked for improvements over the years.

Feedback and ideas are welcome — post them in the Forex Factory thread linked below.

## ⚠️ Notes

- Trading is risky. Test everything on a demo account first — as Big E said: study old charts and demo it until you have the confidence.
- The NEWS filter uses the MT5 economic calendar; in MT4 it always passes.
- Hidden stops only work while the terminal is running.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
