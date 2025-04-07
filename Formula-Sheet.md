# Actuarial, Statistical, and Financial Formulas Reference Document

---

## Aligned with IFOA Standards

---

## **1. Financial Mathematics**

### **Time Value of Money**

1. **Compound Interest (Accumulation Factor)**

   $$
   FV = PV \cdot (1 + i)^n \quad \text{or} \quad FV = PV \cdot e^{\delta n}
   $$

   - $i$: Annual effective interest rate.
   - $\delta$: Force of interest ($\delta = \ln(1+i)$).

   $$

   $$
2. **Discount Factor**

   $$
   v = \frac{1}{1+i} = e^{-\delta}
   $$
3. **Present Value (PV) of Annuity-Certain**

   - *Annuity-immediate* (payments at end of period):
     $$
     a_{\angl{n}} = \frac{1 - v^n}{i}
     $$
   - *Annuity-due* (payments at start of period):
     $$
     \ddot{a}_{\angl{n}} = \frac{1 - v^n}{d} \quad \text{where } d = \frac{i}{1+i}
     $$
4. **Future Value (FV) of Annuity-Certain**

   $$
   s_{\angl{n}} = \frac{(1+i)^n - 1}{i}, \quad \ddot{s}_{\angl{n}} = \frac{(1+i)^n - 1}{d}
   $$

### Additional Financial Mathematics Formulas

1. **Perpetuity**
    - Annuity-immediate:
        $$
         a_{\langle\infty\rangle} = \frac{1}{i}
        $$
    - Annuity-due:
        $$
         \ddot{a}_{\langle\infty\rangle} = \frac{1}{d}
        $$

2. **Varying Annuities**
    - Increasing Annuity-Immediate:
        $$
        (Ia)_{\angl{n}} = \frac{\ddot{a}_{\angl{n}} - nv^n}{i}
        $$
    - Increasing Annuity-Due:
        $$
        (I\ddot{a})_{\angl{n}} = \frac{\ddot{a}_{\angl{n}} - nv^n}{d}
        $$
3. **Continuous Annuities**
    - Present Value:
        $$
        \bar{a}_{\angl{n}} = \frac{1 - v^n}{\delta}
        $$
    - Future Value:
        $$
        \bar{s}_{\angl{n}} = \frac{(1+i)^n - 1}{\delta}
        $$

---

## **2. Actuarial Mathematics**

### **Life Contingencies**

1. **Present Value of Whole Life Annuity**

   - *Annuity-due* (IFOA notation):
     $$
     \ddot{a}_x = \sum_{k=0}^{\infty} v^k \cdot {}_k p_x
     $$
   - *Continuous annuity*:
     $$
     \bar{a}_x = \int_0^{\infty} v^t \cdot {}_t p_x \, dt
     $$
2. **Present Value of Term Life Insurance**

   $$
   A_{x:\angl{n}}^1 = \sum_{k=0}^{n-1} v^{k+1} \cdot {}_k p_x \cdot q_{x+k}
   $$

   - $q_x$: Probability of death within 1 year for age $x$.
3. **Net Premium Reserve**

   $$
   {}_t V = \ddot{a}_{x+t} - P \cdot \ddot{a}_{x+t:\angl{n-t}}
   $$

   - $P$: Premium payment.
4. **Endowment Insurance**

   $$
   A_{x:\angl{n}} = A_{x:\angl{n}}^1 + v^n \cdot {}_n p_x
   $$
5. **Deferred Life Annuity**

   $$
   {}_m \ddot{a}_x = \sum_{k=m}^{\infty} v^k \cdot {}_k p_x
   $$
6. **Accumulated Cost of Insurance**

   $$
   \bar{A}_x = \int_0^{\infty} v^t \cdot {}_t p_x \cdot \mu_{x+t} \, dt
   $$

### Additional Life Contingencies Formulas

1. **Present Value of Whole Life Insurance**
    - Discrete:
        $$
        A_x = \sum_{k=0}^{\infty} v^{k+1} \cdot {}_k p_x \cdot q_{x+k}
        $$
    - Continuous:
        $$
        \bar{A}_x = \int_0^{\infty} v^t \cdot {}_t p_x \cdot \mu_{x+t} \, dt
        $$
2. **Variance of the Present Value of a Whole Life Insurance**
    $$
    Var(Z) = {}^{2}A_x - (A_x)^2
    $$
    where
    $$
    {}^{2}A_x = \sum_{k=0}^{\infty} v^{2(k+1)} \cdot {}_k p_x \cdot q_{x+k}
    $$
