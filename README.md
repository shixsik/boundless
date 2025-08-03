# Boundless Prover Node

![Boundless Logo](https://github.com/shixsik/boundless/blob/main/logo.jpg)

The Boundless Prover Node is a high-performance computational proving system that participates in the Boundless decentralized proving market.

## Table of Contents
- [Requirements](#requirements)
  - [Hardware](#hardware)
  - [Software](#software)
- [How Boundless Prover Market Works](#how-boundless-prover-market-works)

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
   - 
## Increasing Lock-in Rate

Once your broker is running, before the gpu-based prover gets into work, broker must compete with other provers to lock-in the orders. Here is how to optimize broker to lock-in faster than other provers:

1. Decreasing the mcycle_price would tune your Broker to bid at lower prices for proofs.
   
Once an order detected, the broker runs a preflight execution to estimate how many cycles the request needs. As you see in the image, a prover proved orders with millions or thousands of cycles.

`mcycle_price` is actually price of a prover for proving each 1 million cycles. Final price = `mcycle_price` x `cycles`

The less you set `mcycle_price`, the higher chance you outpace other provers.

To get idea of what `mcycle_price` are other provers using, find an order in explorer with your prefered network, go to details page of the order and look for ETH per Megacycle
image

Increasing `lockin_priority_gas` to consume more gas to outrun other bidders.


