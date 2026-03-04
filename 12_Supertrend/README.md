# Supertrend — Dynamic Trend Follower

## Overview
Ye ek clean trend-following strategy hai Supertrend indicator ke saath, jo dynamic support/resistance levels deta hai aur trend direction ke saath flip hota hai. Optional dual Supertrend confirmation bhi hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum TREND FOLLOWING
        approach chahte ho?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Reversal chahiye?
                  |       #14 MACD Divergence ya #3 RSI Extremes dekho
                  |
     Kya tumhe SIMPLE, clean signals
     chahiye (indicator-based)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Complex setup chahiye?
              |       #9 Ichimoku ya #2 MTF dekho
              |
     Kya market mein CLEAR TREND hai
     (na sideways, na choppy)?
                /     \
             YES       NO
              |         |
              |    ❌ Supertrend choppy mein
              |       bahut flip karti hai — #8 Bollinger Squeeze dekho
              |
     Kya stock LIQUID hai (Wipro,
     TCS, Reliance jaise)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Low liquidity mein false
              |       flips zyada — #13 Donchian (longer TF) dekho
              |
     Kya tum DYNAMIC STOP LOSS chahte ho
     (auto trailing with trend)?
                /     \
             YES       NO
              |         |
              |    Fixed targets chahiye?
              |       #5 Strong Trending ya #10 Fibonacci dekho
              |
    ✅ SUPERTREND USE KARO!
    📁 12_Supertrend.pine
```

## Kaise Kaam Karta Hai
1. **Supertrend Flip** — Jab primary Supertrend bearish se bullish flip ho toh long; opposite flip pe short.
2. **Dual Confirmation** (optional) — Slow aur fast dono Supertrends agree karein tab entry.
3. **Dynamic Stops** — Supertrend line khud trailing stop ki tarah kaam karti hai; flip pe exit.
4. **EMA Filter** (optional) — Sirf 200 EMA ki direction mein trade karo.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Factor 1 / Period 1 | 3.0 / 10 | Primary (slower) Supertrend |
| Factor 2 / Period 2 | 2.0 / 7 | Fast Supertrend dual mode ke liye |
| Dual Supertrend | On | Dono STs agree karna chahiye |
| EMA Trend Filter | Off | Optional 200 EMA filter |
| ATR Multiplier | 2.0 | Stop loss distance |
| Trailing ATR | 2.5 | Trailing stop distance |

## Best Used On
- **Timeframe:** 5m – Daily
- **Markets:** Trending stocks (Wipro, TCS, Reliance), Nifty/BankNifty
- **Style:** Trend following with dynamic stops

## Setup
1. TradingView kholo → Pine Editor
2. `12_Supertrend.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: Wipro (WIPRO) — Daily Chart

**Scenario:** Wipro downtrend se bullish flip de raha hai new deal wins ki news ke baad.

1. **Bearish Phase (before flip)**
   - Supertrend 1 (3.0, 10): Red line ₹475 pe — bearish
   - Supertrend 2 (2.0, 7): Red line ₹472 pe — bearish
   - Dono bearish aligned hain (red background)

2. **Bullish Flip!**
   - Wipro ₹480 pe strong bullish candle close karta hai
   - Primary Supertrend bearish se bullish flip hua → Green line ab ₹468 pe
   - Fast Supertrend bhi already bullish tha → **Dual confirmation** ✅
   - **Entry:** Long at ₹480

3. **Risk Management**
   - ATR(14) = ₹12, ATR Mult = 2.0
   - **Stop Loss:** ₹480 − (₹12 × 2.0) = ₹456
   - **Trailing Stop:** ATR × 2.5 = ₹30 trailing distance

4. **Week 2–3 — Uptrend develop hota hai**
   - Wipro ₹505, phir ₹520 tak rally karta hai
   - Supertrend green line upar move karti hai: ₹505 pe
   - Trailing stop: ₹520 − ₹30 = ₹490

5. **Week 4 — Supertrend flip exit**
   - Supertrend bearish flip hota hai → **Exit at ₹512**
   - **Result:** +₹32/share (+6.7%) ~4 weeks mein
   - 500 shares pe: **+₹16,000 profit**

**Kyun kaam kiya:** Dual Supertrend confirmation ne false flip filter kar diya. Wipro ka bullish flip genuine tha deal wins ke fundamental support ke saath.

**Dhyan rakho:**
- Choppy/range-bound market mein Supertrend bahut zyada flip karti hai — avoid karo.
- Dual mode se signals kam aate hain but quality better hoti hai.
- IT sector mein quarterly guidance miss pe achanak bearish flip aa sakta hai.
- Nifty IT index bhi check karo confirmation ke liye.

## Notes
- Green/red Supertrend lines chart pe trend direction dikhati hain.
- Background shading jab dono Supertrends agree karein.
- Supertrend flip pe auto exit — fixed targets ki zaroorat nahi.
- Trending markets mein bahut effective; choppy conditions avoid karo.
