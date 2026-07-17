### Official Website
https://goldenminer.net/


### Download Link
Please visit the [Release Page](https://github.com/GoldenMinerNetwork/golden-miner-nockchain-gpu-miner/releases) to obtain the software.


### How to Get Your Pubkey (Address)

You can obtain an address by using the [iris wallet](https://www.iriswallet.io/). Please make sure to keep your mnemonic phrase safe.

We strongly advise against mining directly to an exchange address. Doing so may lead to various unexpected issues on the exchange's end. The recommended approach is to mine to an address you create yourself via the Iris Wallet, which ensures you maintain full ownership and control of your assets.

~~You can generate one locally using [nockchain-wallet](https://github.com/zorp-corp/nockchain?tab=readme-ov-file#install-wallet). If you encounter a lot of issues during compilation that you can’t resolve, and you trust us, you can download it from [here](https://github.com/GoldenMinerNetwork/nockchain-wallet/releases) . We strongly recommend that you compile directly from the source code.~~

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

Starting from version 0.1.5+1, if there is a `config.toml` file in the software's running directory, its configuration will be given priority
The configurations in `config.toml` are similar to the parameters.
example `config.toml`:
```toml
pubkey = "2ytTMttzXpc79BU9vtVNFkE3TWL15zedV8WZUHSpJwCLzUoHkh7GdZ74CFj2JbQg1gMfZxQCT5bRiDAk5ZHpDUDtD2GTxJQciTuNPuXc9hEm4cGv53kCEyxVETaiBW2HiPoX"
label = "cluster-A"
name = "machine-0"
threads-per-card = 2
```
You can also configure other command-line parameters in `config.toml`. The proxy supports the same functionality.

#### Parameters Explained

- `--label`: Marks which group/cluster the machine belongs to
  **Default**: `"default-label"`

- `--name`: Identifies the specific machine
  **Default**: Local hostname

#### Additional Optional Parameters
- `--mode=<auto|gpu|hybrid>`:
  - **auto** – Automatically selects the optimal mode based on your CPU and GPU configuration.  
  - **hybrid** – Utilizes both CPU and GPU at the same time. If your CPU is powerful, this mode may deliver around **10% performance improvement** compared to pure GPU mode.  
  - **gpu** – Runs entirely on the GPU with **no CPU dependency**.
- `--gpu`:
  Specify which GPUs to use for execution.  For example, use `--gpu=0,1` to run the software on the first and second GPU. 
- `--threads-per-card=<n>`:
  Specifies how many CPU threads to allocate per GPU card.
  Affects task parallelism and memory usage.
  **Default**: Automatically determined based on your GPU memory and CPU cores.
  This value is usually set slightly higher than necessary. If you have limited memory and want to run on multiple GPUs at the same time, you can reduce this value — typically setting it to 1 or 2 should be sufficient.

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
