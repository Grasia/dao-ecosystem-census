# Downloading Realms data with Node.js

## Why?

The best way to access Realms data is through their
[Realms JS SDK](https://www.npmjs.com/package/@solana/spl-governance). This
approach goes against the structure for the rest of the platforms, which is
broken down by platforms/organizations/proposals/votes.

## How?

1. First, get the list of `ProgramIds` from the realms homepage Next.js payload
2. Save this list to `program_ids.txt`, with one `programId` on each line, for example:
```
GovER5Lthms3bLBqWub97yVrMmEogzX7xNjdXpPPCVZw
G41fmJzd29v7Qmdi8ZyTBBYa98ghh3cwHBTexqCG1PQJ
bqTjmeob6XTdfh12px2fZq4aJMpfSY1R1nHZ44VgVZD
```
3. Download all deployments for each `programId` (many just have one)
4. Download all proposals for each deployment
5. Download all votes for each proposal
6. Format the data in python

## How? Using Docker

The `downloadvotes.Dockerfile` file is configured to use Docker to download
the votes.

This can be deployed to a server or a container service as this is a long-running
job.

Build and run the image with:

```
docker build -t downloadvotes -f downloadvotes.Dockerfile .
docker run -it downloadvotes
```
