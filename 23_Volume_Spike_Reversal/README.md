# Volume Spike Reversal — Smart Money Detection

## Overview
Ye strategy abnormal volume spikes detect karti hai (2.5x+ average volume) aur RSI extremes + reversal candle patterns ke saath combine karke potential trend reversals pakadti hai. Smart money (institutional) activity ka sign hai sudden volume spike.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum VOLUME analysis
        samajhte ho?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Volume nahi samajhte?
                  |       #3 RSI Extremes ya #14 MACD Divergence dekho
                  |
     Kya tum REVERSAL trades dhundh
     rahe ho (counter-trend)?
                /     \
             YES       NO
              |         |
              |    ❌ Trend follow karna hai?
              |       #12 Supertrend ya #19 EMA Ribbon dekho
              |
     Kya stock mein EXTENDED MOVE
     hua hai (overbought/oversold)?
                /     \
             YES       NO
              |         |
              |    ⏳ No extreme = no reversal signal
              |       #18 Inside Bar ya #25 NR7 dekho
              |
     Kya volume SPIKE aa raha hai
     (2.5x+ average)?
                /     \
             YES       NO
              |         |
              |    ⏳ Normal volume pe reversal
              |       weak hota hai — wait karo
              |
     Kya REVERSAL CANDLE pattern
     ban raha hai (hammer, shooting star)?
                /     \
             YES       NO
              |         |
              |    ⚠️ "Any Close" mode try karo
              |       ya #14 MACD Divergence dekho
              |
    ✅ VOLUME SPIKE REVERSAL USE KARO!
    📁 23_Volume_Spike_Reversal.pine
```

## Kaise Kaam Karta Hai
1. **Volume Spike Detection** — Volume ≥ 2.5x 20-bar average = spike.
2. **RSI Extreme Filter** — RSI < 30 (oversold) for long; RSI > 70 (overbought) for short.
3. **Candle Confirmation** — Reversal candle (hammer, bullish engulfing) ya simple directional close.
4. **Direction Check** — Price below SMA 20 for long (was falling); above for short (was rising).

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Volume Spike Mult | 2.5x | Kitna volume = spike |
| RSI Length | 14 | RSI period |
| RSI OB/OS | 70 / 30 | Overbought / Oversold |
| Candle Confirmation | Reversal Candle | Reversal pattern, Any Close, ya None |
| ATR Multiplier | 2.0 | Stop loss distance |
| Risk:Reward | 2.5 | Higher R:R for reversal trades |

## Best Used On
- **Timeframe:** 1H – Daily
- **Markets:** PSU/utility stocks (Power Grid, NTPC, Coal India), any stock with clear volume patterns
- **Style:** Reversal / contrarian trading

## Setup
1. TradingView kholo → Pine Editor
2. `23_Volume_Spike_Reversal.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: Power Grid (POWERGRID) — Daily Chart

**Scenario:** Power Grid 3 hafte se gir raha hai sector rotation ke chalte. Volume spike reversal ka signal dhundh rahe ho.

1. **Sell-off Phase**
   - Power Grid ₹320 se ₹285 tak gira — consistent selling
   - 20 SMA = ₹300 → Price neeche (falling) ✅
   - RSI = 24 → Oversold ✅
   - Volume average 15L shares/day

2. **Volume Spike + Reversal Candle!**
   - Day X: Volume = 42L shares (2.8x average!) → **Spike!** ✅
   - Yellow background dikhta hai
   - Candle: Low ₹280, Open ₹283, Close ₹292 (bullish, upper half close) ✅
   - Hammer-like pattern (long lower wick) ✅
   - "VOL↑" label dikhta hai
   - **Entry:** Long at ₹292

3. **Risk Management**
   - ATR(14) = ₹8.50, ATR Mult = 2.0
   - **Stop Loss:** ₹292 − (₹8.50 × 2.0) = ₹275
   - **Take Profit:** ₹292 + (₹17 × 2.5 R:R) = ₹334.50

4. **Week 2-3 — Reversal play out hua**
   - Institutional buyers ne ₹280 pe accumulation kiya tha (volume spike = smart money)
   - Power Grid bounce karta hai ₹292 → ₹310 → ₹330
   - **Take profit hit at ₹334.50**
   - **Result:** +₹42.50/share (+14.6%)
   - 500 shares pe: **+₹21,250 profit**

**Kyun kaam kiya:** 2.8x volume spike ne institutional accumulation signal kiya. ₹280 pe smart money ne buy kiya jab retail panic sell kar raha tha. Hammer candle ne reversal confirm kiya.

**Dhyan rakho:**
- Volume spike reversal ke bina (sirf volume spike) trade mat karo — candle confirmation zaroori.
- PSU stocks mein government disinvestment news se sudden volume spikes aate hain — ye different signal hai.
- Dividend stocks (Power Grid, NTPC) mein ex-dividend date pe volume spike normal hai — avoid.
- 2.5x multiplier strict hai — 2.0x pe zyada signals milenge but quality kam.

## Notes
- Yellow background volume spike days highlight karta hai.
- "VOL↑" / "VOL↓" labels reversal entry points pe dikhte hain.
- Small yellow diamonds = volume spike without reversal signal (watch only).
- Higher R:R (2.5:1) because reversal trades need more room.
