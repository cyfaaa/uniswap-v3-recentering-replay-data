# Dataset Description

## Scope

This release contains the ordered event dataset used in **How Often Should A Liquidity Provider Recenter? A Block-time Replay Study**. The sample window is 2024-03-01 to 2024-08-30. It contains twelve Ethereum Uniswap v3 pools selected to cover ETH/stable pairs, BTC/ETH pairs, BTC/stable pairs and stable/stable pairs across multiple fee tiers.

## Source

The dataset is exported from public Google BigQuery datasets:

- Swap, mint and burn events are exported from the Google Cloud Blockchain Analytics Ethereum Mainnet decoded-events table.
- Transaction gas prices are exported from the Google Cloud public Crypto Ethereum transactions table and joined by block number and transaction index.

The paper repository contains the export templates used to regenerate the data:

- `scripts/bigquery/template_export_swaps.sql`
- `scripts/bigquery/template_export_mint_burn.sql`
- `scripts/bigquery/template_export_gas_multi.sql`

## Released Archive Layout

```text
data/
  bigquery/
    manifest.json
    *_swaps_2024-03-01_26w.csv
    *_mint_burn_2024-03-01_26w.csv
    all_pools_gas_2024-03-01_26w.csv
  experiments/
    block_time_results.csv
    weekly_results.csv
    scale_results.csv
    per_pool_scale_results.csv
    convention_sensitivity.csv
    *.tex
REPRODUCIBILITY.md
DATASET.md
```

## Row Counts

- Swap rows: 3,991,091.
- Mint/burn rows: 97,842.
- Gas rows: 3,748,514.
- Strategy-grid rows: 720 data rows plus header.
- Valid weekly replay rows: 284 data rows plus header.

## Ordering Fields

The swap streams preserve block number, transaction index and log index. This is necessary because the paper studies no-anticipation block-time replay: a strategy may use finalized history before a block, but not the current block's closing price before the block is realized.

## Pool Metadata

Pool addresses, token decimals, fee tiers, labels, row counts and file names are recorded in `data/bigquery/manifest.json`.

## Terms

The release republishes event exports derived from public blockchain datasets. Re-exporting or redistributing the data should follow Google Cloud dataset terms and any terms attached to the upstream public datasets.
