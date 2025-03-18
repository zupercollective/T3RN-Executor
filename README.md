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
grep -o '"tag_name": "[^"]*' | \
cut -d'"' -f4 | \
xargs -I {} curl -LO https://github.com/t3rn/executor-release/releases/download/{}/executor-macos-{}.tar.gz
```

### Ekstrak
```
tar -xzf executor-macos-*.tar.gz
```

### Navigasi ke folder BIN
```
cd executor/executor/bin
```

## Menjalankan XXX

### Run XXX
```
code blocks for commands
```

## Help

Join komunitas [Discord ZuperHunt](https://t.co/n7TeWVlA48) jika kamu ada pertanyaan.

## Change Logs

* 0.0.1
    * Initial Release

## Acknowledgments

Referensi
* [nama_referensi](link_referensi)
