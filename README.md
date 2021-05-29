# DeFiChain Node Playground

Easy-to-set-up playground for experimenting with DeFiChain node.
Main building blocks:
 - [DeFiChain Node](https://github.com/DeFiCh/ain) software for running a node in DeFiChain network
 - [Docker Desktop](https://www.docker.com/products/docker-desktop) application containerization technology
 - [Docker Compose](https://docs.docker.com/compose/) a tool for defining and running containerized applications

## Installation

Installation is a 2 step process assuming Docker Desktop is installed already.

### Step 1: Clone the repo

```bash
git clone git@github.com:RomanShumkov/docker-defichain-node.git .
```

### Step 2: Install

```bash
# Could take 15+ minutes to complete (building from source and setting up the node)
docker-compose up -d
```

You should now be able to run `defi-cli` commands. For example:

```bash
docker-compose exec defichain-node defi-cli -testnet -getinfo
```

## Credits

 - Thank you [u/crypto-pi](https://www.reddit.com/user/crypto-pi/) for sharing your [knowledge](https://www.reddit.com/r/defiblockchain/comments/kmkdji/defichain_on_raspberry_pi_4_with_ubuntu_2004_64/gpgoz3r/) on reddit
