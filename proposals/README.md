# DAO Proposals Data Collection

This directory contains scripts and tools for collecting proposal data across
different DAO platforms. Each platform has its own collection methodology
based on available APIs and data structures.

## Data Schema

| Column | Description |
|--------|-------------|
| `platform` | Platform identifier |
| `platform_deployment_id` | Reference to the DAO deployment |
| `proposal_id` | Unique identifier within the platform |
| `author` | Address/identifier of proposal creator |
| `date` | Creation timestamp |
| `votes_count` | Number of votes on the proposal |

## Platform-Specific Collection

| Platform  | Source | Notes/Key Fields |
|-----------|---------|----------------|
| Aragon    | DAO Analyzer dataset | Uses `createdAt` for date |
| DAOhaus   | DAO Analyzer dataset | Uses `createdAt` for date |
| DAOstack  | DAO Analyzer dataset | Uses `createdAt` for date |
| Realms    | JS SDK | See `realms_node/README.md` for SDK details |
| Snapshot  | Direct API | Two-step collection and processing |
| Tally     | Direct API | Uses `timestamp` for date |

## Collection Process

Each platform's collection script follows these general steps:
1. Fetch raw proposal data
2. Transform to standard schema
3. Validate required fields
4. Save to parquet format

## Technical Notes

- All dates are standardized to pandas datetime format
- Proposal IDs are platform-specific and may not be globally unique
- Some platforms may have additional metadata in raw collection
- Rate limiting is implemented where required by APIs
- Large-scale collections may be split into batches

## Related Components

- See `deployments/` for DAO deployment information
- See `votes/` for proposal voting data
- See `parquet_versions/` for data versioning