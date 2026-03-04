# Parabolic SAR — Stop and Reverse

## Overview
Ye strategy Welles Wilder ka classic Parabolic SAR (Stop and Reverse) indicator use karti hai. SAR dots price ke neeche hain toh bullish, upar hain toh bearish. Flip pe entry/exit. ADX filter se choppy market filter hota hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tumhe VISUAL DOTS based
        trading chahiye (simple signals)?
                    /     \
                 YES       NO
                  |         |
                  |    ⚠️ Line-based chahiye?
                  |       #21 Chandelier ya #12 Supertrend dekho
                  |
     Kya market TRENDING hai
     (ADX > 20)?
                /     \
             YES       NO
              |         |
              |    ❌ SAR choppy market mein
              |       bahut flip karta hai — #3 RSI Extremes dekho
              |
     Kya tum BOTH LONG AND SHORT
     trade karte ho?
                /     \
             YES       NO
              |         |
              |    ⚠️ Sirf long? Trend filter
              |       ON karo — #24 Double EMA better hai
              |
     Kya tum INTRADAY ya SHORT SWING
     trader ho?
                /     \
             YES       NO
              |         |
              |    ⚠️ SAR ka acceleration fast hai
              |       longer TF ke liye #21 Chandelier dekho
              |
     Kya tum AUTO EXIT chahte ho
     (SAR flip = exit)?
                /     \
             YES       NO
              |         |
              |    Fixed TP chahiye?
              |       #24 Double EMA ya #20 Stochastic RSI dekho
              |
    ✅ PARABOLIC SAR USE KARO!
    📁 22_Parabolic_SAR.pine
```

## Kaise Kaam Karta Hai
1. **SAR Calculation** — Parabolic dots price ke neeche (bullish) ya upar (bearish) plot hote hain.
2. **SAR Flip** — Dots neeche se upar jaayein = bearish flip (short); upar se neeche = bullish flip (long).
3. **ADX Filter** — ADX > 20 chahiye — trending market confirm.
4. **EMA Trend Filter** — Optional 50 EMA se overall direction filter.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| SAR Start | 0.02 | Initial acceleration factor |
| SAR Increment | 0.02 | Acceleration step increase |
| SAR Maximum | 0.2 | Max acceleration factor |
| Trend EMA | 50 | Direction filter |
| ADX Length | 14 | ADX period |
| ADX Minimum | 20 | Min ADX for trend confirmation |
| ATR Multiplier | 2.0 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |

## Best Used On
- **Timeframe:** 15m – Daily
- **Markets:** Telecom/utility stocks (Bharti Airtel, Jio Financial, Vodafone Idea), trending stocks
- **Style:** Trend following with auto reversal

## Setup
1. TradingView kholo → Pine Editor
2. `22_Parabolic_SAR.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: Bharti Airtel (BHARTIARTL) — Daily Chart

**Scenario:** Bharti Airtel uptrend mein hai tariff hike aur subscriber growth ke chalte. SAR se trend ride karna hai.

1. **SAR Bearish → Bullish Flip**
   - Bharti Airtel ₹1,580 pe tha, SAR dots upar at ₹1,600 (bearish)
   - Strong candle: ₹1,615 pe close → SAR dots flip to neeche at ₹1,570
   - ADX = 28 → Strong trend ✅
   - 50 EMA = ₹1,560 → Price upar ✅
   - "SAR↑" label dikhta hai
   - **Entry:** Long at ₹1,615

2. **Risk Management**
   - ATR(14) = ₹28, ATR Mult = 2.0
   - **Stop Loss:** ₹1,615 − (₹28 × 2.0) = ₹1,559
   - **Take Profit:** ₹1,615 + (₹56 × 2.0 R:R) = ₹1,727

3. **Week 2-3 — SAR dots trail**
   - Bharti Airtel ₹1,615 → ₹1,660 → ₹1,710
   - SAR dots: ₹1,570 → ₹1,590 → ₹1,620 → ₹1,655
   - Dots accelerate (parabolic shape) — getting closer to price

4. **Week 4 — Take Profit hit**
   - Bharti Airtel ₹1,735 tak rally
   - **Take profit hit at ₹1,727**
   - **Result:** +₹112/share (+6.9%)
   - 100 shares pe: **+₹11,200 profit**

**Kyun kaam kiya:** Bharti Airtel ka trend strong tha (ADX 28). SAR ne clean entry diya aur dots ne trailing stop ka kaam kiya. Acceleration factor ne trend mature hone pe stops tighten kiye.

**Dhyan rakho:**
- SAR ka acceleration factor trend ke saath badhta hai — eventually price SAR hit karegi. Ye feature hai, bug nahi.
- Telecom stocks mein tariff hike news = instant rally. TRAI announcements track karo.
- Choppy market mein SAR har 2-3 bars pe flip karega — ADX filter ON rakho.
- SAR Maximum (0.2) zyada karo toh dots slower tighten hoti hain.

## Notes
- Green dots = bullish (below price); Red dots = bearish (above price).
- SAR flip pe auto entry/exit — no manual trailing needed.
- ADX filter default ON hai — significantly reduces false flips.
- Classic indicator — Welles Wilder ne 1978 mein develop kiya.
