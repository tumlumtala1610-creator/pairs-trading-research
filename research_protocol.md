# Research Protocol

## Research question

Do ETF pairs with evidence of historical cointegration generate
out-of-sample returns after transaction and borrowing costs?

## Secondary questions

1. Does cointegration-based selection improve on correlation-based selection?
2. How sensitive are results to trading and borrowing costs?
3. Under what conditions do historical relationships break down?

## Scope

- Daily data.
- US-listed equity ETFs.
- Candidate pairs are restricted to predefined economic groups.
- OLS hedge ratio and Engle-Granger cointegration testing.
- No intraday trading, machine learning, or live execution in the initial study.

## Sample split

- Development: 2010-01-01 to 2019-12-31.
- Validation: 2020-01-01 to 2022-12-31.
- Final holdout: 2023-01-01 to 2025-12-31.
- Week 1 downloads and analyses use development data only.

## Walk-forward design

- Formation window: 504 trading sessions.
- Trading window: 63 trading sessions.
- Parameters are estimated using formation data only.
- Parameters remain fixed within each trading window.
- A pair must have 504 valid observations in the formation window.

## Pair selection

- Test candidate pairs within each economic group.
- Fix regression direction alphabetically by ticker.
- Apply Holm correction at a 5% significance level
  across all eligible pair tests in each formation window.
- Require a positive hedge ratio and nonzero spread standard deviation.
- Select at most one eligible pair per group.
- Rank eligible pairs by adjusted p-value.
- Hold cash when no pair qualifies.

## Trading rules

- Enter long spread when z <= -2.
- Enter short spread when z >= 2.
- Exit when abs(z) <= 0.5 or the spread crosses zero.
- Stop when abs(z) >= 4.
- Maximum holding period: 20 trading sessions.
- Close positions at the end of each trading window.
- Do not reverse a position in the same execution event.

## Execution

- Generate signals after close on day t.
- Execute at close on day t+1.
- Position P&L begins after execution.

## Portfolio and costs

- Allocate 25% of capital to each economic group.
- Keep unused allocations in cash.
- Initial portfolio gross exposure limit: 100% of equity.
- Transaction cost scenarios: 0, 5, 10, 20 basis points per side.
- Annual borrowing cost scenarios: 0%, 2%, 5%.
- Cash return is assumed to be zero in the initial model.

## Data handling

- Save raw data and download metadata.
- Preserve unadjusted OHLC, adjusted close, volume, and corporate actions.
- Do not backward-fill or forward-fill missing prices.
- Align observations separately for each pair.
- Do not treat pre-inception observations as data errors.
- Do not treat adjusted prices as executable market prices.

## Limitations

- The ETF universe is selected using present-day knowledge.
- Results may be affected by survivorship and selection bias.
- Historical adjusted data are not a point-in-time data archive.
- Borrow availability, recalls, and detailed financing are not modeled.
- Historical cointegration does not guarantee future mean reversion.

## Research discipline

- Record changes to the protocol and their reasons.
- Freeze the final design before evaluating the final holdout.
- Do not change the universe based on observed strategy profitability.

## Initial Formation Study

The initial study uses 504 sessions from January 2, 2013 to
December 31, 2014. This window provides a common sample for all
12 ETFs. It does not set the starting date of the later walk-forward
backtest.

Log-price relationships are estimated by OLS with an intercept.
The dependent variable is the alphabetically first ticker in each pair.

ADF tests are applied to log prices and their first differences,
using an intercept and AIC lag selection with a maximum of 12 lags.
These tests are reported as diagnostics rather than an additional
selection filter.

Engle–Granger tests use an intercept and the same lag-search settings.
Holm correction is applied across all 12 candidate pairs at the
5% significance level.

A pair qualifies only if its test is numerically valid, its
Holm-adjusted p-value is below 0.05, its hedge ratio is positive,
and its spread standard deviation is finite and positive.
At most one pair is selected per group, ranked by adjusted p-value.

Tests with near-collinearity warnings are excluded. Invalid tests
receive a value of 1 when applying Holm correction, while their
original results and warnings remain in the output.

Formation z-scores use the mean and standard deviation estimated
over the full formation window. They describe the training sample
and are not used as trading signals within that same period.