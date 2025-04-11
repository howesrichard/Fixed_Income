# Credit Exposure and Capital Requirements for Interest Rate Swaps

## 1. Credit Exposure Calculation for Interest Rate Swaps

Credit exposure on an interest rate swap refers to the risk of loss if a counterparty defaults. It consists of two primary components:

### Current Exposure (CE)
- Also known as the Mark-to-Market (MtM) or Replacement Cost
- Represents the cost to replace the swap at current market rates if the counterparty defaults now
- Calculated as the present value of expected future cash flows
- Can be positive or negative (only positive values represent credit risk)

### Potential Future Exposure (PFE)
- Estimates potential future increase in exposure due to market movements
- Typically calculated using statistical methods:
  - Monte Carlo simulations
  - Historical simulation
  - Parametric VaR-based approaches
- Considers factors like:
  - Volatility of interest rates
  - Remaining maturity
  - Notional amount
  - Payment frequency

### Expected Exposure (EE)
- The time-weighted average of expected exposures over the life of the swap
- Used in pricing and risk management calculations

### Credit Exposure Profile
The total credit exposure is often represented as a time profile showing how exposure evolves over the life of the swap. For interest rate swaps:
- Exposure typically peaks in the middle of the swap's life
- Declines toward maturity as fewer payments remain
- Is affected by the shape of the yield curve

## 2. Capital Consumption Calculation for Interest Rate Swaps

Banks must hold regulatory capital against swap exposures based on frameworks like Basel III:

### Standardized Approach
- Applies predefined risk weights based on:
  - Counterparty type (e.g., corporate, bank, sovereign)
  - Maturity of the swap
  - Underlying reference rate
- Exposure calculation: Exposure = Current Exposure + (α × Notional × Maturity Factor)
  - Where α varies based on the nature of the swap

### Internal Models Method (IMM)
- Uses bank's internal models (with regulatory approval)
- Typically involves Monte Carlo simulations
- Calculates Exposure at Default (EAD) considering:
  - Expected Positive Exposure (EPE)
  - Effective Expected Positive Exposure (EEPE)
- Risk-weighted assets (RWA) = EAD × Risk Weight × 12.5

#### Monte Carlo Simulation for EAD Calculation
The Monte Carlo simulation process for calculating EAD under IMM typically follows these steps:

1. **Risk Factor Identification**:
   - Identify relevant market risk factors (e.g., yield curves, volatility surfaces)
   - Calibrate stochastic models for each risk factor
   - Specify correlations between risk factors

2. **Scenario Generation**:
   - Generate thousands of random paths for each risk factor
   - Typically use time steps of 1-2 weeks over the life of the swap
   - Consider various stochastic models:
     - Hull-White or Vasicek models for short rates
     - Heath-Jarrow-Morton (HJM) framework for yield curves
     - SABR or Heston models for volatility

3. **Revaluation**:
   - For each time step and each scenario, revalue the swap
   - Calculate net present value (NPV) under each scenario
   - Consider only positive exposures (max(NPV, 0)) as negative values represent no credit risk

4. **Exposure Profile Calculation**:
   - Calculate Expected Exposure (EE) at each time point as the average of positive exposures across scenarios
   - Apply a non-decreasing constraint to generate Effective Expected Exposure (EEE)
   - Calculate Effective Expected Positive Exposure (EEPE) as the time-weighted average of EEE over one year

5. **EAD Determination**:
   - EAD = α × EEPE
   - Where α is a supervisory factor (typically 1.4)
   - This factor accounts for general wrong-way risk, model risk, and other factors

6. **Risk Mitigation Factors**:
   - Incorporate collateral agreements with appropriate margin periods of risk
   - Account for netting sets and legally enforceable netting agreements
   - Apply specific wrong-way risk adjustments where applicable

7. **Stress Testing and Backtesting**:
   - Apply stressed market conditions to ensure robustness
   - Backtest model results against historical data
   - Validate model assumptions and parameters regularly

Banks must demonstrate to regulators that their IMM models meet strict statistical and risk management standards before approval is granted. The models must be integrated with the bank's day-to-day risk management processes ("use test") and undergo regular validation and stress testing.

### SA-CCR (Standardized Approach for Counterparty Credit Risk)
- Replaced the older Current Exposure Method (CEM)
- More risk-sensitive than previous standardized approaches
- Formula: EAD = alpha × (RC + PFE)
  - RC = Replacement Cost
  - PFE = Potential Future Exposure
  - alpha = 1.4 (supervisory factor)

### Credit Valuation Adjustment (CVA)
- Additional capital charge for potential mark-to-market losses due to deterioration in counterparty creditworthiness
- Calculated based on:
  - Counterparty's credit spread
  - Expected positive exposure profile
  - Maturity of exposures

