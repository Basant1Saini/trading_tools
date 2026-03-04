# Ichimoku Cloud Strategy

## Overview
Ye ek complete trading system hai Ichimoku Kinko Hyo indicator pe based. Paanch components use karti hai — Tenkan-Sen, Kijun-Sen, Senkou Span A/B (Cloud), aur Chikou Span — high-confidence entries ke liye.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum SWING/POSITIONAL
        trades lete ho (days/weeks)?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Intraday chahiye?
                  |       #6 VWAP ya #7 Scalper dekho
                  |
     Kya tum MULTIPLE CONFIRMATIONS
     chahte ho ek hi indicator se?
                /     \
             YES       NO
              |         |
              |    ⚠️ Simple setup chahiye?
              |       #5 Strong Trending ya #12 Supertrend dekho
              |
     Kya stock TRENDING market mein hai
     (na sideways, na choppy)?
                /     \
             YES       NO
              |         |
              |    ❌ Ichimoku sideways mein
              |       kaam nahi karta — #3 RSI Extremes dekho
              |
     Kya price CLOUD ke clearly
     upar ya neeche hai?
                /     \
             YES       NO
              |         |
              |    ⏳ Cloud ke andar = no-trade zone
              |       Clear breakout ka wait karo
              |
     Kya TK Cross + Chikou Span
     dono confirm kar rahe hain?
                /     \
             YES       NO
              |         |
              |    ⚠️ Partial signal — kam size
              |       se trade karo ya #10 Fibonacci dekho
              |
    ✅ ICHIMOKU CLOUD USE KARO!
    📁 9_Ichimoku_Cloud.pine
```

## Kaise Kaam Karta Hai
1. **TK Cross Entry** — Tenkan jab Kijun ke upar/neeche cross kare, aur price cloud ke upar/neeche ho.
2. **Cloud Breakout Entry** — Price jab cloud ke upar/neeche break kare TK alignment ke saath.
3. **Chikou Confirmation** (optional) — Current close 26 bars pehle ke close se upar/neeche hona chahiye.
4. **Exit** — Trailing ATR stop ya opposite TK cross.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Tenkan-Sen | 9 | Conversion line period |
| Kijun-Sen | 26 | Base line period |
| Senkou Span B | 52 | Cloud leading span B period |
| Displacement | 26 | Cloud aur Chikou offset |
| TK Cross Entry | On | Tenkan/Kijun crossovers trade karo |
| Cloud Breakout | On | Cloud breakouts trade karo |
| Chikou Confirm | On | Chikou Span confirmation chahiye |
| ATR Multiplier | 2.0 | Stop loss distance |
| Trailing ATR | 3.0 | Trailing stop distance |

## Best Used On
- **Timeframe:** 1H – Weekly
- **Markets:** Metal/commodity stocks (Tata Steel, Hindalco, JSW Steel), indices
- **Style:** Trend following / swing trading

## Setup
1. TradingView kholo → Pine Editor
2. `9_Ichimoku_Cloud.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: Tata Steel (TATASTEEL) — Daily Chart

**Scenario:** Tata Steel steady uptrend mein hai steel demand badhne ke chalte. High-confidence Ichimoku entry chahiye.

1. **Cloud & Component Check**
   - Senkou Span A: ₹142, Senkou Span B: ₹135 → **Green cloud** (bullish)
   - Cloud top = ₹142, Cloud bottom = ₹135
   - Tata Steel price = ₹150 → **Cloud ke upar** ✅
   - Tenkan-Sen (9): ₹148, Kijun-Sen (26): ₹145
   - Tenkan > Kijun → Bullish alignment

2. **TK Cross Signal**
   - Pullback ke baad, Tenkan ₹144 tak gira aur Kijun ₹145 ko wapas upar cross kiya
   - **TK Cross** jab price cloud ke upar hai → Strong bullish signal
   - Chikou: Current close ₹149 > 26 bars pehle ka close ₹138 → **Chikou confirmed** ✅
   - **Paancho conditions met** (rare, high probability!)
   - **Entry:** Long at ₹149

3. **Risk Management**
   - ATR(14) = ₹5.80, ATR Mult = 2.0
   - **Stop Loss:** ₹149 − (₹5.80 × 2.0) = ₹137.40
   - **Trailing Stop:** ATR × 3.0 = ₹17.40 trailing distance

4. **Week 3 — Trend continue karta hai**
   - Tata Steel ₹165 tak rally, trailing stop: ₹165 − ₹17.40 = ₹147.60

5. **Week 5 — TK cross exit**
   - Tenkan ne Kijun ko neeche cross kiya → **Exit at ₹162**
   - **Result:** +₹13/share (+8.7%) ~5 weeks mein
   - 500 shares pe: **+₹6,500 profit**

**Kyun kaam kiya:** Paancho Ichimoku conditions aligned thein — cloud ke upar price, TK cross bullish, Chikou confirmed. Trending market mein ye highest-confidence signal hota hai.

**Dhyan rakho:**
- Price agar cloud ke andar hai, toh no-trade zone hai — clear breakout ka wait karo.
- Aage thin cloud = weak support; thick cloud = strong. Thin cloud ke through breakout trade karo.
- Metal stocks commodity prices (steel, aluminium) se directly correlated hain — global metal prices bhi check karo.
- China ki demand news Tata Steel ko directly impact karti hai.

## Notes
- Cloud (Kumo) 26 bars aage plot hota hai — future support/resistance dikhata hai.
- Green cloud = bullish, red cloud = bearish.
- Thick cloud strong S/R, thin cloud weak S/R.
- 5 conditions aligned = sabse high probability signal.
