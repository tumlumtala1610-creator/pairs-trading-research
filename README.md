# ETF Pairs Trading Research

A study of whether historical cointegration between economically related
ETFs translates into out-of-sample trading performance after costs.

## Research Questions

- Does cointegration-based pair selection improve on correlation-based selection?
- How sensitive are results to transaction costs and borrowing costs?
- When do historical relationships break down?

## Current Progress

- Defined the research protocol and ETF universe.
- Implemented development-sample data collection and download metadata.
- Next: complete data quality checks before statistical testing.

No strategy performance results are available yet.

## ETF Universe

| Group | ETFs |
|---|---|
| US large-cap | SPY, IVV, VOO |
| US broad market | VTI, ITOT, SCHB |
| Developed markets outside the US | EFA, VEA, SCHF |
| Emerging markets | EEM, VWO, IEMG |

Only within-group pairs are considered, giving 12 candidate pairs.

Fund descriptions, issuer sources, and benchmark considerations are
documented in [Universe Notes](report/universe_notes.md).

## Sample Design

| Sample | Period | Purpose |
|---|---|---|
| Development | 2010–2019 | Implementation and initial research |
| Validation | 2020–2022 | Model comparison and design decisions |
| Final holdout | 2023–2025 | Final evaluation after the design is frozen |

Funds enter the dataset when historical observations become available.
Pre-inception prices are not filled.

## Planned Methodology

- Estimate log-price relationships using OLS.
- Test for cointegration using the Engle–Granger method.
- Apply Holm correction to pair-selection tests.
- Use 504-session formation windows and 63-session trading windows.
- Generate spread z-score signals with delayed execution.
- Include transaction and borrowing cost scenarios.
- Compare cointegration-based selection with a correlation baseline.
- Examine parameter sensitivity and relationship breakdowns.

Full assumptions are recorded in the
[Research Protocol](research_protocol.md).

## Repository Structure

```text
configs/        Research configuration
notebooks/      Data inspection and research notebooks
report/         Universe notes and research documentation
results/        Generated tables and figures
requirements.txt
research_protocol.md
```

Downloaded data are stored locally under `data/raw/` and excluded
from version control.

## Setup

Run these commands from the repository root:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Open `notebooks/01_data_quality.ipynb`, select the virtual environment
as the Python kernel, and run the cells in order.

The download configuration currently covers the development sample only.

## Data and Limitations

Historical daily data are retrieved from Yahoo Finance using `yfinance`.
Downloads are saved with metadata and file checksums.

The universe is selected using present-day information and is subject
to selection and survivorship bias. Fund benchmarks may change over
time, and adjusted historical prices are not a point-in-time data archive.

Historical cointegration does not guarantee future mean reversion
or profitability after costs.