### Capital Calculation
1. Risk-Weighted Assets (RWA) = EAD × Risk Weight
2. Capital Requirement = RWA × Capital Ratio (typically 8% minimum under Basel III)

## 3. Risk Mitigation Techniques

Several techniques can reduce credit exposure and capital requirements:

### Netting Agreements
- Allow offsetting of positive and negative exposures with the same counterparty
- Significantly reduce gross exposure
- Recognized in capital calculations when legally enforceable

### Collateral Agreements
- Credit Support Annexes (CSAs) requiring posting of collateral
- Reduces both current and potential exposure
- Affects capital calculations through reduced EAD

### Central Clearing
- Novation to a central counterparty (CCP)
- Lower capital requirements for centrally cleared transactions
- Standardized margining and default management

### Portfolio Compression
- Reduces gross notional exposure by eliminating offsetting positions
- Decreases operational and capital costs

## 4. Central Clearing Requirements Post-GFC

### Background and Motivation
The 2008 Global Financial Crisis (GFC) exposed significant weaknesses in the over-the-counter (OTC) derivatives market, including:
- Lack of transparency
- Insufficient collateralization
- Complex interconnectedness between financial institutions
- Difficulty in assessing counterparty risk

The failure of Lehman Brothers and the near-collapse of AIG highlighted how bilateral OTC derivatives could create systemic risk through contagion effects.

### Regulatory Response
In response to these issues, the G20 leaders agreed at the 2009 Pittsburgh Summit to implement reforms requiring:
- All standardized OTC derivatives to be cleared through central counterparties (CCPs)
- OTC derivative contracts to be reported to trade repositories
- Higher capital requirements for non-centrally cleared derivatives

### Key Legislation
These requirements were implemented through:
- **United States**: Dodd-Frank Wall Street Reform and Consumer Protection Act (2010)
- **European Union**: European Market Infrastructure Regulation (EMIR)
- **Other jurisdictions**: Similar regulations aligned with G20 commitments

### Central Clearing Mechanism
Under central clearing:
1. The original bilateral contract is replaced with two contracts with the CCP
2. The CCP becomes the counterparty to both original parties
3. Counterparty risk is transferred to the CCP
4. The CCP collects initial and variation margin to manage risk
5. Default funds provide additional protection if a clearing member defaults

### Entities Subject to Clearing Mandates

#### United States (CFTC/SEC regulations)
- **Swap Dealers and Major Swap Participants**: Required to clear all mandated swaps
- **Financial Entities**: Including:
  - Commodity pools
  - Private funds
  - Employee benefit plans
  - Banking entities
  - Insurance companies
- **Exemptions**: 
  - End-users using swaps to hedge commercial risk
  - Small financial institutions (total assets under $10 billion)
  - Certain intragroup transactions

#### European Union (EMIR)
- **Financial Counterparties (FCs)**: Including:
  - Banks and investment firms
  - Insurance companies
  - UCITS funds and their managers
  - Alternative investment funds
  - Pension schemes (with phase-in periods)
- **Non-Financial Counterparties above threshold (NFC+)**:
  - Entities whose positions exceed specified clearing thresholds
  - Thresholds vary by asset class (e.g., €1 billion for interest rate derivatives)
- **Exemptions**:
  - Non-Financial Counterparties below threshold (NFC-)
  - Certain intragroup transactions
  - Pension schemes (temporary)

### Products Subject to Clearing
- **Interest Rate Swaps**: 
  - Fixed-to-floating swaps in major currencies
  - Forward Rate Agreements
  - Overnight Index Swaps
  - Basis swaps
- **Credit Default Swaps**:
  - Certain index CDS contracts
- **Requirements vary** by jurisdiction and continue to expand

### Capital Implications
- **Centrally Cleared Swaps**: 
  - Lower risk weights (typically 2-4%)
  - Reduced capital requirements
  - Preferential treatment under leverage ratio calculations
- **Non-Centrally Cleared Swaps**:
  - Higher capital requirements
  - Additional margin requirements
  - Higher CVA capital charges

### Challenges and Ongoing Developments
- Fragmentation of liquidity across CCPs
- Concentration of risk in CCPs (creating new "too big to fail" entities)
- Cross-border recognition and equivalence determinations
- Balancing risk reduction with market efficiency
- Ongoing calibration of margin and default fund contributions

The central clearing mandate has fundamentally transformed the OTC derivatives market structure, with a significant majority of interest rate swaps now being cleared through CCPs. This has reduced bilateral counterparty risk but created new challenges around CCP resilience, recovery, and resolution.