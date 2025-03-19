Penulis: [sbjnk](https://x.com/sbjnk_)

# Pengenalan
Bab ini berisi pengenalan mengenai T3RN Executor

## T3RN
> [!NOTE]
> Modular, Cross chain, Polkadot eco

### Investor
![Screenshot 2025-03-19 052400](https://github.com/user-attachments/assets/cbfbbdaa-b1e2-4027-b574-8b581c08e83d)


# Tutorial T3RN
Bab ini berisi tutorial cara menjalankan T3RN Executor

## Requirement
Syarat menjalankan T3RN Executor
- Spek Komputer
  
| Name | Minimum |
| ------------- | ------------- |
| Operating System  | Linux, MacOS, Windows(WSL)  |
| CPU  | 4 Cores  |
| RAM  | 8 GB  |
| SSD  | 200 GB  |


> [!TIP]
> Kami menggunakan Contabo dengan speksifikasi `Linux/ 4 Core/ 8 GB RAM/ 200 GB SSD`.
  
## Dependencies

### Update
```
sudo apt update && apt upgrade
```

### Buat direktori t3rn
```
mkdir t3rn && cd t3rn
```

### Download latest release
```
curl -s https://api.github.com/repos/t3rn/executor-release/releases/latest | \
grep -Po '"tag_name": "\K.*?(?=")' | \
xargs -I {} wget https://github.com/t3rn/executor-release/releases/download/{}/executor-linux-{}.tar.gz
```

### Ekstrak arsip
```
tar -xzf executor-linux-*.tar.gz
```

### Navigasi ke folder BIN
```
cd executor/executor/bin
```

### Setting Enviroment
```
export ENVIRONMENT=testnet
export LOG_LEVEL=debug
export LOG_PRETTY=false
export EXECUTOR_PROCESS_BIDS_ENABLED=true
export EXECUTOR_PROCESS_ORDERS_ENABLED=true
export EXECUTOR_PROCESS_CLAIMS_ENABLED=true
```

### Set network & RPC
```
export ENABLED_NETWORKS='arbitrum-sepolia,base-sepolia,optimism-sepolia,l2rn'
```

### Set RPC URL
```
export RPC_ENDPOINTS='{
    "l2rn": ["https://b2n.rpc.caldera.xyz/http"],
    "arbt": ["https://arbitrum-sepolia.drpc.org", "https://sepolia-rollup.arbitrum.io/rpc"],
    "bast": ["https://base-sepolia-rpc.publicnode.com", "https://base-sepolia.drpc.org"],
    "opst": ["https://sepolia.optimism.io", "https://optimism-sepolia.drpc.org"],
    "unit": ["https://unichain-sepolia.drpc.org", "https://sepolia.unichain.org"]
}'
```

### Set Private Key (bisa bikin wallet baru dulu di Rabby/Metamask
```
export PRIVATE_KEY_LOCAL=private key kalian
```

### Claim faucet menggunakan address yang telah dibuat
| Name | Link Faucet |
| ------------- | ------------- |
| BRN  | https://faucet.brn.t3rn.io/ |
| ARB Sepo  | https://arbitrum.faucet.dev/ArbSepolia |
| OP Sepo  | https://docs.optimism.io/app-developers/tools/build/faucets |

## Cara menjalankan T3RN Executor

### Untuk bisa running di background, kita pake screen (bagi yang udah install screen bisa skip cara ini)
```
sudo apt-get install screen

screen -Rd tern

cd t3rn

cd executor/executor/bin
```

### Menjalan Executor
```
./executor
```
### Jika muncul log seperti dibawah berarti berhasil! kalian bisa menutup screen nya dengan cara CTRL + A + D
![Screenshot 2025-03-19 065901](https://github.com/user-attachments/assets/326b3406-aa86-437d-bfc9-30c6c5e5639d)


## Help

Join komunitas [Discord ZuperHunt](https://t.co/n7TeWVlA48) jika kamu ada pertanyaan.

## Change Logs

* 0.0.1
    * Initial Release

## Acknowledgments

Referensi
* [Binary Setup by t3rn](https://docs.t3rn.io/executor/become-an-executor/binary-setup)