3. **Temporary Life Annuity**
    - Annuity-due:
        $$
        \ddot{a}_{x:\angl{n}} = \sum_{k=0}^{n-1} v^k \cdot {}_k p_x
        $$
    - Continuous:
        $$
        \bar{a}_{x:\angl{n}} = \int_0^n v^t \cdot {}_t p_x \, dt
        $$
4. **m-thly Life Annuities**
    - Annuity-due:
        $$
        \ddot{a}_x^{(m)} \approx \ddot{a}_x - \frac{m-1}{2m}
        $$
5. **m-thly Life Insurance**
    - $$
        A_x^{(m)} \approx A_x + \frac{m-1}{2m}i
        $$

---

### **Mortality and Survival Functions**

1. **Survival Probability**

   $$
   {}_t p_x = e^{-\int_0^t \mu_{x+s} \, ds}
   $$

   - $\mu_x$: Force of mortality.

   $$

   $$
2. **Deferred Mortality Probability**

   $$
   {}_t|_u q_x = {}_t p_x \cdot {}_u q_{x+t}
   $$
3. **Complete Expectation of Life**

   $$
   \mathring{e}_x = \int_0^{\infty} {}_t p_x \, dt
   $$
4. **Select Mortality**

   $$
   {}_t p_{[x]+s} = \frac{l_{x+s+t}}{l_{x+s}}
   $$

### Additional Mortality and Survival Functions

1. **Curtate Expectation of Life**
    $$
    e_x = \sum_{k=1}^{\infty} {}_k p_x = \sum_{k=0}^{\infty} {}_k p_x - 1 = \ddot{a}_x -1
    $$
2. **De Moivre's Law**
    $$
    {}_t p_x = \frac{\omega - x - t}{\omega - x}, \quad 0 \le t \le \omega - x
    $$
    where $\omega$ is the limiting age.
3. **Uniform Distribution of Deaths (UDD)**
    $$
    {}_t p_x = 1 - t \cdot q_x, \quad 0 \le t \le 1
    $$
4. **Mortality Rate**
    $$
    q_x = 1 - p_x
    $$

---

### **Commutation Functions (IFOA)**

1. **Discounted Lives**
   $$
   D_x = v^x l_x
   $$
2. **Accumulated Annuity Factors**
   $$
   N_x = \sum_{k=0}^{\infty} D_{x+k}
   $$
3. **Death Benefit Factors**
   $$
   C_x = v^{x+1} d_x, \quad M_x = \sum_{k=0}^{\infty} C_{x+k}
   $$
4. **Annuity-Due Commutation**
   $$
   \ddot{a}_x = \frac{N_x}{D_x}
   $$
5. **Term Insurance Commutation**
   $$
   A_{x:\angl{n}}^1 = \frac{M_x - M_{x+n}}{D_x}
   $$

### **Additional Commutation Functions**

1. **Immediate Annuity**
    $$
    a_x = \frac{N_{x+1}}{D_x}
    $$
2. **Whole Life Insurance**
    $$
    A_x = \frac{M_x}{D_x}
    $$
3. **Temporary Annuity**
    $$
    \ddot{a}_{x:n} = \frac{N_x - N_{x+n}}{D_x}
    $$

---

## **3. Probability and Statistics**

### **Distributions**

1. **Normal Distribution**
   $$
   X \sim N(\mu, \sigma^2) \Rightarrow f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}
   $$
2. **Binomial Distribution**
   $$
   P(X=k) = \binom{n}{k} p^k (1-p)^{n-k}
   $$
3. **Poisson Distribution**
   $$
   P(X=k) = \frac{\lambda^k e^{-\lambda}}{k!}
   $$
4. **Exponential Distribution**
   $$
   f(x) = \lambda e^{-\lambda x}, \quad x \geq 0
   $$
5. **Gamma Distribution**
   $$
   f(x) = \frac{\beta^\alpha}{\Gamma(\alpha)} x^{\alpha-1} e^{-\beta x}, \quad x \geq 0
   $$

### **Additional Distributions**

1. **Chi-Squared Distribution**
    $$
    f(x; k) = \frac{1}{2^{k/2} \Gamma(k/2)} x^{k/2 - 1} e^{-x/2}
    $$
    where $k$ is the degrees of freedom.
2. **t-Distribution**
    $$
    f(t; \nu) = \frac{\Gamma(\frac{\nu+1}{2})}{\sqrt{\nu\pi}\Gamma(\frac{\nu}{2})} \left(1 + \frac{t^2}{\nu}\right)^{-\frac{\nu+1}{2}}
    $$
    where $\nu$ is the degrees of freedom.
