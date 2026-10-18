<div align="center">

# ⚡ TL Riverbank Pro

**Inthebox's "Waiting at the Riverbank" gold method — session, HTF level, sweep, BOS and engulf entry.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_RiverbankPro_FF.png" alt="TL Riverbank Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Riverbank Pro.ex4`](MT4/TL%20Riverbank%20Pro.ex4) |
| **MT5** | [`TL Riverbank Pro.ex5`](MT5/TL%20Riverbank%20Pro.ex5) |

> Compiled build only — source code is not published.

## Independently Written

Written from scratch by trader.lifestyle - own code. The trading rules follow Inthebox's "Waiting at the Riverbank" method from his Forex Factory thread <https://www.forexfactory.com/thread/1359156-waiting-at-the-riverband> (all 4,411 posts, his PDF "Waiting at the Riverbank", the 91-page "Rules" PDF and his later "simplified 3 steps model" were read for this EA). Big thanks to Inthebox for sharing it for free.

## The Idea - "let price come to us, we don't chase it"

A crocodile waits at the riverbank where the animals come to drink. The EA waits at the HTF key level during a market session and only acts when the LTF Riverbank pattern confirms it.

## The 6 Conditions (SOP from post #1, graded A / B / C)

3 main conditions
- Market session   - the entry is in the first 3 h after the Tokyo, London or New York open (DST aware, broker GMT auto)
- HTF key level    - the head or the right shoulder touches an HTF level: H4 / D1 engulf zones, Malaysian SnR (A / V close-open levels incl. flipped ones), previous day / week high + low, day + week open
- Premium/discount - buy below / sell above 50 % of the leg or of today's range
3 conditions of the LTF confirmation entry (the Riverbank pattern)
- Liquidity sweep  - price trades beyond a fractal swing point and closes back inside = the HEAD
- Break of structure - a candle CLOSES beyond the last swing point before the head
- Sweep beyond the BOS - the pullback comes back beyond the broken level = the RIGHT SHOULDER
Grade A = 6, B = 5, C = 4 conditions. Minimum grade is an input. Entry: after the pullback into the engulf zone of the impulse leg, the first candle that closes back out of the engulf (thread: "candle that closes above the engulf when coming out of engulf"). Breakout entry at the BOS close and "both" (half / half) are inputs too. Trend: price above / below the 200 EMA (Inthebox's simple model), or the higher timeframe EMA, or HTF HH/HL structure.

## Stop, Target, Management

- Stop at the HEAD (default) or at the right shoulder, + ATR buffer
- Target: next HTF level / swing (1.2 - 3 R), fixed R:R or fixed pips
- Partial close 50 % at +1 R + break even ("40 pips = 1st partial TP, if you don't take it, put BE on") - optional ATR trailing
- Optional exit after 1 or 2 candle closes beyond the engulf (thread SL rule)
- Max 1 trade per session, max trades per day, daily loss limit, spread filter, high impact news filter (MT5 calendar, live), Friday stop

## What We Improved

- Entry timeframe input, default M15 (Inthebox: "experiment to use m15 only") - on M5 the pattern fires 2-3x as often and loses to noise/spread
- Stop at the head instead of the right shoulder: gold sweeps the tight
- Equal risk per trade: in the data the grades A / B / C did NOT predict the result, so the 3/2/1 unit sizing of the PDF is an option (OFF)
- Only the 3 nearest HTF levels above / below are drawn ("at most 3 HTF SnR")
- News filter, daily guard, broker clock / DST handling for the sessions

## The Panel (animated quant panel)

- Riverbank SOP: trend pill, the 6 conditions as traffic lights with their values, grade gauge C / B / A, head / BOS / engulf levels, phase (WAITING AT THE RIVERBANK / SWEPT / BOS / IN THE ENGULF / ENTRY)
- HTF key levels: the 2 nearest above + below with distance in ATR, session clock Tokyo / London / New York with countdown, news
- Signal track record on your chart history, auto trading on/off, close EA trades, daily guard, live statistics
- X closes the panel to a pill, drag the header to move it
- Chart: session boxes (like the thread's charts), LS / BOS marks, engulf zone boxes, HTF levels, 200 EMA, entry arrows with R result tags

## Install

- MT5: copy "TL Riverbank Pro.ex5" to  File > Open Data Folder > MQL5\Experts
- MT4: copy "TL Riverbank Pro.ex4" to  File > Open Data Folder > MQL4\Experts Attach to XAUUSD (any chart timeframe - the entry timeframe is an input, default M15). Allow algo trading. "Allow DLL imports" is only needed for the link buttons (YouTube / RoboForex / WhatsApp / Forex Factory).
- The broker clock: "Auto" assumes a New-York-close broker (GMT+2 winter / GMT+3 summer, e.g. RoboForex, IC Markets). Other brokers: set the offset manually. The session clock in the panel shows the server times.

## Risk Note

Trading is risky. Results of the past are no guarantee. Test on demo first.

trader.lifestyle - YouTube / WhatsApp / Forex Factory: buttons in the panel

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
