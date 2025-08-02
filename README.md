# boundless
The Boundless Prover Node is a computational proving system that participates in the Boundless decentralized proving market. Provers stake USDC, bid on computational tasks, generate zero-knowledge proofs using GPU acceleration, and earn rewards for successful proof generation.
## Requirements
### Hardware
CPU - 16 threads, reasonable single core boost performance (>3Ghz)

Memory - 32 GB

Disk - 100 GB NVME/SSD

### GPU

Minimum: one 8GB vRAM GPU

Recommended to be competetive: 10x GPU with min 8GB vRAM

Recomended GPU models are 4090, 5090 and L4.

You better test it out with single GPUs by lowering your configurations later by reading the further sections.

### Software

Supported: Ubuntu 20.04/22.04

No support: Ubuntu 24.04

## Boundless Prover market
**First**, you need to know how Boundless Prover market actually works to realize what you are doing.

**Request Submission:** Developers submit computational tasks as "orders" on Boundless, offering ETH/ERC-20 rewards

**Prover Stakes USDC:** Provers must deposit USDC as stake before bidding on orders

**Bidding Process:** Provers detect orders and submit competitive bids (mcycle_price)

**Order Locking:** Winning provers lock orders using staked USDC, committing to prove within deadline

**Proof Generation:** Provers compute and submit proofs using GPU acceleration

**Rewards/Slashing:** Valid proofs earn rewards; invalid/late proofs result in stake slashing

## Installing the node manually

Here is the step by step guide to Install and run your Prover smoothly

Dependecies
Delete Preserved Variables
Open /etc/environment:
sudo nano /etc/environment
Delete everything.

Add this code to it:
PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
Install & Update Packages
sudo apt update && sudo apt upgrade -y
sudo apt install curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev tar clang bsdmainutils ncdu unzip libleveldb-dev libclang-dev ninja-build -y
Clone Boundless Repo
git clone https://github.com/boundless-xyz/boundless
cd boundless
git checkout release-0.13
Install Dependecies
To run a Boundless prover, you'll need the following dependencies:

Docker compose
GPU Drivers
Docker Nvidia Support
Rust programming language
Just command runner
CUDA Tollkit
For a quick set up of Boundless dependencies on Ubuntu 22.04 LTS, you can run:

sudo ./scripts/setup.sh
It may take time to install due to installing Nvidia GPU drivers
However, you can install some dependecies manually:

`\\ Execute command lines one by one

# Install rustup:
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
. "$HOME/.cargo/env"

# Update rustup:
rustup update

# Install the Rust Toolchain:
sudo apt update
sudo apt install cargo

# Verify Cargo:
cargo --version

# Install rzup:
curl -L https://risczero.com/install | bash
source ~/.bashrc

# Verify rzup:
rzup --version

# Install RISC Zero Rust Toolchain:
rzup install rust

# Install cargo-risczero:
cargo install cargo-risczero
rzup install cargo-risczero

# Update rustup:
rustup update

# Install Bento-client:
cargo install --locked --git https://github.com/risc0/risc0 bento-client --branch release-2.3 --bin bento_cli
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# Verify Bento-client:
bento_cli --version

# Install Boundless CLI (v13):
cargo install --locked boundless-cli
export PATH=$PATH:/root/.cargo/bin
source ~/.bashrc

# Verify boundless-cli:
boundless -h

# Install Just
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
cargo install just
just --version
`
