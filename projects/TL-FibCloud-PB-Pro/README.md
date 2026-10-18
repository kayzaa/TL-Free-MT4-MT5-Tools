<div align="center">

# ⚡ TL FibCloud PB Pro

**Automated Fibonacci-cloud pullbacks — EA + indicator with cloud-touch and ambiguity filters.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_FibCloud_PB_Pro_dashboard.png" alt="TL FibCloud PB Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL FibCloud PB Pro EA.ex4`](MT4/TL%20FibCloud%20PB%20Pro%20EA.ex4) |
| **MT4** | [`TL FibCloud PB Pro Indicator.ex4`](MT4/TL%20FibCloud%20PB%20Pro%20Indicator.ex4) |
| **MT5** | [`TL FibCloud PB Pro EA.ex5`](MT5/TL%20FibCloud%20PB%20Pro%20EA.ex5) |
| **MT5** | [`TL FibCloud PB Pro Indicator.ex5`](MT5/TL%20FibCloud%20PB%20Pro%20Indicator.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **KK / Sagat1977's pullback system, automated** — the full entry / exit state machine from the Forex Factory post, as an EA for MT4 and MT5.
- **Self-contained** — the EA draws its own Fibonacci cloud and signals; the companion indicator is optional and never places orders.
- **Ambiguity filters** — strict cloud touch, double-sided box guard and dual WPR guard keep unclear bars from entering.
- **Reproducible defaults** — closed higher-timeframe cloud and closed-candle → next-open execution.
- **Complete order management** — broker-held stop, optional target, equity-based sizing, break-even and ATR trailing.
- **Animated Canvas panel** — 3D cloud ribbon, price/time-anchored signal pills, hover help and a coordinated chart theme.

## 🧠 Strategy rules

1. **Build the cloud.** Take the high / low range of *Fib Length* HTF bars (default 50). The 0.382 and 0.618 levels pass through the original Supertrend-style ratchet, so the cloud is more than two unfiltered Fib lines.
2. **Find the box trend.** The box uses the previous 50 completed HTF bars, excluding the current HTF candle. A chart candle's high above the box sets the bullish trend; its low below the box sets the bearish trend. Box dots are trend markers, **not** order instructions by themselves.
3. **Arm a pullback** in the trend direction when price reaches the cloud.
4. **Wait for the WPR cross** within *Pullback validity* (default 2 bars after the touch). Another valid touch refreshes the window.

| Signal | Condition |
|---|---|
| **BUY** | HIGH-series WPR crosses above −80 in an uptrend |
| **SELL** | LOW-series WPR crosses below −20 in a downtrend |
| **Exit long / short** | Opposite WPR signal; a trend flip also exits by default |

> WPR is calculated separately on the HIGH and LOW series (period 20 / slowing 1) — this is **not** the standard close-price iWPR. No new pullback entry happens on the same signal-processing bar as an exit.

### Default timing

- **Cloud HTF mode:** CLOSED. **Signal mode:** CLOSED CANDLE → NEXT OPEN.
- The previous closed chart candle is evaluated when the next candle starts. The marker's logical entry price is that next candle's open; a real order fills at the available bid / ask, with spread and possible slippage.
- Developing-HTF and live HIGH / LOW modes are available but provisional: the cloud, touch condition and combined signal can change before the close. There is no blanket non-repaint guarantee for live mode, and closed history can also change after broker history corrections or a changed calculation window.

### What was added / changed vs. the original

- MT4 and MT5 EA automation, using the same calculation source as the indicator.
- Closed HTF and next-open execution as defaults for reproducibility.
- **Strict cloud touch** (default ON): candle HIGH >= cloud lower edge **and** candle LOW <= cloud upper edge — a candle wholly beyond the cloud does not qualify. Turn `InpStrictTouch` off for the original one-sided touch test.
- **Double-sided box guard** (ON): a bar breaking both box edges keeps the prior box direction and cannot generate a pullback entry. With the guard off, high-break / BUY has deterministic priority (the original transient latch based on which tick arrived first is not reproduced).
- **Dual WPR guard** (ON): simultaneous BUY and SELL crossings cannot enter; existing positions can still exit on their opposite WPR signal.
- Developing-HTF recalculation begins at the affected HTF period boundary.
- Broker-held stop and optional target, equity-based risk sizing, lot cap, spread / ATR entry gate, break-even and closed-bar ATR trailing.
- No old entries on attachment, no delayed entry retry after a rejected bar, one own position per symbol / magic, and a netting-position occupancy guard.
- Animated Canvas panel with collapse / reopen, drag, hover help, symbol/time-anchored cloud and labels, object rebuilding and dark-theme healing.

## 🎯 Risk & order management

| Item | Default behaviour |
|---|---|
| **Initial SL** | 2 × ATR(14) (simple average of 14 true ranges), enlarged when broker stop / freeze distance and spread require it; prices aligned to the trade tick size |
| **Target** | 2 × the initial risk distance; `InpRR=0` disables it (broker SL and strategy exits stay active); no partial exits |
| **Position size** | 0.5 % of equity, max 1 lot; `InpRiskPct=0` for fixed lots (`InpLots=0.01`). Lots round **down** to the broker step; a lot below the broker minimum is skipped, not rounded up |
| **Break-even** | From +1 initial R (price break-even, not commission-inclusive) |
| **ATR trailing** | From +1.5 R, using the last closed candle's close ± 2 ATR; stops only tighten |
| **Spread limit** | 0.15 ATR; 0 disables it |

- Thresholds are checked on ticks; the trailing reference changes on bar close. Set the BE or trailing distance input to 0 to disable it.
- The original risk is saved per account and ticket, so a restart does not reinterpret an already trailed stop as the original risk. If that value is unavailable, strategy exits and the broker stop stay active, but R-based break-even / trailing are not reconstructed.
- Risk estimation does not include future commission, gaps or slippage.
- Session, margin and trade-permission checks run before every order. **AUTO OFF** blocks new orders while existing own trades stay managed. **CLOSE OWN TRADES** asks for confirmation and closes this symbol / magic only.
- On MT5 netting accounts any pre-existing position in the symbol blocks a new entry — do not mix several strategies on one netting position.
- The indicator's virtual state follows only its WPR / trend exits; it does not simulate the EA's SL, TP, BE or trailing, so real trades can close earlier.

## 🖥️ Dashboard & chart

| Panel block | Content |
|---|---|
| **BOX TREND** | Confirmed trend, cloud timeframe, closed / developing mode |
| **FIBONACCI CLOUD** | Last closed chart bar's cloud edges and the touch rule |
| **PULLBACK ENGINE** | HIGH / LOW WPR values, levels, armed side, validity and guards |
| **RISK / EXITS** | ATR, SL / TP settings, equity risk, BE / trailing thresholds |
| **CONTROL** | Own position count, floating P/L, symbol / magic, order status, AUTO ON/OFF, CLOSE OWN TRADES |

- The indicator shows a no-orders status instead of the trading controls.
- Drag the header to move the panel; **X** folds it into a pill, click the pill to reopen. Hover the blocks for explanations.
- On narrow charts the panel can use several columns — collapse it when you need more room.
- Objects rebuild periodically while the program is attached (a template that removes the program cannot be self-recovered).

**Chart style:** candle bodies and wicks in coordinated teal / coral, volume bars and OHLC clutter removed, softer price lines and scale colours. Cloud segments use a 20-layer 3D ribbon gradient with illuminated rims and a dark lower bevel. Entries appear as rounded, shaded Canvas pills anchored to price / time; exits as gold **EXIT BUY / EXIT SELL** pills. Signal spacing adapts to the visible chart range. The original chart settings are restored on removal, and `InpTheme=false` keeps your own chart theme. The 3D depth is decorative — use the reported upper / lower values for exact cloud boundaries.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| `InpTF` | Cloud timeframe; `PERIOD_CURRENT` follows the chart, a lower timeframe is promoted to the chart timeframe |
| `InpAutoTrade` | Enables automatic trading (default off — AUTO OFF still displays the strategy) |
| `InpStrictTouch` | Strict two-sided cloud touch (default on) |
| `InpRR` | Target as a multiple of the initial risk (0 = no target) |
| `InpRiskPct` / `InpLots` | Equity risk per trade, or fixed lots when risk is 0 |
| `InpTheme` | Apply the TL chart theme (false = keep your chart theme) |
| `InpInstance` | Separates chart objects and panel state when several tools run |
| Magic number | Give every independently managed instance its own value |

## 📊 Indicator buffers (new mapping, not KK's original numbers)

| Buffer | Content |
|---|---|
| 0 / 1 | PB BUY price / PB SELL price |
| 2 / 3 | Exit BUY / exit SELL |
| 4 | Trend (+1 / −1 / 0) |
| 5 / 6 | Cloud upper / cloud lower |
| 7 | Virtual position |

No event = `EMPTY_VALUE` for signal buffers; trend / position use 0 for neutral. In closed → next-open mode the event is emitted on the **new** bar (shift 0). When reading from an external EA, wait for valid history, ignore old startup signals and de-duplicate by bar time — or simply use the supplied EA for the matching built-in trading and risk management.

## 🛠️ Installation

1. In your terminal choose **File → Open Data Folder**.
2. Copy the files for your platform:
   - **MT5:** `TL FibCloud PB Pro EA.ex5` → **MQL5 → Experts**, `TL FibCloud PB Pro Indicator.ex5` → **MQL5 → Indicators**
   - **MT4:** `TL FibCloud PB Pro EA.ex4` → **MQL4 → Experts**, `TL FibCloud PB Pro Indicator.ex4` → **MQL4 → Indicators**
3. Refresh the Navigator and attach the EA to the symbol / timeframe you want to trade. Pick the cloud timeframe in `InpTF`.
4. For automatic trading, enable terminal **Algo Trading / AutoTrading** and the EA's trading permission, then set `InpAutoTrade=true` or press **AUTO ON**.
5. **Allow DLL imports** is needed only for the website buttons (shell32.dll) — the engine and chart functions do not use it. If your terminal blocks initialization because DLL imports are disabled, enable them for this tool; no extra DLL file is needed.
6. Use one EA instance per chart with its own magic number. The EA does not need the companion indicator; if both are attached, turn off one panel / cloud to avoid duplicate drawings.

## 🙏 Credits

- Pullback entry / exit logic: **KK / Sagat1977** — [Forex Factory post 15961504](https://www.forexfactory.com/thread/post/15961504#post15961504) (original: `KK_FibCloud_PB_MTF_Ind.mq5`, version 1.85)
- Cloud calculation: **TrendX_**'s Fibonacci Cloud MTF
- Adaptation, automation, Canvas interface and additions: **trader.lifestyle** — [website](https://trader.lifestyle)

## ⚠️ Notes

- **The MT4 build is compile-only** — MT4 runtime verification is still open. The optional indicator wrappers were compiled but not independently runtime-verified. A successful compile is not a runtime check.
- No performance or profitability promise is made. Test on demo and choose your own risk settings.
- **Feedback:** please include platform / build, broker, symbol (with suffix), chart timeframe, cloud timeframe, inputs, signal timestamp and the Experts / Journal messages.

## 🖼️ More screenshots

<img src="screenshots/TL_FibCloud_PB_Pro_panel.png" width="49%">
<img src="screenshots/TL_FibCloud_PB_Pro_pill.png" width="49%">

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
