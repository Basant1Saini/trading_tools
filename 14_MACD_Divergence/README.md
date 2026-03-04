# MACD Divergence — Reversal Hunter

## Overview
Ye strategy price aur MACD indicator ke beech regular aur hidden divergences detect karti hai — trend reversals aur continuations pakadne ke liye. Sabse reliable divergence-based strategies mein se ek hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum REVERSAL ya CONTINUATION
        trades dhundh rahe ho?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Pure trend follow?
                  |       #12 Supertrend ya #5 Strong Trending dekho
                  |
     Kya stock mein recent EXTENDED MOVE
     aaya hai (overbought/oversold)?
                /     \
             YES       NO
              |         |
              |    ❌ No move = no divergence
              |       #8 Bollinger Squeeze ya #1 ORB dekho
              |
     Kya price NEW HIGH/LOW bana raha hai
     lekin MACD nahi bana raha (divergence)?
                /     \
             YES       NO
              |         |
              |    ⏳ Divergence form nahi hua —
              |       wait karo ya #3 RSI Extremes dekho
              |
     Kya MACD HISTOGRAM bhi direction
     mein turn kar raha hai?
                /     \
             YES       NO
              |         |
              |    ⚠️ Histogram flat hai —
              |       premature entry risk, wait karo
              |
     Kya divergence KEY S/R LEVEL pe
     ya significant price zone pe hai?
                /     \
             YES       NO
              |         |
              |    ⚠️ Random jagah pe divergence
              |       weak — confluence dhundho ya skip karo
              |
    ✅ MACD DIVERGENCE USE KARO!
    📁 14_MACD_Divergence.pine
```

## Kaise Kaam Karta Hai
1. **Pivot Detection** — Price aur MACD line dono pe swing highs/lows identify karti hai.
2. **Regular Divergence** — Price naya low/high banaye lekin MACD na banaye → potential reversal.
3. **Hidden Divergence** — Price higher low / lower high banaye lekin MACD na banaye → trend continuation.
4. **Histogram Confirmation** — Entry sirf tab jab MACD histogram trade ki direction mein turn kare.
5. **RSI Filter** (optional) — RSI already extreme hai toh entry avoid karti hai.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| MACD Fast/Slow/Signal | 12, 26, 9 | Standard MACD settings |
| Pivot Lookback | 5 | Pivot confirm karne ke liye bars |
| Pivot Look Forward | 2 | Aage confirm ke liye bars |
| Regular Divergence | On | Reversal divergences trade karo |
| Hidden Divergence | On | Continuation divergences trade karo |
| RSI Filter | On | Extreme RSI entries avoid karo |
| ATR Multiplier | 2.0 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |

## Best Used On
- **Timeframe:** 15m – Daily
- **Markets:** Sab markets — auto stocks (Maruti, Tata Motors), banking, IT
- **Style:** Reversal aur continuation trading

## Setup
1. TradingView kholo → Pine Editor
2. `14_MACD_Divergence.pine` ka code paste karo
3. **Add to Chart** pe click karo
4. MACD indicator alag se bhi add karo visual confirmation ke liye

## Example: Maruti Suzuki (MARUTI) — Daily Chart

**Scenario:** Maruti sell-off ke baad bottom form kar raha hai. MACD divergence reversal signal de raha hai.

1. **Sell-off Phase**
   - Maruti ₹11,200 se gir ke ₹10,400 tak aa gaya auto sector weakness mein
   - Pehla swing low: ₹10,600 (MACD line: −120)
   - Price aur gira: ₹10,400 (naya lower low)

2. **Bullish Divergence Detected!**
   - Price: ₹10,400 < ₹10,600 → **Lower low** ✅
   - MACD: −95 > −120 → **Higher low** ✅
   - **Regular Bullish Divergence** confirmed!
   - MACD histogram turn: −15 se −8 pe aaya (improving)
   - RSI = 35 (70 se neeche, filter OK)
   - "DIV" diamond marker dikhta hai
   - **Entry:** Long at ₹10,450

3. **Risk Management**
   - ATR(14) = ₹250, ATR Mult = 2.0
   - **Stop Loss:** ₹10,450 − (₹250 × 2.0) = ₹9,950
   - **Take Profit:** ₹10,450 + (₹500 × 2.0 R:R) = ₹11,450

4. **Week 3 — Reversal play out hua**
   - Maruti ₹10,400 se bounce karke ₹11,350 tak gaya
   - Auto sector mein buying wapas aayi festive season expectations pe
   - **Take profit hit at ₹11,450**
   - **Result:** +₹1,000/share (+9.6%)
   - 20 shares pe: **+₹20,000 profit**

**Kyun kaam kiya:** Price lower low bana raha tha lekin MACD selling momentum weak ho raha tha (higher low). Ye classic reversal signal hai — selling exhaustion dikha raha tha.

**Dhyan rakho:**
- Regular divergence = counter-trend (reversal); Hidden divergence = with-trend (continuation).
- Divergence key support/resistance pe sabse achha kaam karta hai — random jagah pe mat trade karo.
- Auto stocks mein monthly sales data ka bada impact hota hai — data release dates check karo.
- Alag se MACD indicator chart pe add karo visual divergence confirmation ke liye.

## Notes
- "DIV" diamond markers divergence entry points pe dikhte hain.
- Regular divergence = reversal; Hidden divergence = continuation.
- Key S/R levels pe aur extended moves ke baad best kaam karta hai.
