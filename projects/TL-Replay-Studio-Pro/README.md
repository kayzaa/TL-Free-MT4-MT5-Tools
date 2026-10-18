<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
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

## Overview

Created with IndicatorGenius.com

## Build Status

MT5: compiled without errors or warnings; runtime and Canvas interaction tested. MT4: compiled without errors or warnings. LOCAL RUNTIME NOT VERIFIED: the installed MT4 build 1492 stalls before even a minimal probe EA initializes. The EX4 is supplied in a clearly labelled folder. Do not describe it as runtime-tested.

## What This Suite Does

Review historical closed account trades on a dedicated, fully rendered replay chart, or practice your own decisions with virtual positions. The EA never sends, changes, or closes broker orders. It is a utility attached to an ordinary chart, not a trading strategy. You do not need the Strategy Tester to replay bars.

## Data And Replay

- Current chart symbol, with exact broker suffix. Timeframe is selected in EA inputs.
- Broker BID OHLC history; only closed candles are loaded. No invented prices.
- Latest 12,000 closed bars by default. Maximum configurable range: 100,000 bars.
- Optional From/To dates in BROKER TIME. If a long range exceeds MaxBars, the latest MaxBars within the selected range are used. Check the displayed coverage dates.
- Forward and reverse playback: 0.25, 0.5, 1, 2, 5, 10, 25, 50 or 100 bars per second. These are bars per real second, not tick-time multipliers. Rendering load may reduce the achieved rate; a delayed UI does not skip to an arbitrarily distant wall time.
- Play/pause, first/last candle, single-step, draggable timeline, A/B looping.
- Golden bookmarks, chart zoom, pan and return to replay head.
- Animated logo, playback cursor glow, shaded candles, entry/exit pills, EMA 20, broker tick-volume histogram, crosshair OHLC information and price/time scales.
- SESSION displays 08:00 and 13:00 broker-time guides. These are not automatically converted London/New York exchange sessions and do not adjust for DST.

IMPORTANT: This is CLOSED-BAR REPLAY. It does not reconstruct real intrabar tick paths. Animation decorates the UI and cursor; it does not pretend to be recorded tick movement. Future candles are not drawn. Standard third-party indicators are not hosted inside this custom Canvas chart. The underlying broker chart is separate.

## Installation

- In the target terminal choose File > Open Data Folder.
- MT5: copy MT5/Experts/TL Replay Studio Pro.ex5 into MQL5/Experts. MT4: copy the EX4 from MT4_RUNTIME_UNVERIFIED/Experts into MQL4/Experts.
- Refresh Navigator, then attach the EA to the required symbol's NORMAL chart.
- Enable Allow DLL imports: the suite imports Windows shell32.dll for the external link buttons. There is no separately supplied DLL and no external web data feed. AutoTrading is not needed to send trades: this program has no order execution.
- Maximize the chart. Use at least 1000 x 670 chart pixels (more height recommended). Hide the Strategy Tester and Toolbox if they consume too much chart space.
- Set timeframe/date range, wait for broker history, then press PLAY. If data is unavailable, open that symbol/timeframe, allow it to load, then Reload.

## The Three Panels

TRADES: account history for the current symbol, plus optional imported CSV legs. Click an execution to cue 15 candles before its entry. Play through the trade. The trade supplies A/B bounds extending 15 candles beyond its exit; press LOOP to repeat. If its entry is outside loaded coverage, change From/To and reload. UP/DOWN scroll the library. BLIND hides future exit prices and final results in the library/inspector. It does not hide known entry metadata or create a random challenge.

MT4 reads closed market orders from the terminal's currently loaded Account History. Select All History there if older trades are missing. Pending/cancelled orders and currently open orders are not imported.

MT5 reconstructs closed execution legs by position ID, using weighted entry price and pro-rata entry fees. Partial exits are separate legs; reversals close the old basis and open the remainder. Additional scale-ins change the weighted basis; this is not a FIFO visualization of every entry deal. Missing entry histories are skipped. Broker historical SL/TP modifications and every partial-entry timestamp are not reconstructed. Commission, fee and swap fields attached to deals are included in realized net results; separately booked balance charges are not allocated.

