# DAO Deployments Data Collection

This directory contains scripts and data for collecting DAO deployment information from various platforms. Data was last updated via DAO Analyzer on July 20, 2023.

## Data Schema

Each platform's data is collected into a standardized format with the following columns:

| Column | Description |
|--------|-------------|
| `platform` | Platform identifier |
| `platform_id` | Unique identifier within the platform |
| `name` | DAO name (optional) |
| `website` | DAO website URL (optional) |
| `additional` | Additional metadata like social links (optional) |
| `votes_count` | Number of votes in the deployment* |
| `proposals_count` | Number of proposals in the deployment |

\* Note: Platforms have different ways of estimating the number of votes. This is
the number of votes reported by the platform. In our final dataset the `votes_count`
value is calculated by counting the number of votes recorded in our dataset.


## Types

Currently collecting data from:

- [Snapshot](https://snapshot.org/#/)
- [Tally](https://www.tally.xyz/)
- [Realms](https://realms.today/)
- [Aragon](https://aragon.org/)
- [DAOstack](https://daostack.io/)
- [DAO Haus/Moloch](https://daohaus.club/)

## Unsupported Platforms

The following platforms are currently not included:

| Platform | Reason |
|----------|--------|
| Governor | No public API |
| AssetsOnly | Platform not found |
| Substrate | No API (has [directory](https://substrate.io/ecosystem/projects/)) |
| OpenLaw | Too few DAOs, n<10 |
| Colony | Too few DAOs, n<10 |
