# ETF Universe Notes

## Research purpose

This study tests whether economically related ETF pairs exhibit
historical cointegration and whether that relationship supports
out-of-sample pairs trading after costs.

The universe contains 12 US-listed equity ETFs in four predefined groups.
Selection is based on related economic exposure, not observed trading
profitability.

## Sources and interpretation

Official issuer sources were reviewed on 2026-10-29.

Fund names and benchmarks below describe the reviewed issuer documents.
They are not assumed to have remained unchanged throughout 2010-2019.

ETF inception dates are distinct from the first trading observation
available from the data provider.

## Group 1 US large-cap equities

### SPY

- Fund name: State Street SPDR S&P 500 ETF Trust.
- Group: us_large_cap.
- Benchmark: S&P 500 Index.
- Inception date: 1993-01-22.
- Exposure: US large-cap equities.
- Relevant distinction: Same stated index exposure as IVV and VOO;
  fund implementation and tracking differences may still affect prices.
- Source: https://www.ssga.com/us/en/institutional/etfs/state-street-spdr-sp-500-etf-trust-spy
- Source reviewed: 2026-10-29.

### IVV

- Fund name: iShares Core S&P 500 ETF.
- Group: us_large_cap.
- Benchmark: S&P 500 Index.
- Inception date: 2000-05-15.
- Exposure: US large-cap equities.
- Relevant distinction: Same stated benchmark as SPY and VOO;
  similar exposure does not guarantee a stationary relative-price spread.
- Source: https://www.ishares.com/us/products/239726/ishares-core-sp-500-etf
- Source reviewed: 2026-10-29.

### VOO

- Fund name: Vanguard S&P 500 ETF.
- Group: us_large_cap.
- Benchmark: S&P 500 Index.
- Inception date: 2010-09-07.
- Exposure: US large-cap equities.
- Relevant distinction: The fund began after the requested sample start.
  Pre-inception prices must not be filled.
- Source: https://advisors.vanguard.com/investments/products/voo/vanguard-sp-500-etf
- Source reviewed: 2026-10-29.

## Group 2 US broad-market equities

### VTI

- Fund name in the reviewed factsheet:
  Vanguard Morningstar Total Stock Market ETF.
- Group: us_total_market.
- Benchmark in the reviewed factsheet: Morningstar US Total Market Index.
- Inception date: 2001-05-24.
- Exposure: Broad US equities across large, mid, and small capitalizations.
- Relevant distinction: Broad-market coverage differs from the S&P 500.
  Benchmark history requires care; a current fund label must not be
  applied automatically to the full historical sample.
- Source: https://fund-docs.vanguard.com/F0970.pdf
- Source reviewed: 2026-10-29.

### ITOT

- Fund name: iShares Core S&P Total U.S. Stock Market ETF.
- Group: us_total_market.
- Benchmark in the reviewed issuer page: S&P Total Market Index.
- Inception date: 2004-01-20.
- Exposure: US equities across market capitalizations.
- Relevant distinction: Its index methodology differs from VTI and SCHB.
  The historical benchmark-change timeline has not yet been audited.
- Source: https://www.ishares.com/us/products/239724/ishares-core-sp-total-us-stock-market-etf
- Source reviewed: 2026-10-29.

### SCHB

- Fund name: Schwab U.S. Broad Market ETF.
- Group: us_total_market.
- Benchmark: Dow Jones U.S. Broad Stock Market Index.
- Inception date: 2009-11-03.
- Exposure: US large-, mid-, and small-cap equities.
- Relevant distinction: Different benchmark construction and market
  coverage from the other broad-market funds.
- Source: https://www.schwabassetmanagement.com/products/schb
- Source reviewed: 2026-10-29.

## Group 3 Developed-market equities outside the US

### EFA

- Fund name: iShares MSCI EAFE ETF.
- Group: developed_ex_us.
- Benchmark: MSCI EAFE Index.
- Inception date: 2001-08-14.
- Exposure: Large- and mid-cap developed-market equities outside
  the US and Canada.
- Relevant distinction: Canada is excluded, and small-cap exposure
  differs from an all-cap developed-market benchmark.
- Source: https://www.ishares.com/us/products/239623/ishares-msci-eafe-etf
- Source reviewed: 2026-10-29.

