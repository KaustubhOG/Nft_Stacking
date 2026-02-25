# NFT Staking

An NFT staking protocol built on Solana using the Anchor framework. Users can mint NFTs into a collection, stake them to earn on-chain rewards over time, and claim or unstake whenever they choose.

---

## What It Does

- Initializes a staking config that controls reward rate and freeze period
- Creates an on-chain collection for the NFTs used in the protocol
- Allows users to initialize their user account to track points and stake count
- Allows users to mint NFTs directly into the collection
- Allows users to stake an NFT — locking it and recording the stake timestamp
- Calculates and distributes token rewards based on time staked
- Allows users to unstake their NFT and claim accumulated rewards

---

## Code Structure

```
programs/anchor-nft-staking-q4-25/src/
├── lib.rs
├── errors.rs
├── instructions/
│   ├── mod.rs
│   ├── initialize_config.rs    — sets up staking config: reward rate, freeze period
│   ├── initialize_user.rs      — creates per-user account to track points and stakes
│   ├── create_collection.rs    — creates the NFT collection used by the protocol
│   ├── mint_nft.rs             — mints a new NFT into the collection
│   ├── stake.rs                — locks the NFT, records stake timestamp
│   ├── unstake.rs              — unlocks the NFT, triggers reward claim
│   └── claim.rs                — calculates elapsed time, mints reward tokens to user
└── state/
    ├── mod.rs
    ├── stake_config.rs         — reward rate, freeze period, bump
    ├── user_account.rs         — points balance, amount staked, bump
    ├── stake_account.rs        — NFT mint, stake timestamp, bump
    └── collection_info.rs      — collection mint and authority info
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
