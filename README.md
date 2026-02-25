# NFT Staking

An NFT staking protocol built on Solana using the Anchor framework. Users can stake their NFTs to earn on-chain rewards over time, with all staking logic and reward calculation handled entirely by the program.

---

## What It Does

- Allows users to stake an NFT by transferring it into a program-controlled vault
- Tracks the staking duration on-chain per user
- Calculates and distributes token rewards based on time staked
- Allows users to unstake their NFT and claim accumulated rewards at any time

---

## Code Structure

```
programs/nft-staking/src/
├── lib.rs                  — program entry point, instruction routing
├── instructions/
│   ├── initialize.rs       — sets up the staking config and reward mint
│   ├── stake.rs            — transfers NFT into vault, records stake timestamp
│   ├── unstake.rs          — returns NFT to user, triggers reward claim
│   └── claim.rs            — calculates elapsed time, mints reward tokens to user
└── state/
    ├── config.rs           — staking config: reward rate, freeze period
    └── stake_account.rs    — per-user stake record: NFT mint, timestamp, bump
```

---

## Prerequisites

- [Rust](https://www.rust-lang.org/tools/install)
- [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
- [Anchor CLI](https://www.anchor-lang.com/docs/installation)
- [Node.js](https://nodejs.org/) (v18 or above)
- [Yarn](https://yarnpkg.com/)

---

## How to Run

```bash
cd Nft_Stacking
yarn install
anchor build
anchor test
```

Make sure your Solana CLI is set to localnet:

```bash
solana config set --url localhost
```

Start a local validator if not already running:

```bash
solana-test-validator
```
