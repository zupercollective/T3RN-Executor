Penulis: [sbjnk](https://x.com/sbjnk_)

# Pengenalan
Bab ini berisi pengenalan mengenai T3RN Executor

## T3RN
> [!NOTE]
> Modular, Cross chain, Polkadot eco

### Investor
![Screenshot 2025-03-19 052400](https://github.com/user-attachments/assets/cbfbbdaa-b1e2-4027-b574-8b581c08e83d)


# Tutorial XXX
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
- item_2_dan_seterusnya_jika_ada

> [!TIP]
> Kami menggunakan Contabo dengan speksifikasi `Linux/ 4 Core/ 8 GB RAM/ 200 GB SSD`. Jika kamu membutuhkan VPS, kami memiliki link gratis credit VPS DigitalOcean sebesar $200. Cukup untuk menjalankan XXX selama XX . Daftar sekarang dengan [link utama](link_reff_do_kamu) / [link cadangan](link_reff_do_2_kamu) untuk mendapatkannya.
  
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

### Ekstrak
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
export PRIVATE_KEY_LOCAL=isi private key kalian
```

### Claim faucet menggunakan address yang telah dibuat
```
https://faucet.brn.t3rn.io/
```

## Cara menjalankan T3RN Executor

### Untuk bisa running di background, kita pake screen (bagi yang udah install screen bisa skip cara ini)
```
sudo apt-get install screen

screen -Rd tern
```

## Help

Join komunitas [Discord ZuperHunt](https://t.co/n7TeWVlA48) jika kamu ada pertanyaan.

## Change Logs

* 0.0.1
    * Initial Release

## Acknowledgments

Referensi
* [nama_referensi](link_referensi)
