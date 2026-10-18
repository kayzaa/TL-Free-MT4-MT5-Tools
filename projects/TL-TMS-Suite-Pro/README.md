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

## Overview

MT4 + MT5 · one EA · 28 pairs · monitor, signals, rule check, alerts, tracker, trade manager · no extra indicators needed · free · no lock · no expiry

The full suite on a 1080p chart: 28-pair TMS monitor on the left, best setup, Big E rule check, pair inspector (Heiken Ashi + TMA channel + TDI), signal tracker and currency strength on the right, filter bar on top, live ticker at the bottom.

## Contents

- In memory of Big E - and the people this suite stands on
- What is better than the original tools (the short version)
- The Big E rules the suite checks
- The screen - every part explained
- The TMS monitor - every column explained
- The signal states
- The 19 filters
- The cards: best setup, rule check, inspector, tracker, currency strength
- Exit rules and exit warnings
- Alerts
- Trading: buttons, auto trading and the trade manager
- All inputs, one by one
- Installation and tips

## 1. In Memory Of Big E - And The People This Suite Stands On

This suite would not exist without the work of many traders and coders. Thank you all.

- eelfranz (Big E, RIP) - the creator of Trading Made Simple (<https://www.forexfactory.com/thread/291622-trading-made-simple)> (thread 291622), the biggest system thread on Forex Factory. His idea was simple on purpose: Heiken Ashi candles, the TDI for entries and exits, the stochastic only as confirmation, any timeframe, few rules - and a lot of patience to teach it. Every rule in this suite comes from his posts.
- Dean Malone (CompassFX) - the inventor of the Traders Dynamic Index and the Synergy Average Price Bars that TMS is built on.
- arbinka - Monitor for the TMS system (<https://www.forexfactory.com/thread/303347-monitor-for-trading-made-simple-system)> (thread 303347). His TmsMonitor (2011) and TmsDash (2017-2019) showed Heiken Ashi + TDI over many pairs and timeframes with the slope, the HA x 5 EMA cross and B / S / C buttons. The suite's monitor is built on his idea and layout.
- Seller9 - the TMS EA versions V2 to V22 in the thread Trading Made Simple EA by Guess Whom (<https://www.forexfactory.com/thread/292301-trading-made-simple-ea-by-guess-whom)> (thread 292301). Static / dynamic TDI cross, minimum slope, the 32 / 68 range, the candle patterns, the TMA zone, ADX / CCI, the 2/8 trend, trend lines, trade window, candlestick trailing stop, hidden stops, jumping stop, win / loss limits and many exits - the trade manager and most filters of this suite follow his EA and his V19 manual.
- Steve Hopwood - started the EA thread with the first TMS robot (open source) and its trade management module.
- Numb3rs - collected Big E's rules into the first rules PDF (thread 292285).
- Xaphod (TMS-Osc), gspe (Lawgirl's Trend Display), the Hanover currency strength idea and every coder who shared TMS tools.
- The members whose wishes in the arbinka thread are now built in: mahavir (#408 - a timeframe below the trigger), jusiur (slope with decimals, bounce angle, candle countdown), thechad and jay280584 (stochastic column, push alerts, spread), Forethan (TDI crossing in the 32 / 68 area), aud (flat green line - the yellow clock hand), falanca (orders from the dash), mahavir (auto trading), and all the others who asked for improvements over the years.

## 2. What Is Better Than The Original Tools

Compared with the arbinka monitor / TmsDash

- NEW: the timeframe below the trigger - promised in post #408, never released. Now a column of its own.
- NEW: no indicator files needed. The originals needed "TDI Red Green" and "Heiken Ashi" with exactly the right names - wrong files gave wrong signals (many questions in the thread). Everything is calculated inside the EA.
- NEW: the candle number (candle 1, 2, 3+) - Big E's most important rule, missing in both originals.
- NEW: the Big E clock - the slope as a clock hand (12-2 / 4-6 o'clock), plus the slope with decimals instead of whole numbers (values below 1 were shown as 0).
- NEW: stochastic column, TDI zone 32-50-68, spread, ADR with % used today, TMA zone, 2/8 trend, currency strength - many of them asked for in the thread.
- NEW: MN added: Heiken Ashi + TDI on MN W1 D1 H4 H1 (TmsDash had W1 D1 H4 H1).
- NEW: push alerts are back (missing in TmsDash 1.03), plus an exit warning for open trades.
- NEW: broker prefix / suffix detected automatically (the original needed a special version).
- 28 pairs x 8 timeframes on one chart - the original needed two charts for 28 pairs because of the CPU load.
- Nothing overlaps: the layout adapts to the chart size (two blocks of 14 pairs on small charts).
- MT4 and MT5 (the originals were MT4 .ex4 only).

Compared with the Seller9 TMS EA (V19 / V22)

- NEW: all 28 pairs on one chart - the original needed one chart per pair plus a separate VB6 dashboard program (.exe, DLL registration, folder C:\TMS).
- NEW: filters switch on / off with one click in the filter bar - no more 40 inputs to change and re-attach. Seller9 himself wrote that there were enough settings to confuse everybody.
- NEW: you see why there is no trade: BLOCKED + the name of the filter, and the 14-line rule check.
- NEW: the currency strength is calculated inside the suite - the original Hanover module needed an external "Recent Strength" indicator, files and a template.
- NEW: trend lines work on any chart of the pair (name them "TMS BUY" / "TMS SELL") or with one click on + LINES, plus a break alert.
- NEW: partial close at N R then break even, and limits per pair and for all pairs.
- Fixed: the dynamic TDI "flicker" (Seller9 #698) - the default is the closed candle; a cross on the live candle is only shown as FORMING.
- Fixed: a TDI exit can no longer close a trade on the same candle it was opened - the exit rule only counts after a candle closed.
- Fixed: an opposite signal closes the old trade first (no hedge by accident). No orders while the market is closed.
- Fixed: the old bugs listed in the thread (zone multiplier, slope colors, double orders on slow brokers, fractal stop errors) - everything was rebuilt from the rules and the V19 manual.
- MT4 and MT5, source quality checked: every value of the engine was recalculated independently and matches.

New in this suite (in no original tool)

- The Big E rule check with 14 animated checks for the selected pair.
- The BOUNCE trade detection (Big E's bounce off red).
- The pair inspector: Heiken Ashi chart with the 5 EMA, the TMA channel, your trend lines, candle numbers and every TDI cross, plus the full TDI window.
- The signal tracker in virtual pips with the Big E stop and the exit rule.
- The TMS score to rank the setups, STRONG signals sorted to the top.
- COUNTER TREND marking with its own take profit and lot factor.
- Data-based defaults: the TMA zone settings and the strength filter were chosen from a study over 28 pairs and about 1.5 years of H1 data.

## 3. The Big E Rules The Suite Checks

- Green crosses red on the TDI - a real cross, not just a touch ("a setup is NOT green touching red").
- Enter at the beginning of candle 1 or 2 of the new Heiken Ashi color. Candle 3 or more: too late, find another trade.
- Angle: green at 12-2 o'clock for a long, 4-6 o'clock for a short. 2-4 o'clock is weak - pass.
- Bounce: green comes close to red and turns away again - lower odds, but it works.
- Before you click, look at the basics: does the stochastic confirm, how close are you to 68 / 32, the previous high / low, the trend, small candles, consolidation.
- Exit: green goes flat, hooks over or makes a check mark reversal.

## Tdi (Traders Dynamic Index, as in "Tdi Red Green"): RSI 13 of the close, green = SMA 2 of the RSI, red = SMA 7, yellow market base line = SMA 34, volatility band = base line +/- 1.6185 standard deviations (34), levels 32 / 50 / 68.

Candles: Heiken Ashi (= Average Price Bars), optional Heiken Ashi Smoothed or normal candles. Stochastic 8,3,3 (only direction). 5 EMA of the typical price, shift 2 (Big E used shift 3 - both possible).

## 4. The Screen - Every Part Explained

Header

- Animated logo (green and red TDI lines crossing) and the title. Hover = a short summary of TMS, click = opens the TMS thread.
- Subtitle: pairs loaded, trigger timeframe, the timeframe below, the TDI settings and the candle type.
- TRIGGER TIMEFRAME tabs M5 M15 M30 H1 H4 D1 - switch the signal timeframe live. The suite then also shows the timeframe below and above it. At start the chart timeframe is used. The choice is saved per chart.
- LIVE dot, server time and the cross mode (closed / live candle).
- Buttons RoboForex, WhatsApp, YouTube, FOREX FACTORY (my free tools thread) and X (folds the suite into a small pill).

Filter bar - 19 filter chips (see chapter 7). Green dot + cyan = ON. Click to switch. Hover = the exact rule. On the left: how many filters are on. On the right (when there is room): exit rule, candle limit and slope levels. TMS monitor - left side, one row per pair (chapter 5). Cards - right side (chapter 8). The layout adapts: 2 columns x 3 rows on big charts, fewer cards on small charts. Nothing is ever cut off. Ticker - bottom line: every pair with bid, change since today's open and its current entry signal, scrolling. Pill - after X: a small bar with the best signal, click to open again, drag it anywhere. The chart works normally while the suite is closed. Hover boxes - every cell, value, chip and button has an English explanation (can be switched off). While open - chart scrolling, the OHLC line, price and date scale are paused under the suite and restored when you close or remove it. If a template reload deletes the suite, it rebuilds itself within a second.

## 5. The TMS Monitor - Every Column Explained

- PAIR - blue = spread ok, grey = spread too wide. Small dot top right = you have an open trade on the pair (any magic). Small line bottom left = you drew trend lines (cyan, green when the BUY line is broken, red when the SELL line is broken). The row pulses when a STRONG signal is on. Click = show the pair in the inspector (or open the chart, input).
- SPR - spread in pips, red above the maximum.
- ADR 5d - average daily range of the last 5 days in pips. The thin bar below = % of the ADR already used today (yellow above the ADR filter level).
- HEIKEN ASHI MN W1 D1 H4 H1 - color of the current candle on the 5 big timeframes. A ring = the color changed on this candle. Click = opens that pair on that timeframe.
- TDI MN W1 D1 H4 H1 - green = green line above red, red = below. The small arrow = direction of the green line right now. A ring = green crossed red on this candle.
- TRIGGER (your trigger timeframe, cyan band over the columns):

- B1 B0 - green over / under red on the last closed candle (B1) and the live candle (B0). A ring marks the candle where the cross happened.
- SLOPE 1 / 0 - change of the green line per bar on B1 and B0 (RSI points, one decimal). Bright = strong (4+), normal = at least the minimum (2), grey = too flat.
- ANG - the Big E clock: the green line as a clock hand. 12-2 o'clock long / 4-6 o'clock short = good momentum, yellow hand = flat.
- CDL - candle number of the current color: 1 and 2 are the entry candles (colored), 3+ = too late (grey).
- EMA - candle close crossing the 5 EMA: bright arrow = crossed on this or the last candle, a ring = on this candle, purple = crossed earlier (side only) - like arbinka's HA / 5-EMA column.
- STOCH - stochastic value as a bar with dots at 20 / 80, green = rising, red = falling, the number above.
- 32-50-68 - where green (big dot) and red (small dot) are between 0 and 100 with the 32 / 50 / 68 levels.
- TMA ZONE - where the price is inside the TMA channel: left end = lower band, right end = upper band, yellow line = middle, green / red area = the pullback zone for longs / shorts. The dot glows cyan when the price is in the zone of the signal side.
- D1 2/8 - the 2/8 daily trend of the last 5 days (green up, red down, blue confused). The tall bar = the last closed day (used by the filter), the right bar = today.
- STR gap - strength of the base minus the quote currency (0-100 scale). Green = gap of at least the filter value for a buy, red = for a sell.

- LOWER - TDI side (arrow) and slope one timeframe below the trigger (the #408 wish).
- TMS SIGNAL - the state (chapter 6). An orange EXIT badge appears when you have a trade on the pair and the exit rule fires (FLAT / HOOK / CROSS / COLOR / 5 EMA).
- TRADE B S C - buy, sell, close the suite trades of the pair. Each needs a second click within 3 seconds ("OK?").

SORT button: A-Z (like the arbinka dash) or SIGNAL (STRONG first, then BUY / SELL, BOUNCE, then the TMS score). Small charts: the monitor switches to two blocks of 14 pairs side by side.

## 6. The Signal States

- STRONG BUY / STRONG SELL (pulsing) - Big E entry + all active filters pass + slope 4 or more + the candle crossed the 5 EMA on candle 1-2 + the TDI of the higher timeframe agrees.
- BUY / SELL - Big E entry: green crossed red on the last 1-2 candles, the current candle has the new color, candle 1 or 2, all active filters pass.
- BOUNCE BUY / SELL - green stayed on one side for 3+ candles, came within 2 points of red and turned away again, fresh candle color, filters pass.
- BLOCKED - an entry pattern is there, but a filter says no. The cell shows which one ("BLOCK STOCH"). Switch the filter off if you want the trade anyway.
- LATE - same side, but candle 3 or more - Big E: find another trade.
- SETUP - green crossed red, but the candle color has not changed yet - wait for it.
- FORMING - the live candle is crossing right now. In closed candle mode the signal comes with the candle close (no flicker).
- WAIT - nothing.

Signals that are already there when you start the EA are shown, but not alerted, tracked or traded. Each signal fires once per candle and direction.

## 7. The 19 Filters

Click a chip to switch it. The start values come from the inputs, your clicks are saved per chart. A filter only blocks BUY / SELL / BOUNCE signals. ON at start: SLOPE, ZONE, STOCH, SPREAD, T-LINE, STRENGTH.

- SLOPE - green slope at the signal at least 2 RSI points per bar (12-2 / 4-6 o'clock).
- ZONE - no long when green is above 68, no short when green is below 32 (Seller9 V13).
- STOCH - stochastic 8,3,3 moves in the signal direction and is between 20 and 80.
- 5 EMA - the last closed candle closed above (long) / below (short) the 5 EMA shift 2 - the original setup candle of the 5-method.
- HTF TDI - green on the same side of red on the next higher timeframe.
- HTF HA - the candle color of the next higher timeframe agrees.
- MBL - green above (long) / below (short) the yellow market base line.
- PATTERN - Seller9's candle patterns (his post #2627): #1 = 3 opposite + 3 same color closed candles, #2 = 3 opposite + 1 same, #3 = 3 opposite + 2 same, and the current candle beyond its open.
- ADR - today used at most 80 % of the average daily range (room left to run).
- SPREAD - spread at most 3 pips.
- WINDOW - only in the first 20 minutes of the new trigger candle - like Big E looking at his charts when the new 4h candle opens (Seller9's Candle2TradeWindow).
- NEWS - no signal 30 minutes before / after high impact news of the two currencies (MT5 economic calendar; in MT4 the filter always passes).
- TMA - TMA zone (TmaTrue as in Seller9's EA): middle = LWMA 56 of the close, band = middle +/- 2 x ATR 100. With zone 50 % a long is only allowed when the price is half a band below the middle, a short half a band above - buy the pullback, not the top. Zone 0 = just below / above the middle.
- ADX - ADX 14 (Wilder) at least 25 and +DI / -DI in the signal direction (Seller9 V17).
- CCI - CCI 14 above +50 for a long, below -50 for a short.
- T-LINE - your own trend lines (see chapter 13): a long only after the "TMS BUY" line is broken, a short only after "TMS SELL" is broken (by candle close or price, input). No line drawn = the filter passes.
- 2/8 TREND - the 2/8 daily trend (EMA 2 / EMA 8 on D1, last closed day): green = buyer, red = seller, blue = confused (no trade). This is Seller9's AutoBuySell / Buyer-Seller step.
- STRENGTH - currency strength (Hanover style, own maths): the currency you buy must be at least 10 points stronger than the one you sell (0-100 scale). Optional: base at least 60 and quote at most 40 (Seller9's thresholds).
- HOURS - only inside your trading hours (server time, e.g. 07:00-11:00,13:00-17:00). Also blocks the auto trading outside the hours.

## Best Setup Now

- The pair with the highest TMS score (STRONG first). Big pair name, the state box, chips for the candle number, the slope, the clock position and COUNTER TREND when the signal is against the 2/8 daily trend. Below: TDI chips for MN W1 D1 H4 H1 and the lower timeframe (arrow = TDI side, cyan frame = candle color agrees), an animated TMS score gauge and the facts: entry price, Big E stop (high / low of the last 2 candles + offset, with the distance in pips), ATR of the trigger timeframe, higher timeframe TDI and candle, stochastic, strength of both currencies. Click = inspect the pair.
- TMS score 0-100: 25 slope, 10 candle 1 (7 candle 2), 20 currency strength gap, 10 higher timeframe TDI, 10 stochastic, 10 candle beyond the 5 EMA, 5 TMA side, 10 room to the 68 / 32 level.

## Big E Rule Check (selected pair, 14 animated checks)

Cross · candle 1 or 2 · angle · stochastic · not stretched (68 / 32) · currency strength · TMA pullback zone · higher timeframe · 2/8 daily trend · candle beyond the 5 EMA · ADX / CCI · trend line · spread / ADR / hours · lower timeframe. Each line shows the value. Green = ok, red = a core rule (first 3 lines) is missing, yellow = warning. Top right: how many of 14 are ok.

## Pair Inspector

Pair, price, state and the buttons:

- CHART - opens the pair on the trigger timeframe with your template "TMS" (if you have one).
- 4 CHARTS - lower, trigger, higher timeframe and D1 at once - investigate before you trade (as arbinka and Big E recommend).
- + LINES / DEL LINES - draws a "TMS BUY" line at the last swing high and a "TMS SELL" line at the last swing low of the pair (opens a chart if none is open) - drag them where you want. Or deletes them.
- BUY / SELL - market order with your stop / target settings (second click within 3 s confirms).

The chart: Heiken Ashi candles of the trigger timeframe, the yellow 5 EMA, the TMA channel (cyan middle, blue dotted bands), your trend lines (green / red dashed), dashed vertical lines at every TDI cross and the candle numbers 1 2 3 ... of the current color. Below: the full TDI window with green, red, the yellow base line, the blue volatility band and the 32 / 50 / 68 levels.

## Signal Tracker

Every new BUY / STRONG / BOUNCE signal is followed in virtual pips (spread included) until the exit rule fires on a closed candle (EXIT), the Big E stop is hit (STOP) or the opposite signal comes (END). Pips today, winners / losers, open signals with live pips, 7 days closed, the list of the latest signals (click = inspect). Saved per account for 7 days. Also shown: your own trades of today (trades, winners, losers), the limit status and hidden SL / TP mode. Below: the alert log (signals, exits, trend line breaks, filter switches, trades). This is not a trade history and not a promise - it shows what the signals did since you started the EA.

## Currency Strength

The 8 currencies ranked from strong to weak on a 0-100 scale, colored bars from the middle, the value and a momentum arrow (change over the last 5 bars). How it is calculated: for every pair the position of the close inside the range of the last 20 bars (0 = at the low, 100 = at the high); the base currency gets the value, the quote currency 100 minus the value; the average over the 7 pairs of a currency is its strength. Timeframe: the trigger timeframe (or H1 / H4 / D1, input). At the bottom: the countdown of the trigger candle with a progress bar and the entry window / trading hours status.

## 9. Exit Rules And Exit Warnings

One exit rule is used for the exit warning, the tracker and the trade manager (input):

- Big E (default) - green goes flat (slope below 1 after a move), hooks over (slope turns against the trade) or crosses back over red.
- Cross - green crosses back over red.
- Color - the candle changes color (closed candle).
- 5 EMA - the candle closes back over the 5 EMA.

The rule is checked on the closed candle only. When you have an open trade on a pair (manual or from the suite), the EXIT badge appears in the monitor and you get an exit warning alert (once per candle).

## 10. Alerts

- Popup, sound, push notification and e-mail (each on / off).
- Level: STRONG only / BUY and STRONG (default) / everything incl. BOUNCE.
- Text: state, pair, timeframe, candle number, slope, price.
- Exit warnings for open trades (on / off), trend line break alerts.
- Once per candle and direction. Switching a filter or the trigger timeframe does not cause a storm of alerts.

## 11. Trading: Buttons, Auto Trading And The Trade Manager

Auto trading is OFF by default. The suite is a monitor first - like Big E traded: look, check, click.

- Manual trading - B / S / C in every row and BUY / SELL in the inspector, always with a second click to confirm.
- Auto trading - opens a trade on every new signal of the chosen level (STRONG by default). One position per pair and direction, max trades for the whole suite, an opposite signal closes the old trade first, no orders while the market is closed or (with the HOURS filter on) outside your trading hours.
- Stop loss - Big E (high / low of the last 2 candles + offset - his own advice), last fractal + offset, ATR x multiplier, or none.
- Take profit - none (exit by the TDI, Big E style), ATR x multiplier, or risk-reward x stop distance.
- Counter trend - signals against the 2/8 daily trend get their own take profit multiplier and lot factor (e.g. smaller target, half size).
- Lot size - fixed lots or risk % of the balance (calculated from the stop distance).
- Exit by the exit rule - closes the trade when the rule fires on a candle that closed after the entry.
- Break even - stop to entry + 1 pip after N pips profit.
- Partial close - closes N % of the trade at N R (risk multiples), then moves the stop to break even (MT4: the rest keeps its state on the new ticket).
- Candlestick trailing stop (Seller9 / Hopwood) - after N pips profit the stop follows the low / high of the last N closed candles.
- Jumping stop - every N pips of profit the stop jumps N pips (first jump to break even).
- Hidden stop loss / take profit - the EA watches the levels and closes the trade itself; the broker only gets an emergency stop N pips behind (or none). Break even, trailing and jumping work on the hidden stop.
- Friday close - closes the suite trades on Friday at your hour and stops new auto trades.
- Limits - max new trades, winners and losers per day for all pairs, and the same per pair. When a limit is hit, auto trading skips the signal and writes the reason into the log.
- Magic number - the suite only manages its own trades. Exit warnings are shown for all trades on the pair.

Risk: trading is risky. Test everything on a demo account first. Big E himself said: study old charts and demo it until you have the confidence.

## 12. All Inputs, One By One

Signal

- Trigger timeframe (current = chart) - the timeframe of the signals.
- TDI cross on - closed candle (static TDI, default, no flicker) or live candle (dynamic TDI, earlier, can flicker).
- Enter only on candle 1..N (2) - the candle limit of Big E.
- Minimum slope (2.0) and strong slope (4.0) in RSI points per bar.
- Bounce trades on / off and the bounce gap (2.0 points between green and red).

Filters ON at start - one switch per filter (chapter 7). Filter settings: zone levels (68 / 32), max ADR used (80 %), max spread (3 pips), window minutes (20), news minutes (30), TMA middle (56), TMA ATR (100), TMA band (2.0), TMA zone (50 %), ADX period (14) and minimum (25), CCI period (14) and level (50), trend line break by candle close / price, 2/8 fast (2) and slow (8) EMA, strength timeframe (trigger / H1 / H4 / D1), strength bars (20), strength gap (10), strong / weak thresholds (0 = off), trading hours (07:00-17:00). TDI, candles, EMA, stochastic, ADR RSI period (13) and price (close), green line (2), red line (7), band / base line (34), candle type (Heiken Ashi / HA Smoothed / normal), 5 EMA period (5), shift (2), method (EMA) and price (typical), stochastic 8 / 3 / 3, ADR days (5). Exit - exit rule (Big E / cross / color / 5 EMA) and the flat level (1.0). Tracker - on / off. Alerts - level, popup, sound, push, e-mail, exit warnings. Trading - B / S / C buttons on / off, auto trading on / off and level, lots (0.01), risk % (0 = fixed lots), stop mode, stop offset (2 pips), ATR stop multiplier (1.5), take profit mode, take profit multiplier (2.0), exit by the exit rule, candlestick trailing on / off, trailing candles (2), trailing start (10 pips), break even pips (15), max trades (5), counter trend take profit multiplier (1.0) and lot factor (1.0), partial close % (0 = off) and partial target R (1.0), jumping stop pips (0 = off), hidden SL / TP on / off and the emergency stop distance (25 pips), Friday close hour (-1 = off), magic number, slippage (3 pips). Limits - max trades / winners / losers per day for all pairs and per pair (0 = off). Symbols - pairs to show (empty = all 28, e.g. "EURUSD,GBPJPY,AUDUSD"; the strength still uses all pairs), automatic prefix / suffix detection, or set prefix / suffix by hand. Display - what a click on a pair does (inspector / new chart / this chart), the template for opened charts ("TMS"), refresh interval (1000 ms), pill position, tooltips on / off.

## 13. Installation And Tips

- MT5: copy TL TMS Suite Pro.ex5 to MQL5\Experts - MT4: copy TL TMS Suite Pro.ex4 to MQL4\Experts. Refresh the navigator.
- Drag the EA onto ONE chart (any symbol). The chart timeframe = trigger timeframe at start. Maximise the chart.
- Tick Allow DLL imports (only for the link buttons - they open your browser). For auto trading also allow algo trading.
- First start: the history of 28 pairs x 8 timeframes is loaded (progress bar). No indicator files are needed.

- Tips

- Save your TMS chart layout as a template named TMS - every chart the suite opens uses it.
- Trend lines: draw any trend line or horizontal line on a chart of the pair and rename it to exactly TMS BUY or TMS SELL (object properties) - or use + LINES. Drag them where you want, the suite reads them every few seconds.
- Fewer pairs = a calmer screen: use the input "pairs to show".
- More filters ON = fewer but stronger signals. Start with the defaults, then switch filters in the bar and watch the BLOCKED reasons.
- Hidden SL / TP need the terminal to stay online - keep the emergency stop on.

- In memory of eelfranz (Big E) - and big thanks to Dean Malone, arbinka, Seller9, Steve Hopwood, Numb3rs and everybody in the TMS threads.
- More free EAs and indicators + coding help in my thread: Free EAs, Indicators & Strategies MT4 / MT5 (<https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4)>
- Feedback and ideas are welcome - post them here.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
