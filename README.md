# Uniswap v3 Recentering Replay Data

This repository provides the public display package for the paper:

**How Often Should A Liquidity Provider Recenter? A Block-time Replay Study**

The repository is intentionally small. It stores the paper PDF and dataset documentation directly, while the large dataset archive is attached as a GitHub Release asset.

## Files

- `paper.pdf`: current paper PDF.
- `DATASET.md`: dataset source, scope, schema summary and use notes.
- `SHA256SUMS`: checksums for the committed PDF and release archive.

## Dataset

The dataset covers Ethereum Uniswap v3 activity from **2024-03-01 to 2024-08-30**:

- 12 Uniswap v3 pools.
- 3,991,091 swap rows.
- 97,842 mint/burn rows.
- 3,748,514 transaction-gas rows.
- Generated replay outputs used by the paper tables.

Source data are public Google BigQuery datasets:

- Blockchain Analytics Ethereum Mainnet decoded events for swap, mint and burn events.
- Crypto Ethereum transactions for gas prices.

Download the dataset from the latest GitHub Release:

https://github.com/cyfaaa/uniswap-v3-recentering-replay-data/releases

## Use Note

The CSV files are derived from public blockchain datasets. Re-exporting or redistributing the data should follow Google Cloud dataset terms and any terms attached to the upstream public datasets.
