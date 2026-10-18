<div align="center">

# ⚡ TL Replay Studio Pro

**Replay your closed trades on a dedicated replay chart or practise with virtual positions — never touches broker orders.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Replay_Studio_Pro_MT5.png" alt="TL Replay Studio Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Replay Studio Pro.ex4`](MT4/TL%20Replay%20Studio%20Pro.ex4) |
| **MT5** | [`TL Replay Studio Pro.ex5`](MT5/TL%20Replay%20Studio%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Replay your real closed trades** on a dedicated, fully rendered replay chart — cue any execution and play through it candle by candle.
- **Practice mode** with virtual positions, SL / TP and reward:risk — sharpen decisions without risking a cent.
- **Never touches broker orders** — no order execution at all. A utility, not a trading strategy, and no Strategy Tester needed.
- **Forward and reverse playback** from 0.25 to 100 bars per second, A/B looping, bookmarks, zoom and pan.
- **Honest data** — broker BID OHLC of closed candles only, no invented prices, no fake ticks.
- **Exports** — CSV of trades, virtual results and bookmarks, plus a BMP capture of the suite.

## 🧠 How it works

### Data & replay

- Uses the **current chart symbol** (exact broker suffix); the timeframe is selected in the EA inputs.
- Broker **BID OHLC** history, **closed candles only**. No invented prices.
- Latest **12,000** closed bars by default; configurable up to **100,000** bars.
- Optional **From / To** dates in **broker time**. If a long range exceeds MaxBars, the latest MaxBars within the range are used — check the displayed coverage dates.
- **Playback speeds** (forward and reverse): 0.25, 0.5, 1, 2, 5, 10, 25, 50 or 100 bars per real second — not tick-time multipliers. Rendering load may reduce the achieved rate; a delayed UI does not jump to an arbitrarily distant time.
- **Controls:** play / pause, first / last candle, single-step, draggable timeline, A/B looping, golden bookmarks, chart zoom, pan and return to the replay head.
- **Visuals:** animated logo, playback cursor glow, shaded candles, entry / exit pills, EMA 20, broker tick-volume histogram, crosshair OHLC info and price / time scales.
- **SESSION** shows 08:00 and 13:00 broker-time guides. These are not automatically converted London / New York sessions and do not adjust for DST.

> **Closed-bar replay.** It does not reconstruct real intrabar tick paths — animation decorates the UI and cursor, it does not pretend to be recorded tick movement. Future candles are not drawn. Standard third-party indicators are not hosted inside the custom Canvas chart; the underlying broker chart is separate.

### The three panels

**TRADES** — account history for the current symbol, plus optional imported CSV legs.
- Click an execution to cue 15 candles before its entry, then play through the trade. The trade supplies A/B bounds extending 15 candles beyond its exit; press **LOOP** to repeat.
- If an entry is outside the loaded coverage, change From / To and reload. UP / DOWN scroll the library.
- **BLIND** hides future exit prices and final results in the library / inspector. It does not hide known entry metadata or create a random challenge.
- **MT4** reads closed market orders from the terminal's currently loaded Account History — select *All History* there if older trades are missing. Pending / cancelled orders and currently open orders are not imported.
- **MT5** reconstructs closed execution legs by position ID, using a weighted entry price and pro-rata entry fees. Partial exits are separate legs; reversals close the old basis and open the remainder. Additional scale-ins change the weighted basis (this is not a FIFO view of every entry deal). Missing entry histories are skipped. Historical SL / TP modifications and every partial-entry timestamp are not reconstructed. Commission, fee and swap fields attached to deals are included in realized net results; separately booked balance charges are not allocated.

**PRACTICE** — one virtual position at a time.
- **BUY** opens at the visible bar-close bid plus the configured spread; **SELL** at bid. The first following bar can trigger SL or TP.
- Defaults: 0.10 lot label, 300 symbol-point stop, 2.0 reward/risk, 20 points fixed spread. Points are the symbol's `_Point` units, **not** universal forex pips — edit them in the inputs.
- Practice reports **points**, not estimated currency profit. The lot input is a journal label and does not scale the point result. No commission, swap or latency is simulated.

**Practice exit rules**
- Long exits use bid; short exits use bid plus the configured fixed spread.
- Stop gaps fill at the adverse bar open; target gaps fill at the target limit.
- If an OHLC candle hits both SL and TP without a decisive opening gap, **SL wins**.
- **CLOSE VIRTUAL POSITION** exits at the displayed bar close, with the applicable spread.
- Rewind rebuilds virtual outcomes; future entries disappear from current results.
- Placing / closing a virtual trade after rewinding discards later virtual entries and manual closes — this creates a new branch. There is no undo of discarded branches.

**SAVE SESSION / RESTORE** (Practice panel, on charts taller than 770 px) stores the replay cursor, virtual entries / manual closes, bookmarks, loop bounds, direction and speed.
- One local slot per symbol / timeframe, overwritten only when SAVE SESSION is pressed.
- Restore requires exactly the same loaded bar count, first / last bar timestamps and spread setting — use fixed From / To dates when resuming on another day.
- Restore replaces the current virtual session and pauses playback; export or save the current one first.
- **No autosave:** export / save before changing inputs, timeframe or symbol, or removing the EA. Reload is blocked while practice trades exist, so nothing is silently discarded — export / save and reattach to start a fresh dataset. Bookmarks are session-local unless saved.

Results cover loaded / imported closed trades — not deposits or floating equity. They are descriptive history, not a forecast.

## 🖥️ Dashboard & chart

| Key / action | What it does |
|---|---|
| Space | Play / pause |
| Left / Right | Previous / next candle |
| Home / End | First / last loaded candle |
| B / S / C | Virtual buy / sell / close |
| M | Add / remove bookmark |
| + / - | Change replay speed |
| H | Help |

- Click the chart first for keyboard focus. Drag the header to move the suite.
- **X** minimizes it and pauses playback; click its pill to reopen (it returns to the input position).
- **PAN** reviews older candles without moving the simulation clock.
- The suite recreates its bitmap if deleted. Chart scrolling is restored after dragging and when the EA is removed.
- While expanded, it hides the underlying MT5 chart (or masks its colours on MT4) so live prices never mix with the replay. Original chart visibility / colours return when minimized or removed.

## 📤 Exports & CSV import

- **CSV export:** currently visible closed historical legs, virtual results and bookmarks.
- **BMP:** saves the current rendered suite — a real Canvas capture.
- Both are saved in the terminal's `MQL4/Files` or `MQL5/Files` folder.

**Optional input CSV** — comma-separated ANSI / ASCII file in that same Files folder; set `InpTradeCSV` to its file name.
- Header and column order must be exactly: `id,symbol,direction,entry_time,exit_time,entry_price,exit_price,lots,net`
- Dates in broker time, format year.month.day hours:minutes:seconds (e.g. `2026.01.31 14:30:00`). `direction`: BUY or SELL. Decimal separator: dot.
- Only rows matching the exact chart symbol are imported. One row per **closed** execution leg. `net` is the final net in account currency, supplied by you.
- Invalid prices / volume / direction / dates are skipped. Avoid commas inside fields. An empty template is supplied.
- The journal export uses a different, documented output schema and is not directly an input file.
- Do not import trades already loaded from the account unless you want them counted twice — set `InpShowAccountTrades=false` when using an equivalent CSV instead.

## 🛠️ Installation

1. In the terminal choose `File → Open Data Folder`.
   - **MT5:** copy `TL Replay Studio Pro.ex5` into `MQL5 → Experts`.
   - **MT4:** copy `TL Replay Studio Pro.ex4` into `MQL4 → Experts` (see the build note below).
2. Refresh the Navigator, then attach the EA to the required symbol's **normal** chart.
3. Enable **Allow DLL imports** — the suite imports Windows `shell32.dll` for the external link buttons. There is no separately supplied DLL and no external web data feed. AutoTrading is not needed: the program has no order execution.
4. Maximize the chart — at least **1000 x 670** chart pixels (more height recommended). Hide the Strategy Tester and Toolbox if they take too much space.
5. Set timeframe / date range, wait for broker history, then press **PLAY**. If data is unavailable, open that symbol / timeframe, let it load, then **Reload**.

## ⚠️ Notes

- **Build status:** MT5 compiled without errors or warnings, with runtime and Canvas interaction checked. MT4 compiled without errors or warnings, but its **runtime is not verified** — treat the EX4 as untested.
- No live order management, real tick playback, news / calendar feed or multi-symbol account reconstruction in one chart — use one chart per symbol.
- Broker history availability limits the replay. It cannot recover missing ticks, historical spread changes, missing executions or deleted account records.
- Session persistence keeps the practice state described above; it does not archive a copy of broker candles or all UI preferences.
- No strategy or profitability claims.

## 🔗 Links

- [RoboForex partner link](https://my.roboforex.com/en/?a=jjlu)
- Created with [IndicatorGenius.com](https://indicatorgenius.com/)

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
