# Forward FX Rates and Interest Rate Parity

The relationship between forward FX rates, spot rates, and interest rates is governed by a concept called "Interest Rate Parity" (IRP). This principle ensures that investors cannot achieve risk-free profits through currency arbitrage.

## The Theoretical Relationship

The forward exchange rate is determined by the following formula:

$$F = S \times \frac{(1 + r_d)}{(1 + r_f)}$$

Where:
- $F$ = Forward exchange rate (domestic currency per unit of foreign currency)
- $S$ = Spot exchange rate
- $r_d$ = Domestic interest rate
- $r_f$ = Foreign interest rate

In continuous compounding terms, this is often expressed as:

$$F = S \times e^{(r_d - r_f) \times T}$$

Where $T$ is the time to maturity in years.

## Intuitive Explanation

If interest rates in Country A are higher than in Country B, the currency of Country A should trade at a forward discount relative to Country B's currency. This is because:

1. An investor could borrow in the lower-interest currency
2. Convert to the higher-interest currency at the spot rate
3. Invest at the higher interest rate
4. Use a forward contract to convert back to the original currency

For this not to be a "free lunch," the forward rate must adjust to offset the interest rate differential.

## Deviations from Interest Rate Parity in Practice

Several factors can cause deviations from IRP:

### 1. Transaction Costs
Real-world trading involves spreads, fees, and taxes that can make seemingly profitable arbitrage opportunities unprofitable when all costs are considered.

### 2. Counterparty and Credit Risk
Forward contracts carry counterparty risk. During periods of financial stress, this risk premium can cause deviations from theoretical pricing.

### 3. Liquidity Constraints
During market stress, funding liquidity can decrease dramatically, preventing arbitrageurs from borrowing to exploit price differences.

### 4. Capital Controls
Regulatory barriers in some countries restrict the free flow of capital, preventing perfect arbitrage.

### 5. Market Segmentation
Not all market participants have equal access to all markets, leading to pricing inefficiencies.

### 6. Risk Premia
Currencies perceived as risky may require additional compensation beyond what IRP would suggest.

### 7. Central Bank Intervention
Central banks may influence currency markets through policy actions or direct intervention.

### 8. Covered Interest Rate Parity (CIP) Violations
Since the 2008 financial crisis, persistent violations of CIP have occurred due to banking regulations, balance sheet constraints, and changes in money market dynamics.

The divergence between theory and practice is often measured as the "cross-currency basis," which has become an important indicator of stress in global financial markets.