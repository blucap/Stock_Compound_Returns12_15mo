# Stock Compound Returns for 12 and 15 months after the start of the fiscal year
Date      : August 28, 2021                                                      
Author    : Martien Lubberink, based on a SAS script from Rabih Moussawi, see this [link](https://wrds-www.wharton.upenn.edu/pages/support/applications/risk-and-valuation-measures/stock-return-volatility-and-compound-returns-and-after-fiscal-year-ends/)

- Inputs are CRSP Monthly File and Compustat Data with FPE Dates
- Linking CRSP and Compustat using CCM 
- 12 and 15-Month Compound Returns are computed for Stocks and for the Market Index
- Computes Book Value of Equity 

You need to install the WRDS library, see this [link](https://pypi.org/project/wrds/)

Then run this once to set the pgpass file:

    import wrds
    db = wrds.Connection(wrds_username='yours')
    db.create_pgpass_file()

For the calculation of pref shares, I use [the python equivalent of the SAS 'coalesce' function](https://stackoverflow.com/questions/38152389/coalesce-values-from-2-columns-into-a-single-column-in-a-pandas-dataframe)

For the mapping of returns to fiscal years, see this [sheet](https://docs.google.com/spreadsheets/d/e/2PACX-1vTn99bA4H6VWjQZmSpQ5NiK8uA_rx0ZhSdBBEOr6j_adfTqjgjtKucfTCo5kffVPzTdIHwH5v7Fe--c/pubhtml) for the logic.
