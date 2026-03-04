# Chandelier Exit — ATR Trailing Stop System

## Overview
Ye strategy Chandelier Exit indicator use karti hai — jo highest high se ATR ka multiple neeche trailing stop lagati hai. Jab price trailing stop ke neeche close kare, exit. Direction flip pe new entry. Trend mein ride karne ka best system hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum TRAILING STOP based
        system chahte ho?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Fixed targets chahiye?
                  |       #10 Fibonacci ya #11 Pivot Points dekho
                  |
     Kya tum TRENDS ride karna chahte ho
     (let profits run)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Quick profits chahiye?
              |       #7 Scalper ya #16 Gap and Go dekho
              |
     Kya tum ATR-BASED dynamic stops
     samajhte ho?
                /     \
             YES       NO
              |         |
              |    ⚠️ Simpler trailing chahiye?
              |       #12 Supertrend (similar but simpler) dekho
              |
     Kya stock TRENDING hai
     (clear directional move)?
                /     \
             YES       NO
              |         |
              |    ❌ Choppy market mein
              |       Chandelier whipsaw karega — #8 Bollinger Squeeze dekho
              |
     Kya tum SWING/POSITIONAL trades
     lete ho (days se weeks)?
                /     \
             YES       NO
              |         |
              |    ❌ Intraday ke liye
              |       #22 Parabolic SAR faster hai
              |
    ✅ CHANDELIER EXIT USE KARO!
    📁 21_Chandelier_Exit.pine
```

## Kaise Kaam Karta Hai
1. **Long Stop** — Highest high (22 bars) minus ATR × 3.0 = trailing stop.
2. **Short Stop** — Lowest low (22 bars) plus ATR × 3.0 = trailing stop.
3. **Flip Entry** — Jab direction flip ho (bearish → bullish), long entry; opposite pe short.
4. **Dynamic Trailing** — Stop trend ke saath move karti hai — profits lock hote rehte hain.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| ATR Period | 22 | Lookback for ATR + extreme price |
| ATR Multiplier | 3.0 | Stop distance (higher = wider stops) |
| Use Close | On | Close vs High/Low for extremes |
| Trend EMA | 200 | Optional long-term direction filter |
| Initial SL ATR | 1.5 | Tight initial stop before trailing kicks in |

## Best Used On
- **Timeframe:** Daily – Weekly
- **Markets:** Quality trending stocks (Titan, Bajaj Finance, HDFC Bank)
- **Style:** Swing / position trading with trailing stops

## Setup
1. TradingView kholo → Pine Editor
2. `21_Chandelier_Exit.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: Titan Company (TITAN) — Daily Chart

**Scenario:** Titan steady uptrend mein hai festive season demand aur jewellery growth ke chalte. Trailing stop system se ride karna hai.

1. **Bearish Phase → Bullish Flip**
   - Titan ₹3,350 pe tha, Chandelier short line (red) ₹3,420 pe
   - Strong bullish candle: Titan ₹3,440 pe close → Short line ₹3,420 ke upar
   - **Direction flip: Bearish → Bullish!**
   - "CHAN↑" label dikhta hai, background green
   - **Entry:** Long at ₹3,440

2. **Risk Management**
   - ATR(22) = ₹75, Initial SL Mult = 1.5
   - **Initial Stop:** ₹3,440 − (₹75 × 1.5) = ₹3,327
   - Chandelier trailing: Highest high − (ATR × 3.0)

3. **Week 2-4 — Trend develops**
   - Titan ₹3,440 → ₹3,550 → ₹3,680
   - Chandelier long line (green) trails: ₹3,350 → ₹3,420 → ₹3,455
   - Stop automatically tighten hota ja raha hai

4. **Week 6 — Chandelier Exit triggered**
   - Titan pullback karta hai ₹3,650 se ₹3,580 tak
   - Chandelier long line ₹3,590 pe thi
   - Close ₹3,580 < ₹3,590 → **Exit triggered at ₹3,580**
   - **Result:** +₹140/share (+4.1%) ~6 weeks mein
   - 100 shares pe: **+₹14,000 profit**

**Kyun kaam kiya:** Chandelier Exit ne trend ke saath trailing stop dynamically adjust kiya. Wide ATR multiplier (3.0) ne minor pullbacks mein stop hit nahi hone diya.

**Dhyan rakho:**
- ATR Multiplier badhane se stops wider hote hain — zyada room but bada risk per trade.
- Titan jaise consumer stocks mein festive season (Oct-Dec) strong trends laati hai.
- Gold prices Titan ko directly impact karte hain — gold rally = Titan rally usually.
- Choppy market mein frequent flips = losses. ADX > 20 check karo.

## Notes
- Green line = long trailing stop; Red line = short trailing stop.
- Background green = bullish direction; red = bearish.
- "CHAN↑" / "CHAN↓" labels direction flip pe dikhte hain.
- 3.0 ATR multiplier gives room for normal pullbacks.
