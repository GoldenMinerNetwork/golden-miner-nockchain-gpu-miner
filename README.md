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
- `--gpu`:
  Specify which GPUs to use for execution.  For example, use `--gpu=0,1` to run the software on the first and second GPU. 
- `--gpu-memory-percentage`:
  Max GPU memory usage (percentage). Accepts any integer from 1 to 100. Setting this too low may cause the application to crash. The default value (100) is recommended.
- `--threads-per-card=<n>`:
  Specifies how many CPU threads to allocate per GPU card.
  Affects task parallelism and memory usage.
  **Default**: Automatically determined based on your GPU memory and CPU cores.
  This value is usually set slightly higher than necessary. If you have limited memory and want to run on multiple GPUs at the same time, you can reduce this value — typically setting it to 1 or 2 should be sufficient.

- `--local-ip=<local ip>`:
  Specifies the machine’s local network IP address.
  If multiple local IPs exist, one will be chosen randomly.
  **Default**: Automatically detected.

#### HiveOS
To set up a custom HiveOS Flight Sheet, you need to fill in the following parameters:
- `Miner name`: golden_miner_hiveos
- `Installation URL`: The GitHub download link for the latest version, for example: https://github.com/GoldenMinerNetwork/golden-miner-nockchain-gpu-miner/releases/download/v0.4.3/golden_miner_hiveos-0.4.3.tar.gz
- `Hash algorithm`: No selection required.
- `Wallet and worker template`: Enter any value (this field cannot be left empty).
- `Pool URL`: Enter any value (this field cannot be left empty).
- `Extra config arguments`: Please refer to the parameters mentioned earlier in the documentation, for example: --pubkey=<your address>

![HiveOS example](https://private-user-images.githubusercontent.com/231620692/524764589-3363d191-6d41-4fc7-9861-b06b0888f4d7.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODQzMTU3MzcsIm5iZiI6MTc4NDMxNTQzNywicGF0aCI6Ii8yMzE2MjA2OTIvNTI0NzY0NTg5LTMzNjNkMTkxLTZkNDEtNGZjNy05ODYxLWIwNmIwODg4ZjRkNy5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzE3JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcxN1QxOTEwMzdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02Mjk2YjAwMDgyNzZiMDM3MjkyYTQwMGM1NWQ1ZTc5OGNhOGUxMGZlNTUyNWU1Y2I1NWMyZjg2MGQyNzRjMGQwJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.Nv9udnPmx8R47uQrFx4aI4eKlIbJeeI_Eorg35YbxxQ)


### Software Runtime Environment
- Tested on **Ubuntu 22.04** and **Ubuntu 24.04**
- Currently only supports **Nvidia GPU**


### Important Notes
We use the tuple **(label, name, local-ip)** to **uniquely identify** and display your machine on the website.
If multiple machines share the same combination of these three values,
the website may only display the speed of **one** machine.
However, **this will not affect your actual earnings**.
