# Tutorial The Power Testnet Node Airdrop Finder

<p style="font-size:14px" align="right">
<a href="https://t.me/airdropfind" target="_blank">Join Telegram Airdrop Finder<img src="https://user-images.githubusercontent.com/50621007/183283867-56b4d69f-bc6e-4939-b00a-72aa019d1aea.png" width="30"/></a>
</p>

<p align="center">
  <img height="auto" width="auto" src="https://raw.githubusercontent.com/bayy420-999/airdropfind/main/NavIcon.png">
</p>

## Referensi

[Dokumen resmi](https://doc.thepower.io/docs/Community/phase-2/testnet-flow)

[Server Discord Sao Network](https://discord.gg/FcTGw9v2ux)

[Telegram chat](https://t.me/thepower_chat)

[Registrasi (di telegram bot)](https://t.me/thepowerio_bot)

[Wallet](https://hub.thepower.io)

## Persyaratan hardware & software

### Persyaratan hardware

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|CPU|4 Cores|
|RAM|4 GB DDR4 RAM|
|Penyimpanan|40 GB SSD|
|Koneksi|10Mbit/s port|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|CPU|32 Cores|
|RAM|32 GB DDR4 RAM|
|Penyimpanan|2 x 1 TB NVMe SSD|
|Koneksi|1 Gbit/s port|

### Persyaratan software/OS

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|Sistem Operasi|Ubuntu 22.04|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|Sistem Operasi|Ubuntu 22.04|

## Setup

### Join Testnet

1. Buka https://t.me/thepowerio_bot
2. Start bot
3. Pilih `Testnet Campaign`
4. Pencet `Let's roll`
5. Pilih `Phase II`
6. Ikutin tutornya
7. Nanti bakal disuruh masukin address, Buat walletnya di https://hub.thepower.io
8. Next terus sampe keluar link seperti dibawah:
   ```console
   "http://c1040n14.deinfra.net:1080/?genesis=WsR0oYGe8k00IMpLH4I_g3R-_CEEQai_GJI5CU2tKVk",
   "http://c1040n17.deinfra.net:1080/?genesis=WsR0oYGe8k00IMpLH4I_g3R-_CEEQai_GJI5CU2tKVk",
   "http://c1040n16.deinfra.net:1080/?genesis=WsR0oYGe8k00IMpLH4I_g3R-_CEEQai_GJI5CU2tKVk"
   ```
9. Copy linknya
10. Done

### Cari PTR DNS Reserve

Contabo:
1. Buka https://my.contabo.com/rdns
2. Login pake account kalian
3. Copy DNS yang dibagian PTR Record

### Download & install Node

1. Install wget & curl
   ```console
   apt-get install wget curl
   ```
2. Download script
   ```console
   rm -rf run.sh
   wget https://raw.githubusercontent.com/bayy420-999/Tutorial-ThePower-Testnet-II-AirdropFinder/main/run.sh
   ```
3. Ganti permission file menjadi executable
   ```console
   chmod +x run.sh
   ```
4. Masukan Hostname (DNS yang dicopy tadi)
5. Masukan Upstream link (yang dicopy tadi) dengan format seperti dibawah:
   ```console
   "http://c1040n14.deinfra.net:1080/?genesis=WsR0oYGe8k00IMpLH4I_g3R-_CEEQai_GJI5CU2tKVk",
   "http://c1040n17.deinfra.net:1080/?genesis=WsR0oYGe8k00IMpLH4I_g3R-_CEEQai_GJI5CU2tKVk",
   "http://c1040n16.deinfra.net:1080/?genesis=WsR0oYGe8k00IMpLH4I_g3R-_CEEQai_GJI5CU2tKVk"
   ```
   Ubah jadi
   ```console
   "http://c1040n14.deinfra.net:1080/?genesis=WsR0oYGe8k00IMpLH4I_g3R-_CEEQai_GJI5CU2tKVk", "http://c1040n17.deinfra.net:1080/?genesis=WsR0oYGe8k00IMpLH4I_g3R-_CEEQai_GJI5CU2tKVk", "http://c1040n16.deinfra.net:1080/?genesis=WsR0oYGe8k00IMpLH4I_g3R-_CEEQai_GJI5CU2tKVk"
   ```
   (Hapus newline/enter)
6. Masukan email kalian
7. Tunggu sampai setup finished

### Jalankan Node
1. Masuk ke direktori Node
   ```console
   cd /opt/thepower
   ```
2. Jalankan Node
   ```console
   docker-compose up -d
   ```
3. Cek status Node
   ```console
   curl https://<hostname>:1443/api/node/status | jq
   ```
   Ganti hostname make DNS/Hostname kalian, contoh:
   ```console
   curl https://vmi1371906.contaboserver.net:1443/api/node/status | jq
   ```
   Jika berhasil maka akan keluar output seperti ini:
   ```json
   {
     "result": "ok",
     "status": {
       "blockchain": {
         "chain": 0,
         "hash": "3A25E164D15E5ABB92406AA832A47638BC89230F15CC5A1FF045C480C15055CF",
         "header": {
           "chain": 1040,
           "height": 26,
           "parent": "C01FE5BE5A577EE8594BE2046B381FE9519216B8DD6A116290DFC2E95D9BAC94",
           "roots": {
             "settings_hash": "6124F181A01382C42F896BDB8680CCDF9BE077BE58BA6E530E9A9364BB691D63",
             "ledger_hash": "7CA466E37B92D6AF6BBD1212FB6E29778E25AB9ACC6C7DFB6383A9DDC4B9EE76",
             "tmp": "00000000000013F1",
             "entropy": "",
             "mean_time": "00000186BC785C50"
           },
           "ver": 2
         },
         "signatures": [
           "c1040.oval",
           "c1040.fajrrmdhn",
           "c1040.brianfloria",
           "c1040.yitnosatino",
           "c1040.baninazar",
           "c1040.alfrianto",
           "c1040.nickname",
           "c1040.simpson",
           "c1040.novz",
           "c1040.jambicrypto",
           "c1040.lambo"
         ],
         "temporary": 5105
       },
       "blockchain_reader_lastblock": "undefined",
       "blockvote": {
         "block": 0,
         "candidates": [],
         "sig": 0,
         "signatures": []
       },
       "is_sync": "error",
       "nodeid": "47QWUC2e2zPB6Q6ikhxoGPZJY3w5",
       "nodename": "47QWUC2e2zPB6Q6ikhxoGPZJY3w5",
       "public_key": "302A300506032B65700321001D3BBAB27A6D26549125C9EDD8FFB4E33B92A70C370D1970CFEF73BEA63B3FE2",
       "sync_peers": [],
       "tpic_peers": [],
       "ver": "v0.14.8",
       "xchain_inbound": {
         "error": true
       },
       "xchain_outbound": {
         "error": true
       }
     },
     "ok": true
   }
   ```
4. Submit url ke bot
   Balik ke bot tadi terus submit url kalian ke bot, contoh url:
   ```console
   https://vmi1371906.contaboserver.net:1443/api/node/status
   ```
5. Done

## Perintah berguna

1. Menjalankan Node
   ```console
   docker-compose up -d
   ```
   (Pastikan kalian di folder `/opt/thepower`)
2. Matikan Node
   ```console
   docker-compose down
   ```
   (Pastikan kalian di folder `/opt/thepower`)
3. Matikan dan hapus data Node
   ```console
   docker-compose down -v
   ```
   (Pastikan kalian di folder `/opt/thepower`)
4. Cek status Node
   ```console
   curl https://<hostname>:1443/api/node/status | jq
   ```
5. Cek log Node
   ```console
   tail -f 100 /opt/thepower/log/info.log
   ```
6. Hapus Node secara keseluruhan
   ```console
   cd /opt/thepower && docker-compose down -v
   cd $HOME && rm -rf .acme.sh /opt/thepower /usr/local/bin/tp
   ```

## Troubleshoot
Reserved
