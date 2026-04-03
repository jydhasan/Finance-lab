<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/41f78a4d-ff06-4bfd-9a67-0cbd5ffbe7c7" />



# 💹 Finance Lab

An interactive, browser-based finance toolkit — no backend, no dependencies beyond Chart.js. Open the HTML file and start exploring.

![Finance Lab Preview](https://img.shields.io/badge/status-active-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![HTML](https://img.shields.io/badge/built%20with-HTML%2FJS-orange)

---

## ✨ Features

Finance Lab bundles **11 interactive tools** into a single dark-themed dashboard. Each tool is built around a core concept in finance — see the [Theory Guide](#-theory-guide) below for full explanations.

| # | Tool | What it does |
|---|---|---|
| 1 | **Compound Interest** | Explore exponential growth with variable compounding frequency and monthly top-ups |
| 2 | **Simple Interest** | Calculate SI and compare it side-by-side with compound growth |
| 3 | **Annuity** | Compute FV and PV for Ordinary Annuity and Annuity Due |
| 4 | **Discounting / PV** | Visualize how a future cash amount erodes to present value |
| 5 | **Capital Budgeting** | Input custom cash flows to get NPV, IRR, Payback Period, and Profitability Index |
| 6 | **Loan / EMI** | Break down monthly EMI and see yearly principal vs interest split |
| 7 | **CAPM & Beta** | Calculate required return using the Capital Asset Pricing Model |
| 8 | **Bond / YTM** | Price a bond and see how price changes with market rates |
| 9 | **Break-Even** | Find the unit/revenue threshold where a business covers all costs |
| 10 | **Currency Converter** | Convert between 20 major currencies with a quick reference table |
| 11 | **Portfolio Tracker** | Track weighted returns across multiple assets in a portfolio |

---

## 🚀 Getting Started

No installation needed. Just open the file in any modern browser.

```bash
git clone https://github.com/your-username/finance-lab.git
cd finance-lab
open finance_lab_full.html   # macOS
# or just double-click the file on Windows/Linux
```

---

## 📚 Theory Guide

### 1. Compound Interest

**What it is:** Compound interest means you earn interest not just on your original principal, but also on the interest you've already earned. Over time, this creates exponential growth — famously called "the eighth wonder of the world."

**How it works:** Each period, your balance grows by a percentage. That larger balance then grows again next period, and so on. The more frequently interest compounds (monthly vs annually), the faster your money grows.

**Formula:**
```
FV = P × (1 + r/n)^(n×t)
```
where `P` = principal, `r` = annual rate, `n` = compounding periods per year, `t` = years.

With monthly contributions added:
```
FV = P × (1 + r/n)^(n×t)  +  M × [(1 + r/12)^(12t) - 1] / (r/12)
```

**Example:** $10,000 at 7% for 20 years → grows to ~$38,697. Add $200/month → over $104,000.

**Real-world use:** Savings accounts, fixed deposits, retirement funds, mutual funds.

---

### 2. Simple Interest

**What it is:** Simple interest is calculated only on the original principal — the interest does not compound. It grows in a straight line, not a curve.

**Formula:**
```
SI = P × r × t
Final Balance = P × (1 + r × t)
```

**Compared to compound:** SI always produces less than CI over time because there is no "interest on interest." The gap widens significantly over longer periods.

**Example:** $10,000 at 7% for 10 years → SI gives $17,000, CI gives $19,672. Over 30 years, the gap becomes enormous.

**Real-world use:** Short-term loans, car loans in some countries, personal lending between individuals.

---

### 3. Annuity

**What it is:** An annuity is a series of equal, regular payments made over a fixed period. It answers questions like: "If I invest $1,000 every year for 10 years at 6%, how much will I have?" or "What is that stream of payments worth today?"

**Two types:**
- **Ordinary Annuity** — payments are made at the *end* of each period (most common)
- **Annuity Due** — payments are made at the *beginning* of each period (slightly more valuable)

**Formulas:**

Future Value (Ordinary):
```
FV = PMT × [(1 + r)^n - 1] / r
```

Present Value (Ordinary):
```
PV = PMT × [1 - (1 + r)^-n] / r
```
Multiply both by `(1 + r)` for Annuity Due.

**Example:** $1,000/year for 10 years at 6% → FV ≈ $13,181, PV ≈ $7,360.

**Real-world use:** Pension payments, insurance payouts, loan repayment schedules, lease agreements, savings plans.

---

### 4. Discounting / Present Value

**What it is:** Discounting is the reverse of compounding. It answers: "How much is a future sum of money worth *right now*?" The core idea is that money today is worth more than the same amount in the future — because today's money can be invested and grow.

**This concept is called the Time Value of Money (TVM).**

**Formula:**
```
PV = FV / (1 + r)^t
```
The term `1 / (1 + r)^t` is called the **Discount Factor**.

**Example:** $50,000 received 10 years from now, at an 8% discount rate, is worth only ~$23,160 today. A high discount rate or long time horizon rapidly shrinks present value.

**Real-world use:** Valuing future cash flows in investments, comparing financial options that pay out at different times, valuing companies (DCF analysis).

---

### 5. Capital Budgeting

**What it is:** Capital budgeting helps businesses decide whether a long-term investment (a project, machine, expansion) is financially worthwhile. You compare the upfront cost against the future cash flows it generates.

**Key metrics:**

**Net Present Value (NPV)** — the total present value of all cash flows, including the initial outflow. If NPV > 0, the project creates value.
```
NPV = Σ [ CFt / (1 + r)^t ]
```

**Internal Rate of Return (IRR)** — the discount rate at which NPV = 0. If IRR > your cost of capital (WACC), the project is worth doing.

**Payback Period** — how many years until the cumulative cash flows recover the initial investment. Simple but ignores time value.

**Profitability Index (PI)** — NPV per dollar invested. PI > 1 means the project adds value.
```
PI = (NPV + Initial Investment) / Initial Investment
```

**Example:** Invest $50,000, receive $15,000/year for 5 years at 10% WACC → NPV ≈ +$6,860, IRR ≈ 15.2%, Payback = 4 years.

**Real-world use:** Business investment decisions, project evaluation, corporate finance, startup funding analysis.

---

### 6. Loan / EMI

**What it is:** A loan EMI (Equated Monthly Installment) is a fixed amount paid every month to repay a loan over a set tenure. Each payment covers both interest for that month and a portion of the principal. Early payments are mostly interest; later payments are mostly principal.

**Formula:**
```
EMI = P × r × (1 + r)^n / [(1 + r)^n - 1]
```
where `P` = loan amount, `r` = monthly interest rate (annual rate ÷ 12), `n` = total months.

**Total interest paid** = (EMI × n) − P. For long-tenure, high-rate loans, total interest can exceed the original loan amount.

**Example:** $100,000 loan at 8% for 20 years → EMI ≈ $836/month, total paid ≈ $200,640, total interest ≈ $100,640 — nearly doubling the original amount.

**Real-world use:** Home loans, car loans, personal loans, student loans, business financing.

---

### 7. CAPM & Beta

**What it is:** The Capital Asset Pricing Model (CAPM) is used to calculate the *expected return* of an investment based on its systematic risk (Beta). It defines the relationship between risk and return.

**Beta (β)** measures how much an asset moves relative to the overall market:
- β = 1.0 → moves exactly with the market
- β > 1.0 → more volatile than the market (higher risk, higher expected return)
- β < 1.0 → less volatile (defensive, lower expected return)
- β = 0 → no correlation with market (e.g., cash)
- β < 0 → moves opposite to market (e.g., gold in some periods)

**Formula:**
```
Re = Rf + β × (Rm − Rf)
```
where `Rf` = risk-free rate, `Rm` = expected market return, `(Rm − Rf)` = market risk premium.

**The Security Market Line (SML)** is a graph of this equation — it shows the required return for any given beta. Assets above the SML are undervalued; below it are overvalued.

**Example:** Rf = 4%, Rm = 10%, β = 1.2 → Re = 4% + 1.2 × (10% − 4%) = **11.2%**

**Real-world use:** Valuing stocks, setting required return hurdles, portfolio construction, cost of equity in WACC calculations.

---

### 8. Bond Pricing & YTM

**What it is:** A bond is a fixed-income instrument where the issuer promises to pay regular **coupon payments** and return the **face value** at maturity. Bond pricing is about finding what that promise is worth today, given current market interest rates.

**Key relationship: bond prices and interest rates move in opposite directions.**
- If market rates rise above the coupon rate → bond price falls (trades at a **discount**)
- If market rates fall below the coupon rate → bond price rises (trades at a **premium**)

**Bond Price Formula:**
```
Price = C × [1 - (1 + YTM)^-n] / YTM  +  FV / (1 + YTM)^n
```
where `C` = annual coupon payment, `YTM` = yield to maturity (market rate), `n` = years to maturity.

**Current Yield** = Annual Coupon / Current Price (approximate return, ignores capital gain/loss at maturity).

**Yield to Maturity (YTM)** = total annualized return if held to maturity, accounting for all coupons and the difference between purchase price and face value.

**Example:** Face value $1,000, coupon 6%, 10 years, YTM 8% → Price ≈ $865.80 (discount, since market rate > coupon).

**Real-world use:** Government bonds (T-bills, treasury bonds), corporate bonds, debentures, fixed income portfolio management.

---

### 9. Break-Even Analysis

**What it is:** Break-even analysis finds the point where total revenue equals total costs — the threshold at which a business neither makes a profit nor a loss. Below this point, every unit sold increases the loss. Above it, every unit contributes to profit.

**Key concepts:**
- **Fixed Costs (FC)** — costs that don't change with output (rent, salaries, insurance)
- **Variable Costs (VC)** — costs per unit that scale with output (materials, packaging)
- **Contribution Margin (CM)** = Selling Price − Variable Cost per unit

**Formulas:**
```
BEP (Units)      = Fixed Costs / Contribution Margin
BEP (Revenue)    = BEP Units × Selling Price
Profit / Loss    = (Units Sold × CM) − Fixed Costs
Margin of Safety = (Actual Units − BEP Units) / Actual Units × 100%
```

**Margin of Safety** shows how far above break-even you are — a higher margin means the business can absorb a larger drop in sales before making a loss.

**Example:** FC = $50,000, VC = $30/unit, SP = $50/unit → CM = $20, BEP = 2,500 units. Sell 5,000 → Profit = $50,000, Margin of Safety = 50%.

**Real-world use:** Startup viability analysis, pricing decisions, production planning, cost management.

---

### 10. Currency Converter

**What it is:** A currency converter translates an amount from one currency to another using exchange rates. Exchange rates represent the price of one currency in terms of another and fluctuate constantly based on trade, inflation, interest rates, and market sentiment.

**Formula:**
```
Converted Amount = Input Amount × (Target Rate / Base Rate)
```
All rates in this tool are quoted against USD (e.g., 1 USD = 110 BDT, 1 USD = 83.5 INR).

**Supported currencies (20):** USD, EUR, GBP, JPY, BDT, INR, CAD, AUD, CHF, CNY, SGD, AED, MYR, THB, KRW, HKD, SAR, TRY, ZAR, BRL.

> **Note:** Rates in this tool are approximate and for educational use. For live rates, connect to a free FX API such as [ExchangeRate-API](https://www.exchangerate-api.com/).

**Real-world use:** International payments, forex trading, travel budgeting, import/export pricing, remittances.

---

### 11. Portfolio Return Tracker

**What it is:** A portfolio is a collection of investments (stocks, bonds, real estate, cash, etc.) held together to spread risk. Portfolio return is the weighted average of the individual returns of each asset, where the weight reflects what fraction of the total money is invested in that asset.

**Formula:**
```
Portfolio Return = Σ (Weight_i × Return_i)
```
where weights must sum to 100%.

**Contribution** of each asset = its weight × its individual return. An asset with a high weight and a high return contributes the most to the overall portfolio.

**Diversification** means spreading investments across assets that don't move together (low correlation), so a loss in one is offset by gains in another. This tool tracks return contribution — risk and correlation analysis (standard deviation, Sharpe ratio, covariance matrix) is planned in the roadmap.

**Example:** 40% Stocks (12%) + 30% Bonds (6%) + 20% Real Estate (9%) + 10% Cash (5%):
```
Portfolio Return = (0.40×12) + (0.30×6) + (0.20×9) + (0.10×5)
                = 4.8 + 1.8 + 1.8 + 0.5
                = 8.9%
```

**Real-world use:** Personal investment tracking, fund management, retirement planning, asset allocation strategy.

---

## 🛠️ Built With

- **Vanilla HTML / CSS / JavaScript** — zero build tooling
- **[Chart.js 4.4](https://www.chartjs.org/)** — loaded from CDN
- **[Fraunces](https://fonts.google.com/specimen/Fraunces) + [DM Mono](https://fonts.google.com/specimen/DM+Mono)** — Google Fonts

---

## 📁 Project Structure

```
finance-lab/
├── finance_lab_full.html   # The entire app — single file
└── README.md
```

---

## 🗺️ Roadmap

- [ ] Portfolio risk (standard deviation, Sharpe ratio, correlation matrix)
- [ ] WACC calculator
- [ ] Dividend Discount Model (DDM)
- [ ] Export results to PDF / CSV
- [ ] Dark / Light theme toggle
- [ ] Mobile-optimized layout

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first.

1. Fork the repo
2. Create your branch (`git checkout -b feature/new-tool`)
3. Commit your changes (`git commit -m 'Add WACC calculator'`)
4. Push and open a Pull Request

---

## 📄 License

[MIT](LICENSE) — free to use, modify, and distribute.

---

> Built with ☕ and a love for finance. If this helped you, give it a ⭐!
