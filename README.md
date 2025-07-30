# DAOs Ecosystem Census

A comprehensive data collection and analysis project for Decentralized Autonomous Organizations (DAOs) across multiple platforms. This repository contains tools and scripts to gather, process, and analyze data about DAO deployments, proposals, and voting patterns.

## Project Overview

This project collects data from multiple DAO platforms and standardizes it into a common schema for analysis. The data collection is organized into three main components:

1. **Deployments**: Information about DAO deployments across platforms
2. **Proposals**: Proposal data from each DAO
3. **Votes**: Voting records for each proposal

### Supported Platforms

Currently collecting data from:
- Snapshot (2404+ deployments)
- Aragon (84 deployments)
- Moloch/DAOhaus (36 deployments)
- Realms (18 deployments)
- DAOstack (12 deployments)
- Tally

Data sources:
- Direct API access (Snapshot, Tally, Realms)
- DAO Analyzer dataset (Aragon, DAOstack, DAOhaus)
- Realms JS SDK

## Data Schema

### Deployments
- platform
- platform_id
- name
- website
- votes_count
- proposals_count
- additional (may contain website, social info)

### Proposals
- platform
- platform_deployment_id
- proposal_id
- author
- date
- votes_count

### Votes
- platform
- platform_deployment_id
- proposal_id
- vote_id
- voter
- date
- choice
- weight

## Usage

The repository is organized by data type (deployments, proposals, votes) and
then by platform. Each platform has its own collection scripts and specific
implementation details.

### Running the data collection

Each platform has its own code / process for collecting data, according to
various factors, including API availability and the number of deployments
per platform.

Each platform has a directory that outlines how to run its data collection,
see each directory for details about running its collection.

## Data Collection Dates
Data was collected during June and July of 2023, specificlaly:

- Snapshot: June 23-27, 2023
- DAO Analyzer data: July 20, 2023
- Realms: July 12, 2023
- Tally: July 18, 2023

## References

- [DAO Analyzer Scripts](https://github.com/Grasia/dao-analyzer/blob/master/cache_scripts/README.md)
- [DAO Analyzer Dataset](https://www.kaggle.com/datasets/daviddavo/dao-analyzer)
