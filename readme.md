# Python for Serve Your Static 🚀

Sebuah proyek demonstrasi untuk membangun server web statis lokal (Localhost) menggunakan fitur bawaan Python (`http.server`). Proyek ini mensimulasikan bagaimana sebuah sistem Computer Based Test (CBT) atau aplikasi web statis dapat diakses oleh banyak perangkat (HP/Laptop) dalam satu jaringan yang sama tanpa memerlukan koneksi internet aktif.

## 📖 Deskripsi Proyek

Proyek ini dibangun untuk memahami konsep dasar jaringan *Client-Server* pada Local Area Network (LAN) atau WLAN. Dengan memanfaatkan Python, kita menyulap sebuah laptop (Windows) menjadi server mini yang mendistribusikan file HTML statis ke perangkat lain (seperti *smartphone*) melalui jaringan WiFi.

Konsep ini sangat berguna untuk skenario **Ujian Berbasis Komputer (Offline CBT)** di sekolah atau institusi yang menginginkan peserta ujian tidak memiliki akses ke internet luar (mencegah kecurangan/browsing), namun tetap bisa mengakses halaman soal ujian.

## ✨ Fitur Utama
*   **Zero-Installation Server**: Tidak memerlukan aplikasi web server berat seperti Apache, Nginx, atau XAMPP. Cukup Python bawaan.
*   **Cross-Device Accessible**: Halaman web bisa dibuka dari OS apapun (Android, iOS, macOS, dll) selama terhubung di jaringan yang sama.
*   **Offline Capable**: Dapat berjalan 100% tanpa koneksi internet pusat (hanya mengandalkan sinyal WiFi dari router lokal).

## 🛠️ Prasyarat (Prerequisites)
1. Perangkat Server (Laptop/PC) dengan sistem operasi Windows/Linux/macOS.
2. [Python 3.x](https://www.python.org/downloads/) terinstal di perangkat Server (diuji menggunakan Python 3.10+).
3. Jaringan WiFi yang sama (Router Home WiFi atau Router Offline seperti TP-Link TL-WR840N).

## 🚀 Cara Menjalankan (How to Run)

### 1. Menyiapkan File Statis
Buat sebuah folder proyek (misal: `proyekIseng`), buka **Command Prompt (CMD)** di folder tersebut, dan buat file `index.html`:
```bash
notepad index.html
```
Isi dengan kode HTML statis sederhana, lalu simpan.

### 2. Menjalankan Server Python
Di jendela CMD yang sama, jalankan perintah berikut untuk mengaktifkan server di *port* 8000:
```bash
python -m http.server 8000
```
*(Izinkan akses jika muncul notifikasi dari Windows Defender Firewall).*

### 3. Mencari IPv4 Address Server
Buka jendela CMD baru, lalu ketik:
```bash
ipconfig
```
Cari bagian `Wireless LAN adapter Wi-Fi` dan catat angka pada **IPv4 Address** (contoh: `192.168.1.10`).

### 4. Mengakses dari Perangkat Client (HP)
Pastikan HP terhubung ke WiFi yang sama dengan laptop. Buka browser di HP dan ketikkan IP address beserta port tadi:
```text
http://192.168.1.10:8000
```
Halaman web akan langsung dirender di layar HP.

---

## 📡 Skenario Topologi Jaringan (Ujian Offline)

Proyek ini dirancang untuk bisa berjalan di skenario **Isolasi Jaringan (Tanpa Internet)**.

```text
[Modem Internet Rumah] ──► (TIDAK DISAMBUNGKAN)
        │
[Router Cadangan/Access Point] ──WiFi──► [HP Peserta / Client]
        │
        └──LAN/WiFi──► [Laptop Server / Python HTTP Server]
```

**Penjelasan:**
* Router cadangan hanya berfungsi sebagai terminal pengirim sinyal WiFi (Intranet), tanpa ada kabel internet masuk (WAN kosong).
* Peserta tidak bisa mengakses Google atau *browsing* jawaban.
* Server Python menyiarkan file statis di jaringan tertutup, menjaga ujian tetap aman, cepat, dan menghemat bandwidth kuota internet.

## 👤 Author
**irawanfree** - *Networking & Static Web Serving Experiment*
