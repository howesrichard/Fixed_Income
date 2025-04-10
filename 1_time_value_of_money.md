# Time Value of Money: Foundational Principles in Finance

## Introduction

The time value of money (TVM) is one of the most fundamental concepts in finance. It recognizes that money available today is worth more than the same amount in the future due to its potential earning capacity. This principle forms the basis for virtually all financial decisions, from personal savings to corporate investment strategies.

## Present Value (PV)

The present value represents the current worth of a future sum of money, given a specified rate of return.

**Formula:**
$PV = \frac{FV}{(1+r)^n}$

Where:
- PV = Present Value
- FV = Future Value
- r = Interest rate per period
- n = Number of periods

**Example:**
If you expect to receive $1,000 in 5 years and the interest rate is 5% per year, the present value would be:

$PV = \frac{1,000}{(1+0.05)^5} = \frac{1,000}{1.2763} = \$783.53$

## Future Value (FV)

Future value calculates what an investment today will be worth at a future date, given a specific interest rate.

**Formula:**
$FV = PV \times (1+r)^n$

**Example:**
If you invest $1,000 today at an annual interest rate of 5% for 5 years, the future value would be:

$FV = 1,000 \times (1+0.05)^5 = 1,000 \times 1.2763 = \$1,276.30$

## Present Value of an Annuity

An annuity is a series of equal payments made at equal intervals.

### Present Value of an Ordinary Annuity

Payments occur at the end of each period.

**Formula:**
$PV_{annuity} = PMT \times \frac{1 - (1+r)^{-n}}{r}$

Where:
- PMT = Payment per period
- r = Interest rate per period
- n = Number of periods

**Example:**
The present value of $100 paid at the end of each year for 5 years, with an interest rate of 5% per year:

$PV_{annuity} = 100 \times \frac{1 - (1+0.05)^{-5}}{0.05} = 100 \times 4.3295 = \$432.95$

### Present Value of an Annuity Due

Payments occur at the beginning of each period.

**Formula:**
$PV_{annuity\ due} = PMT \times \frac{1 - (1+r)^{-n}}{r} \times (1+r) = PV_{ordinary\ annuity} \times (1+r)$

## Future Value of an Annuity

### Future Value of an Ordinary Annuity

**Formula:**
$FV_{annuity} = PMT \times \frac{(1+r)^n - 1}{r}$

**Example:**
If you save $100 at the end of each year for 5 years, earning 5% annually:

$FV_{annuity} = 100 \times \frac{(1+0.05)^5 - 1}{0.05} = 100 \times 5.5256 = \$552.56$

### Future Value of an Annuity Due

**Formula:**
$FV_{annuity\ due} = PMT \times \frac{(1+r)^n - 1}{r} \times (1+r) = FV_{ordinary\ annuity} \times (1+r)$

## Bond Valuation

A bond's value is the present value of all future cash flows, including coupon payments and the face value at maturity.

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

## Compounding Periods

The frequency of compounding affects the effective annual rate (EAR) and the future value of investments.

### Periodic Compounding

When interest is compounded m times per year:

**Effective Annual Rate (EAR):**
$EAR = \left(1 + \frac{r}{m}\right)^m - 1$

Where:
- r = Nominal annual interest rate
- m = Number of compounding periods per year

**Future Value with Periodic Compounding:**
$FV = PV \times \left(1 + \frac{r}{m}\right)^{m \times n}$

**Examples of Compounding:**
- Annual compounding (m=1): $FV = PV \times (1 + r)^n$
- Semiannual compounding (m=2): $FV = PV \times \left(1 + \frac{r}{2}\right)^{2n}$
- Quarterly compounding (m=4): $FV = PV \times \left(1 + \frac{r}{4}\right)^{4n}$
- Monthly compounding (m=12): $FV = PV \times \left(1 + \frac{r}{12}\right)^{12n}$
- Daily compounding (m=365): $FV = PV \times \left(1 + \frac{r}{365}\right)^{365n}$

### Continuous Compounding

Continuous compounding represents the theoretical limit as the number of compounding periods approaches infinity.

**Formula for Future Value with Continuous Compounding:**
$FV = PV \times e^{rt}$

Where:
- e = Mathematical constant approximately equal to 2.71828
- r = Nominal annual interest rate
- t = Time in years

**Effective Annual Rate with Continuous Compounding:**
$EAR = e^r - 1$

**Example:**
$1,000 invested for 5 years at a nominal rate of 5% with continuous compounding:

$FV = 1,000 \times e^{0.05 \times 5} = 1,000 \times e^{0.25} = 1,000 \times 1.2840 = \$1,284.00$

Compare this to annual compounding: $1,000 \times (1+0.05)^5 = \$1,276.30$

## Practical Applications

These time value of money principles apply to numerous financial decisions:

1. Investment evaluation (NPV, IRR)
2. Loan amortization
3. Retirement planning
4. Insurance premium calculations
5. Real estate valuation
6. Corporate financial planning

Understanding these fundamental concepts provides the foundation for making informed financial decisions in both personal and professional contexts.