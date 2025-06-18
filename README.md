# 💠 Craft World Bot - LYAMRIZZ INSIDER

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Status](https://img.shields.io/badge/status-stable-success)
![License](https://img.shields.io/badge/license-MIT-green)
![Made By](https://img.shields.io/badge/created%20by-ZeroDev%20%26%20Lyamrizz-magenta)

Bot otomatis untuk mengelola aktivitas akun di [Craft World](https://preview.craft-world.gg), mendukung banyak akun, auto-sync GraphQL, dan otomatisasi aksi seperti:

- ✅ **Claim Area**
- 🏭 **Start & Upgrade Factory**
- ⛏️ **Claim, Start & Upgrade Mine**
- 🔄 **Auto Sync Data dari GraphQL ke config**

> Dibuat dan dikembangkan oleh **ZeroDev** dan **Lyamrizz**  
> Untuk keperluan otomatisasi personal game *Craft World (preview.craft-world.gg)*

---

## 🔧 Fitur Utama

- 🔁 **Auto loop setiap 30 detik**
- 🔑 **Auto fetch token via Firebase `refresh_token`**
- 🧠 **Intelligent GraphQL sync**: data `mine`, `factory`, dan `area` diambil dan disimpan otomatis
- 👥 **Multi-akun support** (hingga akun tak terbatas sesuai config)
- 🖥️ **CLI dengan UI Rich (warna, panel, ikon emoji)**

---

## 🚀 Instalasi

### 1. Clone repository

```bash
git clone https://github.com/robiyann/craft.git
cd craft
```

### 2. Install dependensi Python

```bash
pip install -r requirements.txt
```

---

## ⚙️ Konfigurasi `config.json`

Buat file `config.json` di folder yang sama dengan `bot.py`. Contoh untuk 5 akun:

```json
{
  "apiKey_1": "API_KEY_AKUN_1",
  "refresh_token_1": "REFRESH_TOKEN_AKUN_1",

  "apiKey_2": "API_KEY_AKUN_2",
  "refresh_token_2": "REFRESH_TOKEN_AKUN_2",

  "apiKey_3": "API_KEY_AKUN_3",
  "refresh_token_3": "REFRESH_TOKEN_AKUN_3",

  "apiKey_4": "API_KEY_AKUN_4",
  "refresh_token_4": "REFRESH_TOKEN_AKUN_4",

  "apiKey_5": "API_KEY_AKUN_5",
  "refresh_token_5": "REFRESH_TOKEN_AKUN_5"
}
```

📌 `refresh_token` dan `apiKey` bisa kamu ambil melalui DevTools browser saat login Craft World.

saat game dijalankan, pencet f12 atau devtools, cari dibagian application - indexedDB - firebaselocalstoragedb -firebaselocalstorage - lalu copy bagian refresh token dan apikey di bagian value nya
![image](https://github.com/user-attachments/assets/57cc7fbc-c92f-490d-b74c-aea5645dac17)

---

## ▶️ Menjalankan Bot

```bash
python craftworld.py
```

✅ Bot akan:
- Ambil data terbaru dari GraphQL
- Update otomatis `mineIds`, `areaIds`, `factoryIds` di `config.json`
- Eksekusi aksi:
  - Claim semua area
  - Start + upgrade semua factory
  - Claim, upgrade, dan start semua mine

🕒 Bot akan melakukan loop otomatis setiap 30 detik.

---

## 🧩 Troubleshooting

| Masalah                                   | Solusi                                                                 |
|-------------------------------------------|------------------------------------------------------------------------|
| `401 Unauthorized`                        | Periksa `refresh_token` dan `apiKey` sudah valid dan tidak expired     |
| `config.json` tidak terbaca               | Pastikan file valid JSON dan ada di direktori yang sama dengan `bot.py`|
| Tidak ada aksi berjalan                   | Tunggu 30 detik; pastikan ID-ID tersinkron dari GraphQL               |

---

## 📦 Struktur Direktori

```
craft/
├── bot.py              # Main bot script
├── config.json         # Konfigurasi akun-akun
├── requirements.txt    # Dependensi Python
└── README.md           # Dokumentasi
```

---

## 👨‍💻 Pengembang

> Dibuat dan dikembangkan oleh:
- 🧠 **ZeroDev**
- 🔮 **Lyamrizz**

---

## 📃 Lisensi

Proyek ini menggunakan lisensi **MIT**. Bebas digunakan dan dimodifikasi untuk keperluan pribadi.
