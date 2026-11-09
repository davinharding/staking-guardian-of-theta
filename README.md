# Theta Vibes NFT Staking Contracts

Solidity staking contracts for the Theta Vibes NFT collections on the Theta blockchain. Holders deposit their NFTs and earn an ERC-20 reward token over time, with one contract per collection (Guardian, Rastaman, Lil Monsters, Dreamland, and more).

Part of the **Theta Vibes / Guardian of Theta** project: [frontend](https://github.com/davinharding/guardian-of-theta-frontend) · [NFT staking contracts](https://github.com/davinharding/staking-guardian-of-theta) · [GOT reward airdropper](https://github.com/davinharding/GOTAirdropper)

## How it works

- **Stake many at once.** `deposit(tokenIds[])` and `withdraw(tokenIds[])` move batches of NFTs in and out of the contract.
- **Receipt tokens.** Staking mints a non-transferable ERC-721 receipt (`UntransferableERC721`), so staked positions show up in wallets but can't be traded.
- **Block-based rewards.** Rewards accrue per token per block; `calculateRewards` and `stakedInfoOf` power the UI, and `claimRewards` pays out without unstaking.
- **Owner controls.** Adjustable reward rate, emissions on/off, deposit pausing, and reward-token withdrawal.

Adapted from the Sappy Seals staking design and extended for multiple collections.

## Run it

```bash
npm install
npx hardhat compile
npx hardhat test
```

## Layout

```text
contracts/   StakeGuardian.sol + one staking contract per collection, reward token contracts
test/        Hardhat tests for StakeGuardian
scripts/     deploy script
```

---

<sub>Built by [Davin Harding](https://davin.io) · More at [github.com/davinharding](https://github.com/davinharding)</sub>