### VEA

- Fund name: Vanguard FTSE Developed Markets ETF.
- Group: developed_ex_us.
- Benchmark in the reviewed factsheet:
  FTSE Developed All Cap ex US Index.
- Inception date: 2007-07-20.
- Exposure: Developed-market equities outside the US, including Canada,
  with large-, mid-, and small-cap coverage.
- Relevant distinction: Different country and capitalization coverage
  from EFA. The benchmark changed during the development sample.
- Source: https://fund-docs.vanguard.com/F0936.pdf
- Source reviewed: 2026-10-29.

### SCHF

- Fund name: Schwab International Equity ETF.
- Group: developed_ex_us.
- Benchmark: FTSE Developed ex US Index.
- Inception date: 2009-11-03.
- Exposure: Large- and mid-cap developed-market equities outside the US.
- Relevant distinction: The issuer describes exposure including Canada
  and South Korea. Unlike VEA's all-cap benchmark, its stated focus is
  large- and mid-cap equities.
- Source: https://www.schwabassetmanagement.com/products/schf
- Source reviewed: 2026-10-29.

## Group 4 Emerging-market equities

### EEM

- Fund name: iShares MSCI Emerging Markets ETF.
- Group: emerging_markets.
- Benchmark: MSCI Emerging Markets Index.
- Inception date: 2003-04-07.
- Exposure: Large- and mid-cap emerging-market equities.
- Relevant distinction: Narrower capitalization coverage than IEMG;
  MSCI and FTSE country classifications can differ.
- Source: https://www.ishares.com/us/products/239637/ishares-msci-emerging-markets-etf
- Source reviewed: 2026-10-29.

### VWO

- Fund name: Vanguard FTSE Emerging Markets ETF.
- Group: emerging_markets.
- Benchmark in the reviewed factsheet:
  FTSE Emerging Markets All Cap China A Inclusion Index.
- Inception date: 2005-03-04.
- Exposure: Emerging-market equities across large, mid, and small caps.
- Relevant distinction: Country classification and China A-share
  coverage differ across benchmark methodologies. Benchmark transitions
  occurred within 2010-2019.
- Source: https://fund-docs.vanguard.com/F0964.pdf
- Source reviewed: 2026-10-29.

### IEMG

- Fund name: iShares Core MSCI Emerging Markets ETF.
- Group: emerging_markets.
- Benchmark: MSCI Emerging Markets Investable Market Index.
- Inception date: 2012-10-18.
- Exposure: Large-, mid-, and small-cap emerging-market equities.
- Relevant distinction: Includes small-cap coverage beyond EEM's stated
  scope. No prices should be created before inception.
- Source: https://www.ishares.com/us/products/244050/ishares-core-msci-emerging-markets-etf
- Source reviewed: 2026-10-29.

## Historical benchmark considerations

VEA's reviewed factsheet describes a spliced benchmark history:
MSCI EAFE through May 2013, followed by FTSE benchmarks and a transition
to the all-cap ex-US benchmark completed in 2016.

VWO's reviewed factsheet describes transitions from MSCI Emerging Markets
to FTSE benchmarks during 2013 and further benchmark transitions
during 2015-2016.

These changes may alter economic exposure and should be considered
when interpreting relationship breakdowns.

A complete point-in-time benchmark audit for every fund is outside
Week 1. Current descriptions alone must not be used to attribute
historical performance differences.

## Candidate pair construction

Only within-group pairs are considered.

With three ETFs in each group, there are three pairs per group
and 12 candidate pairs in total.

Regression direction will be fixed alphabetically by ticker.

Pair availability will depend on actual historical observations.
Each formation window must contain the required valid observations.

## Why restrict pairs to the same group

These funds provide related economic exposures, which motivates testing
a stable relative-price relationship. Differences in benchmarks and
portfolio construction may nevertheless cause persistent divergence.

Restricting candidates to predefined groups keeps the economic
hypothesis interpretable and limits the number of statistical tests.

## Limitations

- This is a fixed universe selected using present-day information.
- Survivorship and selection bias remain.
- Similar exposure is not evidence of cointegration.
- Cointegration is not evidence of profitable trading after costs.
- Historical adjusted data are not a point-in-time data archive.