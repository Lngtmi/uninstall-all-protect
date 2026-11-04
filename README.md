# Uninstall All Protect

Script untuk **melepas semua protect/guard panel** dari VPS: Guard Reviactyl (termasuk Guard Manager + sudoers-nya) dan Protect Pterodactyl (termasuk Protect Manager + sudoers-nya) — file panel dipulihkan dari backup yang dibuat saat pemasangan.

Panel, database, Wings/Agent, dan data server **tidak** dihapus. Bila tidak ada protect yang terdeteksi, script berhenti tanpa mengubah apa pun.

```
uninstall-all-protect.sh
```

## Kebutuhan

- Dijalankan sebagai **root** di VPS tempat panel terinstall
- Panel Reviactyl di `/var/www/reviactyl` dan/atau Pterodactyl di `/var/www/pterodactyl`

## Cara Pakai — Bash (1 perintah)

Ini satu-satunya cara pakai yang disarankan. Tidak perlu download apa pun — jalankan di VPS panel sebagai root:

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/Lngtmi/uninstall-all-protect/main/uninstall-all-protect.sh)
```

## Yang dilakukan

- **Reviactyl:** middleware dipulihkan dari backup scoped, halaman Guard Manager + view-nya dihapus, `storage/app/guard-scripts` + `guard-config.json` dihapus, `/etc/sudoers.d/reviactyl-guard` dicabut.
- **Pterodactyl:** file yang diubah protect dipulihkan dari backup, Protect Manager (controller + view + config) dihapus, `/etc/sudoers.d/pterodactyl-protect` dicabut.
- Setiap file yang akan ditimpa saat pemulihan dibackup dulu dengan suffix `.uninstall-protect.<tanggal>.bak`.

## Kontak

Ada pertanyaan atau butuh bantuan? Hubungi saya di Telegram: [@pratamanie](https://t.me/pratamanie)

---
SOURCE CODE BY PRATAMA
