# BasedToken: an ERC-20 Token on Base Sepolia

**BasedToken (BASED)** is an ERC-20 token written in Solidity and tested with Foundry. It was built as the token for a rock-paper-scissors game on **Base Sepolia** (a Base test network), and shows the common features a real token needs.

Deployed on Base Sepolia at `0xb7f7800de6f931be4c11a867f3a94ddb4aa1a271`.

## Features

| Feature | How it works |
| --- | --- |
| **Roles** | Admin, minter, and pauser roles (OpenZeppelin `AccessControl`). The deployer gets all three. |
| **Mint** | Minters create new tokens with `mint(to, amount)`. |
| **Burn** | Anyone can burn their own tokens. |
| **Pause** | Pausers can freeze and unfreeze all transfers. |
| **Blacklist** | The admin can block an address from sending or receiving. |
| **Daily reward** | Anyone can call `claimReward()` once every 24 hours to get **10 BASED**. |

## Getting started

You need [Foundry](https://book.getfoundry.sh/).

```bash
cd rpsgame-contracterc20
forge install     # get OpenZeppelin and forge-std
forge build
forge test
```

To deploy (never commit your private key):

```bash
forge script script/BasedToken.s.sol --rpc-url <base_sepolia_rpc_url> --private-key <your_private_key> --broadcast
```

## Project structure

| Path | What it is |
| --- | --- |
| `rpsgame-contracterc20/src/BasedToken.sol` | The token contract |
| `rpsgame-contracterc20/test/BasedToken.t.sol` | Tests |
| `rpsgame-contracterc20/script/BasedToken.s.sol` | Deploy script |
| `rpsgame-contracterc20/broadcast/` | Records of past deployments |
