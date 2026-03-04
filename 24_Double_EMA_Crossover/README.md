# Double EMA Crossover — Golden/Death Cross

## Overview
Ye classic EMA crossover strategy hai — Fast EMA (9) jab Slow EMA (21) ko upar cross kare = Golden Cross (buy); neeche cross kare = Death Cross (sell). 200 EMA trend filter aur MACD confirmation se false signals kam hote hain.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum CLASSIC, time-tested
        strategy chahte ho?
                    /     \
                 YES       NO
                  |         |
                  |    ⚠️ Advanced chahiye?
                  |       #9 Ichimoku ya #19 EMA Ribbon dekho
                  |
     Kya tum EMA CROSSOVER concept
     samajhte ho (beginner-friendly)?
                /     \
             YES       NO
              |         |
              |    ✅ Perfect beginner strategy!
              |       Pehle isse try karo, phir advanced dekho
              |
     Kya market TRENDING hai
     (200 EMA se clearly upar/neeche)?
                /     \
             YES       NO
              |         |
              |    ❌ Sideways mein crossovers
              |       false hote hain — #8 Bollinger Squeeze dekho
              |
     Kya tum MACD confirmation bhi
     use karna chahte ho (double check)?
                /     \
             YES       NO
              |         |
              |    ⚠️ MACD filter OFF karo
              |       settings mein (zyada signals milenge)
              |
     Kya tum BOTH DIRECTIONS trade
     karte ho (long + short)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Sirf long? 200 EMA filter
              |       ON karo — sirf uptrend mein trade
              |
    ✅ DOUBLE EMA CROSSOVER USE KARO!
    📁 24_Double_EMA_Crossover.pine
```

## Kaise Kaam Karta Hai
1. **Golden Cross** — Fast EMA (9) crosses above Slow EMA (21) = Buy.
2. **Death Cross** — Fast EMA (9) crosses below Slow EMA (21) = Sell.
3. **200 EMA Filter** — Sirf tab trade jab price 200 EMA ki direction mein ho.
4. **MACD Confirmation** — MACD line signal line ke upar (bull) ya neeche (bear) hona chahiye.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Fast EMA | 9 | Quick response EMA |
| Slow EMA | 21 | Slower trend EMA |
| Trend EMA | 200 | Long-term direction filter |
| Use MACD | On | MACD momentum confirmation |
| ATR Multiplier | 2.0 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |

## Best Used On
- **Timeframe:** 1H – Daily
- **Markets:** Auto sector (M&M, Tata Motors, Maruti), any liquid stock
- **Style:** Swing trading — classic approach

## Setup
1. TradingView kholo → Pine Editor
2. `24_Double_EMA_Crossover.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: M&M (M&M) — Daily Chart

**Scenario:** Mahindra & Mahindra uptrend mein hai SUV market share gains ke chalte. Classic crossover entry chahiye.

1. **Pre-Signal Setup**
   - M&M price: ₹2,720, EMA 200: ₹2,550 → Price upar (bullish bias) ✅
   - EMA 9: ₹2,680, EMA 21: ₹2,700 → Fast < Slow (abhi bearish cross)
   - MACD line: −8, Signal: −5 → Bearish but converging

2. **Golden Cross Signal!**
   - Pullback ke baad M&M rally start: ₹2,690 → ₹2,740
   - EMA 9 (₹2,725) crosses above EMA 21 (₹2,720) → **Golden Cross!**
   - Price ₹2,740 > EMA 200 (₹2,555) ✅
   - MACD: +3 > Signal: −1 → MACD bullish ✅
   - "GX↑" label dikhta hai
   - **Entry:** Long at ₹2,740

3. **Risk Management**
   - ATR(14) = ₹52, ATR Mult = 2.0
   - **Stop Loss:** ₹2,740 − (₹52 × 2.0) = ₹2,636
   - **Take Profit:** ₹2,740 + (₹104 × 2.0 R:R) = ₹2,948

4. **Week 3 — Trend delivers**
   - M&M new SUV launch hype + strong sales data
   - Price ₹2,740 → ₹2,880 → ₹2,960
   - **Take profit hit at ₹2,948**
   - **Result:** +₹208/share (+7.6%)
   - 50 shares pe: **+₹10,400 profit**

**Kyun kaam kiya:** Golden Cross + MACD confirmation + 200 EMA uptrend — triple alignment. M&M ke fundamentals (SUV demand) ne technical setup support kiya.

**Dhyan rakho:**
- EMA crossover lagging indicator hai — exact bottom nahi milega. Trend confirm hone ke baad entry milti hai.
- Auto stocks mein monthly sales data (1st week of month) big catalyst hota hai.
- Sideways market mein golden/death cross frequently alternate karte hain — 200 EMA filter ON rakho.
- MACD confirmation adds 1-2 bars delay but significantly reduces false crosses.

## Notes
- Green/red fill EMAs ke beech gap dikhata hai.
- "GX↑" (Golden Cross) aur "DX↓" (Death Cross) labels dikhte hain.
- Opposite cross pe automatic exit bhi hoti hai.
- Beginner ke liye best starting strategy — simple, proven concept.
