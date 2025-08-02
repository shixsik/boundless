# Boundless Prover Node

![Boundless Logo](https://github.com/shixsik/boundless/main/logo.jpg)

The Boundless Prover Node is a high-performance computational proving system that participates in the Boundless decentralized proving market.

## Table of Contents
- [Requirements](#requirements)
  - [Hardware](#hardware)
  - [Software](#software)
- [How Boundless Prover Market Works](#how-boundless-prover-market-works)
- [Installation](#installation)
  - [Quick Setup](#quick-setup)
  - [Manual Installation](#manual-installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
- [Support](#support)
- [License](#license)

## Requirements

### Hardware
- **CPU**: 16 threads, single core boost >3GHz
- **RAM**: 32GB
- **Storage**: 100GB NVME/SSD
- **GPU**:
  - Minimum: 1x GPU with 8GB vRAM
  - Recommended: 10x GPUs with 8GB+ vRAM
  - Best models: RTX 4090, RTX 5090, NVIDIA L4

### Software
- **OS**: Ubuntu 20.04/22.04 LTS
- **Not supported**: Ubuntu 24.04

## How Boundless Prover Market Works

1. **Request Submission**: Developers submit tasks as "orders" with ETH/ERC-20 rewards
2. **Staking**: Provers deposit USDC stake
3. **Bidding**: Provers submit competitive bids (mcycle_price)
4. **Order Locking**: Winners lock orders with staked USDC
5. **Proof Generation**: GPU-accelerated proof computation
6. **Rewards**: 
   - Valid proofs → rewards
   - Invalid/late proofs → slashing

## Installation

### Quick Setup
For Ubuntu 22.04:
```bash
sudo ./scripts/setup.sh