PRACTICE: one virtual position at a time. BUY opens at the visible bar-close bid plus the configured spread; SELL at bid. The first subsequent bar can trigger SL or TP. Defaults: 0.10 lot label, 300 SYMBOL POINTS stop, 2.0 reward/risk, 20 points fixed spread. Points are the symbol's _Point units, NOT universally forex pips. Edit these in inputs. Practice reports POINTS, not estimated currency profit. The lot input is a journal label; it does not scale the point result. No commission, swap or latency is simulated.

Exit rules:
- Long exits use bid, short exits use bid plus the configured fixed spread.
- Stop gaps fill at the adverse bar open; target gaps fill at the target limit.
- If an OHLC candle hits both SL and TP without a decisive opening gap, SL wins.
- CLOSE VIRTUAL POSITION exits at the displayed bar close, with the applicable spread.
- Rewind rebuilds virtual outcomes. Future entries disappear from current results.
- Placing/closing a virtual trade after rewinding discards later virtual entries and later manual closes: this creates a new branch. There is no undo of discarded branches.

## Save Session / Restore (Practice panel on charts taller than 770 px): stores replay

cursor, virtual entries/manual closes, bookmarks, loop bounds, direction and speed. One local slot per symbol/timeframe, overwritten only when SAVE SESSION is pressed. Restore requires exactly the same loaded bar count, first/last bar timestamps and spread setting. Use fixed From/To dates when resuming on another day. Restore replaces the current virtual session and pauses playback; export or save the current one first. No autosave: export/save before changing inputs, timeframe, symbol or removing the EA. Reload is blocked while practice trades exist, to prevent silently discarding them; export/save and reattach to start a fresh dataset. Bookmarks are session-local unless saved.

This covers loaded/imported closed trades, not deposits or floating account equity. The displayed results are descriptive history, not a forecast or strategy backtest.

## Keyboard And Mouse

Space: play/pause. Left/Right: previous/next candle. Home/End: first/last loaded candle. B/S/C: virtual buy/sell/close. M: add/remove bookmark. +/-: change replay speed. H: help. Click the chart first for keyboard focus. Drag the header to move the suite. X minimizes it and pauses playback. Click its pill to reopen. Reopening returns it to the input position. PAN reviews older candles without moving the simulation clock. The suite recreates its bitmap if deleted. Chart scrolling is restored after dragging and when the EA is removed. While expanded, it hides the underlying MT5 chart (or masks its colors on MT4) to avoid mixing live prices with replay. Original chart visibility/colors are restored when minimized or removed.

## Exports And CSV Import

CSV exports currently visible closed historical legs, virtual results and bookmarks. BMP saves the current rendered suite. Both are saved in the terminal's MQL4/Files or MQL5/Files folder. BMP is a real Canvas capture, not a generated promotional mockup.

Optional input CSV: comma-separated ANSI/ASCII file inside that same Files folder. Set InpTradeCSV to its file name. Header and column order must be exactly: id,symbol,direction,entry_time,exit_time,entry_price,exit_price,lots,net Dates: YYYY.MM.DD HH:MM:SS in broker time. direction: BUY or SELL. Decimal separator: dot. Only rows matching the exact chart symbol are imported. One row per CLOSED execution leg. net is the final net in account currency, supplied by you. Invalid prices/volume/ direction/dates are skipped. Avoid commas inside fields. The empty template is supplied. The journal export uses a different, documented output schema and is not directly an input file. Do not import trades already loaded from the account unless you want them counted twice; set InpShowAccountTrades=false when using an equivalent CSV instead.

## Limits / Practical Notes

- No live order management, real tick playback, news/calendar feed or multi-symbol account reconstruction in one chart. Use one chart per symbol.
- Broker history availability limits the replay. It cannot recover missing ticks, historical spread changes, missing executions or deleted account records.
- Session persistence preserves the practice inputs described above; it does not archive an immutable copy of broker candles or all UI preferences.
- No strategy/profitability claims. No live orders were used for testing.

Links Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4> YouTube: <https://www.youtube.com/@traderlifestyle> WhatsApp: <https://wa.me/18585003724> RoboForex partner link: <https://my.roboforex.com/en/?a=jjlu> Created with: <https://indicatorgenius.com/>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
