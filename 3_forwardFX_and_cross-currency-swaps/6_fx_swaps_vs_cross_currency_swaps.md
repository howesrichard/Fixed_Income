# FX Swaps vs. Cross-Currency Swaps

These two instruments serve different purposes in the foreign exchange markets and have distinct structures, despite their similar names.

## FX Swaps

### Structure
- **Initial Exchange**: Exchange of two currencies at the current spot rate
- **Terminal Exchange**: Reversal of the initial exchange at a pre-agreed forward rate
- **No Interim Interest Payments**: No periodic interest exchanges during the life of the swap
- **Maturities**: Typically short-term (from overnight to 1 year, occasionally longer)

### Key Features
- **Purpose**: Primarily used for short-term liquidity management and hedging
- **Pricing**: Determined by the interest rate differential between the two currencies
- **Interest Component**: Embedded in the forward points (difference between forward and spot rates)
- **Principal Risk**: Minimal as only the difference between spot and forward rates is at risk
- **Documentation**: Typically executed under an ISDA Master Agreement but as a single transaction

## Cross-Currency Swaps

### Structure
- **Initial Exchange**: Exchange of principal amounts in two different currencies at current spot rate
- **Interim Interest Payments**: Regular exchange of interest payments (fixed or floating) throughout the life of the swap
- **Terminal Exchange**: Re-exchange of principal amounts at maturity at the same initial exchange rate
- **Maturities**: Medium to long-term (typically 2-30 years)

### Key Features
- **Purpose**: Long-term funding, asset-liability management, hedging long-term FX exposures
- **Pricing**: Combined function of interest rate differentials and the cross-currency basis spread
- **Interest Component**: Explicit periodic exchanges (usually quarterly or semi-annually)
- **Principal Risk**: Full principal amount is at risk
- **Documentation**: Always executed under an ISDA Master Agreement with more detailed terms

## Key Differences Table

| Feature | FX Swap | Cross-Currency Swap |
|---------|---------|---------------------|
| Interim Cash Flows | None | Periodic interest payments |
| Interest Rates | Implicit in forward points | Explicitly exchanged |
| Basis Spread | Not applicable | Explicitly priced component |
| Maturity | Short-term (typically < 1 year) | Longer-term (2-30 years) |
| Accounting | Off-balance sheet (typically) | On-balance sheet |
| Credit Risk | Limited to mark-to-market | Full principal plus interest |
| Primary Users | Corporate treasuries, banks' short-term funding | Issuers of foreign debt, long-term investors |
| Capital Treatment | Lower regulatory capital requirements | Higher regulatory capital requirements |
| Currency Risk | Hedges short-term exposures | Hedges long-term exposures |

## Market and Pricing Relationship

The pricing relationship between FX swaps and cross-currency swaps is interconnected:

1. Short-dated cross-currency swap rates are influenced by FX swap rates
2. The term structure of cross-currency basis spreads extends the FX swap implied basis to longer tenors
3. During market stress, dislocations often appear first in FX swap markets before affecting cross-currency swap pricing

In practice, when discussing "basis swap spreads" in the context of CIP deviations, cross-currency basis swaps provide the market-standard measure for longer tenors, while FX swap implied bases are the reference for shorter tenors.