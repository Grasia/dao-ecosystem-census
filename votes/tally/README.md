downloaded 19 July 2023 and 20 July 2023

we have:
- `responses_by_chain_without_42161_or_10.pkl` - this has all the chains except 42161 and 10
- the chain 10 and chain 42161 folders
  - first_pass
  - individual proposals
- one proposal in the eip155:1 directory
  - I think this got captured in the pickle, but we need to confirm

- [x] confirm the large eip155:1 value is in the pickle
- [x] re-assemble the chain 10 and chain 42161 data on a per-chain basis
  - substitute the new proposals for the old (truncated) ones
- [x] combine the chain 10, chain 42161, and other chains data
- [x] put into desired format
