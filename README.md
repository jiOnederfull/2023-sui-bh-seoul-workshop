# 2023-sui-bh-seoul-workshop
- https://docs.sui.io/build/install
- https://docs.sui.io/build/connect-sui-network

## Install Prerequisites
- https://docs.sui.io/build/install#rust-and-cargo
- https://docs.sui.io/build/install#macos-prerequisites
1. Rust
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
```
1) Proceed with installation (default)
2) Customize installation
3) Cancel installation
>
```
```
source "$HOME/.cargo/env"
```
```
rustup update stable
```
2. Brew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
- Press RETURN/ENTER
```
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/onederfull/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```
3. cURL / CMake / Git CLI
```
brew install curl cmake git
```
## Install Sui Binaries - Devnet
- https://docs.sui.io/build/install#install-sui-binaries 
```
cargo install --locked --git https://github.com/MystenLabs/sui.git --branch devnet sui
```
- 해당 레포 git clone: `git clone https://github.com/jiOnederfull/2023-sui-bh-seoul-workshop`
```
mv sui_devnet_linux ~/.cargo/bin/sui
```
```
mv sui_devnet_mac ~/.cargo/bin/sui
```
### Environment Set up
- https://docs.sui.io/build/connect-sui-network#environment-set-up
```
which sui
```
- The command installs Sui components in the ~/.cargo/bin folder.
### Confirm the Installation
- https://docs.sui.io/build/install#confirm-the-installation
```
sui
```

## Configure Sui Client
- https://docs.sui.io/build/connect-sui-network#configure-sui-client
```
sui client
```
- Enter `y`
- Enter
- Enter `0` for selecting ed25519

> Generated new keypair for address with scheme "ed25519" [0xb9c83a8b40d3263c9ba40d551514fbac1f8c12e98a4005a0dac072d3549c2442]
> 
> Secret Recovery Phrase : [cap wheat many line human lazy few solid bored proud speed grocery]
```
cd ~/.sui
ls -al
cd sui_config
```
```
cat client.yaml
```
```
cat sui.keystore
```

## Connect to a custom RPC endpoint
- https://docs.sui.io/build/connect-sui-network#connect-to-a-custom-rpc-endpoint
```
sui client envs
```
```
sui client new-env --alias ATN_Mainnet --rpc https://sui-mainnet-rpc.allthatnode.com:443
```
```
sui client switch --env ATN_Mainnet
```

## Request Test Tokens
- https://docs.sui.io/build/connect-sui-network#request-test-tokens
- discord: https://discord.com/invite/sui
```
sui client active-address
```
```
!faucet <YOUR-CLIENT-ADDRESS>
```
- https://suiexplorer.com/

## Create a New Address
```
sui client new-address ed25519
```
```
sui client addresses
```
```
sui client switch --address <address>
```