3. **Weibull Distribution**
    $$
    f(x) = \frac{k}{\lambda} \left(\frac{x}{\lambda}\right)^{k-1} e^{-(x/\lambda)^k}, \quad x \geq 0
    $$

---

### **Expectation and Variance**

1. **Law of Total Expectation**
   $$
   E[X] = E[E[X|Y]]
   $$
2. **Variance Formula**
   $$
   \text{Var}(X) = E[X^2] - (E[X])^2
   $$
3. **Covariance**
   $$
   \text{Cov}(X, Y) = E[XY] - E[X]E[Y]
   $$

### **Additional Expectation and Variance Formulas**

1. **Law of Total Variance**
    $$
    Var(X) = E[Var(X|Y)] + Var(E[X|Y])
    $$
2. **Correlation**
    $$
    \rho_{X,Y} = \frac{Cov(X,Y)}{\sigma_X \sigma_Y}
    $$

---

### **Hypothesis Testing**

1. **Z-Test Statistic**
   $$
   Z = \frac{\bar{X} - \mu}{\sigma/\sqrt{n}}
   $$
2. **Chi-Square Test**
   $$
   \chi^2 = \sum \frac{(O_i - E_i)^2}{E_i}
   $$
3. **t-Test Statistic**
   $$
   t = \frac{\bar{X} - \mu}{s/\sqrt{n}}
   $$

### **Additional Hypothesis Testing Formulas**

1. **F-Test Statistic**
    $$
    F = \frac{s_1^2}{s_2^2}
    $$
    where $s_1^2$ and $s_2^2$ are the sample variances of two populations.
2. **p-value**
    *The probability of obtaining test results at least as extreme as the results actually observed during the test, assuming that the null hypothesis is correct.*

---

## **4. Financial Derivatives**

1. **Black-Scholes Option Pricing**
   $$
   C = S_0 N(d_1) - K e^{-rT} N(d_2) $$  
   - $d_1 = \frac{\ln(S_0/K) + (r + \sigma^2/2)T}{\sigma \sqrt{T}}$, $d_2 = d_1 - \sigma \sqrt{T}$.
   $$
2. **Duration and Convexity**
   - *Macaulay Duration*:
     $$
     D = \frac{\sum t \cdot PV(CF_t)}{\text{Price}}
     $$
   - *Convexity*:
     $$
     C = \frac{\sum t(t+1) \cdot PV(CF_t)}{(1+i)^2 \cdot \text{Price}}
     $$

### **Additional Financial Derivatives Formulas**

1. **Put-Call Parity**
    $$
    C - P = S_0 - Ke^{-rT}
    $$
2. **Delta**
    $$
    \Delta = \frac{\partial C}{\partial S}
    $$
3. **Gamma**
    $$
    \Gamma = \frac{\partial^2 C}{\partial S^2}
    $$
4. **Vega**
    $$
    \nu = \frac{\partial C}{\partial \sigma}
    $$
5. **Theta**
    $$
    \Theta = \frac{\partial C}{\partial t}
    $$
6. **Rho**
    $$
    \rho = \frac{\partial C}{\partial r}
    $$

---

## **Additional Actuarial Formulas**

1. **Joint Life Annuity**

   $$
   \ddot{a}_{xy} = \sum_{k=0}^{\infty} v^k \cdot {}_k p_{xy}
   $$
2. **Last Survivor Annuity**

   $\ddot{a}_{\overline{xy}}$ = $\ddot{a}_x + \ddot{a}_y - \ddot{a}_{xy}$
3. **Net Premium for Whole Life Insurance**

   $$
   P_x = \frac{A_x}{\ddot{a}_x}
   $$
4. **Thiele’s Differential Equation**

   $$
   \frac{d}{dt} {}_t V = \delta \cdot {}_t V + P - \mu_{x+t} (S - {}_t V)
   $$
5. **Variance of Present Value**

   $$
   \text{Var}(PV) = E[PV^2] - (E[PV])^2
   $$

---

## **5. Regulations and Standards (IFRS 17)**

### **Key Considerations under IFRS 17**

1. **Measurement Models**:
    - **General Measurement Model (GMM)**: Used for most insurance contracts. Requires estimating future cash flows, discounting them, and adding a risk adjustment for non-financial risk.
    - **Premium Allocation Approach (PAA)**: A simplified approach for short-duration contracts or when the GMM is too burdensome. Revenue is recognized as premiums are received, and a simplified liability for incurred claims is used.
    - **Variable Fee Approach (VFA)**: Used for contracts with direct participation features. The CSM is adjusted to reflect the changes in the value of the underlying items.
