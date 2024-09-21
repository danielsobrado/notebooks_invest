# SEC XBRL Downloader

This Python script downloads and processes XBRL (eXtensible Business Reporting Language) files from the U.S. Securities and Exchange Commission (SEC) EDGAR database for specified companies and filing types.

## Features

- Downloads XBRL instance documents for a given ticker symbol and filing type
- Caches downloaded files to reduce unnecessary network requests
- Extracts relevant information from SEC filing URLs
- Renames and stores processed XML files with a consistent naming convention

## Main Functions

### `get_cik(ticker)`
Retrieves the Central Index Key (CIK) for a given ticker symbol.

### `download_xml(ticker, filing_type='10-Q', num_filings=5)`
Downloads XBRL files for the specified ticker, filing type, and number of filings.

### `rename_and_store_xml_files(xml_files, ticker, destination_folder='xbrls')`
Renames and stores the downloaded XML files using a consistent naming convention.

## File Naming Convention

The script renames downloaded files using the following format:

```text
{ticker}-{cik}-{accession_number}-{date}.xml
```

- `ticker`: The stock ticker symbol (lowercase)
- `cik`: The 10-digit Central Index Key
- `accession_number`: The SEC filing accession number
- `date`: The filing date in `YYYYMMDD` format

## Caching

The script implements a caching mechanism to avoid redundant downloads. Cached files are stored in the following directories:

- HTML files: `sec_cache/`
- XML files: `xml_cache_{ticker}/`

## Limitations

- The script is designed for educational and research purposes and should be used in compliance with SEC's fair access rules.
- It may require adjustments for different filing types or changes in the SEC's website structure.

## Disclaimer

This script is provided as-is, without any warranties or guarantees. Users should ensure they comply with SEC's terms of service and usage guidelines when accessing EDGAR data.
