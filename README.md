**M.Rifky Erlangga_TK@B# Sistem-Operasi**
# Praktikum 5: Job Control
## Struktur Direktori
```
Praktikum-5-JobControl/
│── README.md
│── scripts/
│   ├── setup_profiles.sh
│   ├── prompt_ps1.sh
│   ├── logout_message.sh
│   ├── p1.sh
│   ├── p2.sh
│   ├── p3.sh
│   ├── p4.sh
│   ├── jobs.sh
│── .gitignore
```

## Instalasi & Penggunaan
1. Clone repositori:
   ```bash
   git clone https://github.com/username/Praktikum-5-JobControl.git
   cd Praktikum-5-JobControl/scripts
   ```
2. Jalankan script setup_profiles.sh untuk mengatur profile shell:
   ```bash
   bash setup_profiles.sh
   ```
3. Jalankan script untuk prompt PS1:
   ```bash
   bash prompt_ps1.sh
   ```
4. Jalankan logout message setup:
   ```bash
   bash logout_message.sh
   ```
5. Menjalankan script jobs:
   ```bash
   bash jobs.sh &
   ```
6. Menjalankan script p1, p2, p3, dan p4:
   ```bash
   bash p1.sh
   bash p2.sh
   bash p3.sh
   bash p4.sh
   ```

## Konfigurasi Tambahan
- Mengatur **history size** menjadi 20:
  ```bash
  echo 'HISTSIZE=20' >> ~/.bashrc
  echo 'HISTFILESIZE=20' >> ~/.bashrc
  ```
- Menjalankan history terakhir:
  ```bash
  !!
  ```
- Mengulang perintah dengan prefix tertentu:
  ```bash
  !ls
  ```
