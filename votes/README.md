# DAO Votes Data Collection

This directory contains scripts and tools for collecting voting data across
different DAO platforms. Each platform has specific collection methods based
on their data structure and accessibility.

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
| `weight` | Vote weight value (also known as voting power) |

## Platform-Specific Details

| Platform  | Source | Notes/Key Fields |
|-----------|---------|----------------|
| Aragon    | DAO Analyzer dataset | - Votes are called "casts" in source data<br>- Uses `createdAt` for date field |
| DAOhaus   | DAO Analyzer dataset | Uses `createdAt` for date field |
| DAOstack  | DAO Analyzer dataset | Uses `createdAt` for date field |
| Realms    | JS SDK | - Includes relinquished votes<br>- Uses `voterWeight` for weights<br>- Choice field not present for all values<br>- See [Realms Governance docs](https://github.com/solana-labs/solana-program-library/blob/master/governance/README.md) |
| Snapshot  | Direct API | Uses `created` for date field |
| Tally     | Direct API | Uses `timestamp` for date field |

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