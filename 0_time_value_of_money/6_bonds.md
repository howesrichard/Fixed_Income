# Bonds
## Bond Valuation

Recall that a bond's value is the present value of all future cash flows, including coupon payments and the face value at maturity.

**Formula:**
$P = \sum_{t=1}^{n} \frac{C}{(1+r)^t} + \frac{F}{(1+r)^n}$

Where:
- P = Bond price
- C = Coupon payment
- F = Face value (par value)
- r = Required yield (market interest rate)
- n = Number of periods to maturity

For bonds with semiannual coupon payments (common in the US), the formula becomes:

$P = \sum_{t=1}^{2n} \frac{C/2}{(1+r/2)^t} + \frac{F}{(1+r/2)^{2n}}$

## Relationship between Price and Yield

Price and yield  are inversely related and the relationship is non-linear as shown below.

![Bond Price vs Yield Chart](images\bond_price_yield_chart.png)

## Macaulay Duration Formula

### Definition
Macaulay Duration represents the weighted average time until a bond's cash flows are received, with the weights being the present value of each cash flow relative to the bond's price.

### Formula

The Macaulay Duration (D) is calculated using the following formula:

$$
D = \frac{\sum_{t=1}^{n} \frac{t \times C_t}{(1+y)^t}}{\sum_{t=1}^{n} \frac{C_t}{(1+y)^t}}
$$

Where:
- $D$ = Macaulay Duration (in years)
- $t$ = Time period when the cash flow occurs
- $C_t$ = Cash flow at time t (coupon payment or principal)
- $y$ = Yield to maturity (in decimal form)
- $n$ = Total number of periods until maturity

#### Alternative Representation

The formula can also be written as:

$$
D = \frac{\sum_{t=1}^{n} t \times PV(C_t)}{P}
$$

Where:
- $PV(C_t)$ = Present value of the cash flow at time t
- $P$ = Price of the bond (which equals the sum of all present values of future cash flows)

#### Example Calculation

For a 3-year bond with annual coupon payments of $50, a face value of $1,000, and a yield to maturity of 5%:

| Time (t) | Cash Flow ($C_t$) | Discount Factor $(1+y)^{-t}$ | PV of Cash Flow | t × PV of Cash Flow |
|----------|------------------|------------------------|-----------------|---------------------|
| 1        | $50              | 0.9524                 | $47.62          | $47.62              |
| 2        | $50              | 0.9070                 | $45.35          | $90.70              |
| 3        | $1,050           | 0.8638                 | $907.03         | $2,721.08           |
|          |                  | Sum:                   | $1,000.00       | $2,859.40           |

Macaulay Duration = $2,859.40 / $1,000.00 = 2.86 years

### Macaulay Duration as a Weighted Average

The Macaulay Duration represents the weighted average time until cash flows are received, with weights proportional to the present value of each cash flow. This can be seen directly from the formula:

1. Each time period $t$ is weighted by: $\frac{CF_t \times (1+y/m)^{-t}}{P}$
2. These weights sum to 1 since $P = \sum_{t=1}^{n} CF_t \times (1+y/m)^{-t}$
3. The weighted sum $\sum_{t=1}^{n} t \times \frac{CF_t \times (1+y/m)^{-t}}{P}$ gives us the average time, weighted by present value

Intuitively, this measures how long, on average, you must wait to receive the bond's payments. Cash flows that contribute more to the bond's present value (larger or earlier payments) have greater influence on this average.

So a Macaulay Duration of 2.86 years means that the bond's weighted-average time to receive all cash flows is 2.86 years.  

### Macauley Duration as a measure of interest rate risk

This provides a measure of the bond's interest rate risk.   But the duration measure is not a perfect measure of interest rate sensitivity.   For that we need to modify it.

## Macaulay Modified Duration

### The Need for Modification

Macaulay Duration by itself measures the weighted average time until a bond's cash flows are received. While this is useful for understanding the effective time horizon of a bond, it doesn't directly tell us how the bond price will react to yield changes.

The modification to Macaulay Duration is necessary for several key reasons:

1. **Non-linear relationship**: Bond prices and yields have an inverse but convex (curved) relationship, not a linear one. This means the relationship between percentage changes is not one-to-one.

2. **Different compounding frequencies**: Bonds can have different compounding periods (annual, semi-annual, etc.), and this affects how price changes in response to yield changes.

3. **Scaling factor needed**: To convert from a time measure (Macaulay Duration) to a price sensitivity measure, we need to apply a scaling factor based on the current yield environment.

### The Modification Formula

The modification involves dividing the Macaulay Duration by a factor of (1 + y/n):

$$\text{Modified Duration} = \frac{\text{Macaulay Duration}}{(1 + \frac{y}{n})}$$

Where:
- y = yield to maturity (in decimal form)
- n = number of compounding periods per year

## Practical Significance

This adjustment gives us a measure that directly approximates the percentage change in bond price for a 1% (100 basis point) change in yield. For example, a Modified Duration of 5 means that if interest rates increase by 1%, the bond's price will decrease by approximately 5%.

The modification becomes increasingly important when:
- Interest rates are high
- Compounding periods are more frequent than annual
- More precise risk management is required

Without this modification, Macaulay Duration would overestimate the price sensitivity of bonds in most real-world scenarios.

## Mathematical Relationship to Price Sensitivity

The relationship between Modified Duration and bond price changes can be expressed as:

$$\frac{\Delta P}{P} \approx -\text{Modified Duration} \times \Delta y$$

Where:
- ΔP/P = percentage change in bond price
- Δy = change in yield (in decimal form)

This formula shows why Modified Duration is the more practical metric for bond portfolio managers and fixed income investors who need to measure and manage interest rate risk.

### Derivation of Modified Duration from Macaulay Duration

To derive Modified Duration, we start by examining how a bond's price changes with respect to yield:

1. First, we take the price function of a bond: $P = \sum_{t=1}^{n} CF_t \times (1+y/m)^{-t}$

2. Differentiating with respect to $y$:
   $$\frac{dP}{dy} = \sum_{t=1}^{n} CF_t \times (-t) \times (1+y/m)^{-t-1} \times \frac{1}{m}$$

3. Rearranging:
   $$\frac{dP}{dy} = -\frac{1}{m} \times \sum_{t=1}^{n} t \times CF_t \times (1+y/m)^{-t} \times \frac{1}{1+y/m}$$

4. Factoring out $P$ and $D_{mac}$:
   $$\frac{dP}{dy} = -\frac{P \times D_{mac}}{1+y/m} \times \frac{1}{m}$$

5. The percentage change in price is:
   $$\frac{1}{P} \times \frac{dP}{dy} = -\frac{D_{mac}}{1+y/m} \times \frac{1}{m} = -\frac{D_{mod}}{m}$$

This gives us the Modified Duration: $D_{mod} = \frac{D_{mac}}{1+y/m}$