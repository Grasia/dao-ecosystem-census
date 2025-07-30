# DAO Votes Data Collection

This directory contains scripts and tools for collecting voting data across different DAO platforms. Each platform has specific collection methods based on their data structure and accessibility.

## Data Schema

| Column | Description |
|--------|-------------|
| `platform` | Platform identifier |
| `platform_deployment_id` | Reference to the DAO deployment |
| `proposal_id` | Reference to the proposal |
| `vote_id` | Unique identifier for the vote |
| `voter` | Address/identifier of the voter |
| `date` | Vote timestamp (as pandas datetime) |
| `choice` | Vote choice (as string) |
| `weight` | Vote weight value |

## Platform-Specific Details

### Aragon
- Source: DAO Analyzer dataset (July 20, 2023)
- Notes: 
  - Votes are called "casts" in source data
  - Uses `createdAt` for date field

### DAOhaus
- Source: DAO Analyzer dataset (July 20, 2023)
- Notes: Uses `createdAt` for date field

### DAOstack
- Source: DAO Analyzer dataset (July 20, 2023)
- Notes: Uses `createdAt` for date field

### Realms
- Source: JS SDK (July 12, 2023)
- Notes:
  - Includes relinquished votes
  - Uses voterWeight for weights
  - Choice field not present for all values
  - See [Realms Governance docs](https://github.com/solana-labs/solana-program-library/blob/master/governance/README.md)

### Snapshot
- Collection period: June 23-27, 2023
- Time window:
  ```
  YEAR_AGO_EPOCH = 1656021600  # 2022-06-24 00:00:00
  NOW_EPOCH =      1687557600  # 2023-06-24 00:00:00
  ```
- Notes: Uses `created` for date field

### Tally
- Source: Direct API
- Collection date: July 18, 2023
- Notes: Uses `timestamp` for date field

## Technical Implementation

### Collection Process
1. Platform-specific data collection
2. Schema standardization
3. Date field normalization
4. Weight calculation/standardization
5. Storage in parquet format

### Important Notes
- All dates are converted to pandas datetime format
- Vote choices are stored as strings for cross-platform compatibility
- Vote weights may have platform-specific meaning
- Some platforms may have additional metadata in raw collection

## Related Components
- See `proposals/` for proposal information
- See `deployments/` for DAO deployment data
- See `parquet_versions/` for data versioning