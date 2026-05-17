# MTH9877 Interest Rate and Credit Models — Assignment 1

Factor models of the interest rate curve (Nelson-Siegel, Dynamic Nelson-Siegel via Kalman filter, and curve-trade applications).

**Group E** — Lin, Yueqi; Smalhout, Paolo Chai; Tuzes, Daniel.

## Contents

| File | Description |
| --- | --- |
| `MTH9877_Assignment1_GroupE.ipynb` | Main notebook covering Parts (A)-(E) |
| `9877Assignment1_GroupE_report.pdf` | Written report (deliverable) |
| `9877Assignment1_GroupE_slides.pdf` | Presentation slides |
| `IR&C_Assignment1_2026.pdf` | Assignment handout |
| `script.pdf` | Lecture-note excerpt for reference |
| `feds200628.csv` | FRB / Gürkaynak-Sack-Wright Svensson parameters (input data) |
| `requirements.txt` | Python dependencies |
| `report/output/` | Figures saved by the notebook (created at runtime) |

## How to run

1. **Clone and enter the repo**
   ```bash
   git clone https://github.com/liny-r/MTH9877-IR-Assignment1.git
   cd MTH9877-IR-Assignment1
   ```

2. **Install dependencies** (Python 3.10+ recommended)
   ```bash
   python -m venv .venv
   source .venv/bin/activate           # Windows: .venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Launch Jupyter and run the notebook top-to-bottom**
   ```bash
   jupyter notebook MTH9877_Assignment1_GroupE.ipynb
   ```
   Use *Kernel → Restart & Run All*. All plots render inline; figure copies are written to `report/output/` (created at runtime by an early setup cell).

   The input dataset `feds200628.csv` (FRB / Gürkaynak-Sack-Wright Svensson parameters, daily) is committed to the repo. The freshest copy can be re-downloaded from <https://www.federalreserve.gov/data/nominal-yield-curve.htm>.

## Notebook structure

- **Part (A)** — Closed-form derivation of the NS zero-coupon yield, with loadings and economic interpretation of $\beta_0, \beta_1, \beta_2$.
- **Part (B)** — Daily zero-coupon yields from 2016-01-01 at $T \in \{0.25, 0.5, 1, 2, 3, 5, 7, 10\}$ years, evaluated from the FRB/GSW Svensson parameters.
- **Part (C)** — Cross-sectional NS calibration: nonlinear least squares; comparison of three $\lambda$-selection strategies (grid search, fixed $\lambda$, full NLLS); time-series stability of $(\beta_0, \beta_1, \beta_2)$.
- **Part (D)** — Dynamic Nelson-Siegel via state-space / Kalman filter, with out-of-sample evaluation.
- **Part (E)** — Curve-trade application (DV01-neutral strategies) and forecasting comparison across horizons.

## Notes

- Random seeds are set where Monte Carlo / cross-validation appears, so results are deterministic.
- Heavy cells (Kalman EM, rolling backtests) can take a few minutes on a laptop.
- Generated PDF figures under `report/output/` are git-ignored; they are regenerated each run.

## Attribution

Code and write-up drafted by Group E with assistance from large language models (ChatGPT / Claude) for literature pointers and code review, per the assignment's allowed use of AI tools.
