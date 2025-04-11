## Overnight Index Swaps (OIS)

### Overview
Overnight Index Swaps (OIS) are interest rate swap contracts where a fixed rate is exchanged for a floating rate based on a compounded overnight interbank cash rate, the Reserve Bank of Australia (RBA) cash rate in Australia's case. OIS has grown in importance as a key benchmark for risk-free rates.

### Key Characteristics

- **Reference Rate**: RBA overnight cash rate (compounded)
- **Tenor**: Range from 1 week to 2 years typically, with longer tenors possible
- **Payment Frequency**: Single payment at maturity (for short tenors)
- **Market Structure**: OTC market with customizable terms
- **Credit Risk**: Minimal, as only interest differentials are exchanged, not principal
- **Calculation Method**: Geometric compounding of the overnight rates over the calculation period

### Uses
- Hedging overnight cash rate exposure
- Speculating on RBA monetary policy decisions
- Deriving market expectations of future RBA cash rate movements
- Funding for financial institutions
- Creating term structures of risk-free rates

### Pricing Formula

The fixed rate of an OIS is priced to reflect the expected geometric average of the overnight cash rate over the term of the swap:

$\text{OIS Rate} = \left[\prod_{i=1}^{n}(1 + r_i \times \frac{d_i}{365}) \right]^{\frac{365}{\sum d_i}} - 1$

Where:
- $r_i$ = Overnight cash rate for period $i$
- $d_i$ = Number of days the rate $r_i$ applies
- $n$ = Number of overnight periods

The present value of an OIS can be calculated as:

$\text{PV} = \text{Notional} \times (\text{Fixed Rate} - \text{Realized OIS Rate}) \times \frac{\sum d_i}{365} \times \text{Discount Factor}$

