### Official Website
https://goldenminer.net/


### Download Link
Please visit the [Release Page](https://github.com/GoldenMinerNetwork/golden-miner-nockchain-gpu-miner/releases) to obtain the software.


### How to Get Your Pubkey
You can generate one locally using [nockchain-wallet](https://github.com/zorp-corp/nockchain?tab=readme-ov-file#install-wallet)

### Proxy
***If you have multiple machines, we strongly recommend using the [proxy](https://github.com/GoldenMinerNetwork/golden-miner-nockchain-gpu-miner/blob/main/proxy.md) software. It will effectively reduce your network requirements and help you achieve a more stable hashrate.***

### Run Commands
First, give the software permission to run
```bash
chmod +x ./golden-miner-pool-prover
```

#### Minimal Command
```bash
./golden-miner-pool-prover --pubkey=<your-pubkey>
```

#### Common Command
```bash
./golden-miner-pool-prover --pubkey=<your-pubkey> --label=<group label of machine> --name=<machine name>
```

#### Parameters Explained

- `--label`: Marks which group/cluster the machine belongs to
  **Default**: `"default-label"`

- `--name`: Identifies the specific machine
  **Default**: Local hostname

#### Additional Optional Parameters
- `--threads-per-card=<n>`:
  Specifies how many CPU threads to allocate per GPU card.
  Affects task parallelism and memory usage.
  **Default**: Automatically determined based on your GPU memory and CPU cores.

- `--local-ip=<local ip>`:
  Specifies the machine’s local network IP address.
  If multiple local IPs exist, one will be chosen randomly.
  **Default**: Automatically detected.


### Software Runtime Environment
- Tested on **Ubuntu 22.04** and **Ubuntu 24.04**
- Currently only supports **Nvidia GPU**


### Important Notes
We use the tuple **(label, name, local-ip)** to **uniquely identify** and display your machine on the website.
If multiple machines share the same combination of these three values,
the website may only display the speed of **one** machine.
However, **this will not affect your actual earnings**.