2. **Contractual Service Margin (CSM)**:
    - Represents the unearned profit that the insurer will recognize over the coverage period.
    - Initially measured as the difference between the fulfillment cash flows and the premiums received.
    - Recognized in profit or loss as services are provided.
3. **Risk Adjustment**:
    - Reflects the compensation an insurer requires for bearing the uncertainty about the amount and timing of future cash flows.
    - Can be determined using techniques such as Confidence Level, Cost of Capital, or Quantile techniques.
4. **Discount Rates**:
    - Should reflect the current market rates and the characteristics of the insurance contract liabilities.
    - Adjustments may be needed to reflect liquidity premiums.
5. **Presentation**:
    - Insurers must present insurance revenue separately from insurance service expenses.
    - Disclose significant judgments and assumptions made in applying IFRS 17.
6. **Transition**:
    - IFRS 17 provides different transition approaches: Full Retrospective, Modified Retrospective, and Fair Value.
    - The choice of transition approach can significantly impact the opening balance sheet.
7. **Relevant Formulas/Concepts for IFRS 17 Calculations**:
    - **Best Estimate of Future Cash Flows**:
        $$
        BE = \sum_{t=1}^{n} \frac{E[CF_t]}{(1+r)^t}
        $$
        Where $E[CF_t]$ is the expected cash flow at time t, and $r$ is the discount rate.
    - **Risk Adjustment (RA)**:
        - Cost of Capital Approach:
            $$
            RA = \sum_{t=1}^{n} \frac{CF_t \times CoC}{(1+r)^t}
            $$
            Where $CoC$ is the cost of capital rate.
    - **Contractual Service Margin (CSM) Amortization**:
        $$
        \text{Amortization} = \frac{\text{CSM at start of period}}{\text{Coverage Units}} \times \text{Coverage Units Provided}
        $$


## **6. IFRS 17 Insurance Contracts**

### **Measurement Models**

1. **General Measurement Model (GMM) - Building Blocks Approach**
   $$
   Insurance\;Contract\;Liability = FCF + RA + CSM
   $$
   where:
   - FCF: Fulfilment Cash Flows
   - RA: Risk Adjustment
   - CSM: Contractual Service Margin

2. **Premium Allocation Approach (PAA) - Liability for Remaining Coverage**
   $$
   LRC = Premiums\;Received - Acquisition\;Cash\;Flows + Amortization
   $$

3. **Loss Component Calculation**
   $$
   Loss\;Component = max(0, -CSM)
   $$

### **Risk Adjustment Calculation Methods**

1. **Cost of Capital Method**
   $$
   RA = \sum_{t=1}^{T} \frac{CoC \cdot SCR_t}{(1 + r_f)^t}
   $$
   - CoC: Cost of Capital rate
   - SCR: Solvency Capital Requirement

2. **Confidence Level Approach**
   $$
   RA = VaR_{\alpha}(Losses) - E(Losses)
   $$
   where α is the confidence level (e.g., 75%)

### **CSM Adjustments**

1. **CSM Roll-forward**
   $$
   CSM_t = CSM_{t-1} \cdot (1 + i) + New\;Business - Amortization \pm Experience\;Adjustments
   $$

2. **Coverage Units Recognition**
   $$
   CSM\;Release = CSM_t \cdot \frac{CU_t}{\sum_{i=t}^{T} CU_i}
   $$
   where CU represents Coverage Units

---

## **7. Risk Measures**

### **Value at Risk and Related Measures**

1. **Value at Risk (VaR)**
   $$
   P(X \leq VaR_\alpha) = \alpha
   $$

2. **Conditional Tail Expectation (CTE) / Expected Shortfall**
   $$
   CTE_\alpha(X) = E[X|X > VaR_\alpha]
   $$

3. **Risk-Based Capital**
   $$
   RBC\;Ratio = \frac{Total\;Adjusted\;Capital}{Required\;Risk\;Based\;Capital}
   $$

### **Risk Adjusted Performance Measures**

1. **Sharpe Ratio**
   $$
   SR = \frac{R_p - R_f}{\sigma_p}
   $$

2. **Risk-Adjusted Return on Capital (RAROC)**
   $$
   RAROC = \frac{Expected\;Return}{Economic\;Capital}
   $$

---
