# Option Pricing Using Fast Fourier Transform (FFT)

An interactive quantitative finance dashboard that implements the landmark **Carr-Madan (1999)** methodology to price European options under the **Variance Gamma (VG)** stochastic process, benchmarked against the analytical **Black-Scholes-Merton (BSM)** model.

---

## 📌 Project Overview

The main objective of this project was to explore how shifting option pricing problems from the **time domain** into the **frequency domain** allows for the simultaneous calculation of an entire chain of option strikes with remarkable speed, achieving a computational complexity of:

\[
O(N \log N)
\]

### Key Features Implemented

- **Variance Gamma Pricing Engine:** Models asset returns using a jump process that captures real-world **skewness (\(\theta\))** and **kurtosis (\(\nu\))**, overcoming the constant-volatility assumption of the Black-Scholes model.

- **Carr-Madan Damping:** Implements an exponential damping factor **(\(\alpha\))** to ensure the modified call payoff is square-integrable, enabling efficient Fourier transformation.

- **Hyperbolic Smoothing:** Incorporates a modified time-value isolation technique using **sinh damping** to suppress high-frequency oscillations observed for short-maturity options (\(T \rightarrow 0\)).

- **Numerical Integration:** Discretizes the pricing integral using **Simpson's Rule**, while satisfying the Nyquist grid constraint:

\[
\lambda \eta = \frac{2\pi}{N}
\]

required by the Discrete Fourier Transform.

- **Streamlit Dashboard:** Provides an interactive interface to modify market inputs, adjust Variance Gamma parameters, and visualize pricing results alongside the analytical Black-Scholes benchmark, highlighting the **volatility smile**.
