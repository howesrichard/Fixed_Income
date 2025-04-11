# Understanding the AUD/USD Cross-Currency Basis Swap Spread

When I stated that the AUD/USD cross-currency basis swap spread reached approximately -50 basis points during the GFC, here's what that specifically means with the relevant rates:

## The Rates During the GFC (Late 2008)

### Interest Rates (3-month)
- AUD (Australian Bank Bill Swap Rate): ~5.25%
- USD (LIBOR): ~3.00%
- Interest rate differential: ~2.25% (AUD higher than USD)

### Exchange Rates
- AUD/USD spot (approx): 0.6500
- 3-month AUD/USD forward (theoretical based on interest rate parity): ~0.6631
- 3-month AUD/USD forward (actual market rate): ~0.6601

## What the Basis Swap Measures

A cross-currency basis swap involves:
1. Party A swaps principal amount in AUD for equivalent USD at spot rate with Party B
2. Party A receives USD LIBOR
3. Party A pays AUD interest rate (BBSW) + the basis spread
4. At maturity, principal amounts are swapped back at the original spot rate

The basis spread is the additional premium above or below the standard interest rate that must be paid to execute the swap. It represents the deviation from covered interest parity.

## Numerical Example

For a notional amount of AUD 100 million with a -50 basis point basis:

1. **Principal Exchange (Initial)**:
   - AUD 100 million exchanged for USD 65 million (at 0.6500 spot rate)

2. **Interest Payments (Quarterly)**:
   - Party A receives: USD 65 million × 3.00% × 0.25 = USD 487,500
   - Party A pays: AUD 100 million × (5.25% - 0.50%) × 0.25 = AUD 1,187,500
   - Note that the AUD interest payment is reduced by the negative basis

3. **Principal Exchange (Maturity)**:
   - USD 65 million exchanged back for AUD 100 million (at the original spot rate)

## What the -50bp Basis Practically Means

The negative basis of -50bp means:

1. **USD Premium**: Borrowing USD through the swap market was effectively 0.50% more expensive annually than the interest rate differential would suggest

2. **Deviation Magnitude**: According to CIP, the AUD/USD forward rate should have been around 0.6631, but was trading closer to 0.6601, reflecting the basis deviation

3. **Market Interpretation**: Market participants needed to pay an additional 50bp premium to obtain USD funding using AUD as collateral, beyond what interest rate differentials suggested

4. **Economic Impact**: Australian banks borrowing USD through cross-currency swaps were paying approximately AUD 50 million per year in additional funding costs for every AUD 10 billion borrowed (compared to theoretical CIP rates)

This -50bp spread was unprecedented in pre-crisis markets, where the basis typically traded within 1-5bp of zero. The widening indicated severe stress in USD funding markets and reflected the breakdown of arbitrage mechanisms that would normally keep the basis near zero.

The basis spread effectively became a market-determined price for the scarcity of USD funding availability and the institutional constraints preventing arbitrageurs from exploiting and closing the gap.