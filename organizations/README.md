# DAO Organizations Data Collection

This directory contains scripts and data for collecting and analyzing information about DAO organizations from various sources. The focus is on identifying the maximum number of organzations in the DAO ecosystem.

## Directory Structure

- `01_deepdao_daos/`: Scripts for collecting and processing DeepDAO organization data
- `01_messari_daos/`: Scripts for processing Messari platform data
- `combine_deepdao_and_manual_organizations/`: Tools to merge and analyze data from different sources
- `deepdao_review/`: Analysis and review tools for DeepDAO data, including similarity detection (unused in final dataset)
- `organizations_grouping_analysis/`: Scripts for analyzing and grouping related organizations (unused in final dataset)

## Data Sources

- **DeepDAO**: Primary source for organization metadata and statistics
- **Messari**: Additional platform and organization data
- **Manual Collection from DAO Analyzer**: Curated data for validation and enrichment

## Key Components

### DeepDAO Processing
- Organization scraping and data collection
- Data cleaning and standardization
- Visualization tools
- Docker environment for reproducible collection

### Organization Analysis
- Name similarity detection using sentence embeddings
- Cross-platform organization matching
- Grouping analysis for related organizations
- Data filtering and validation tools

### Data Integration
- Tools for combining data from multiple sources
- Quality checks and data validation
- Preparation scripts for deployment collection integration

## Technical Implementation

### Similarity Detection (unused in final dataset)
The `deepdao_review/with_sentence_embeddings/` directory contains tools for:
- Generating embeddings for organization names
- Computing similarity scores
- Creating and analyzing organization pairs
- Review interface for manual validation

### Data Processing Pipeline
1. Initial data collection from DeepDAO and Messari
2. Data cleaning and standardization
3. Similarity analysis and grouping
4. Manual review and validation
5. Integration with deployment collection
