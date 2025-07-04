

---

## Instalasi dan Menjalankan WA-aichatbot di Android (via Termux & Ubuntu CLI)

### 1. Unduh dan Instal Aplikasi yang Dibutuhkan

* **Termux:** Unduh dari F-Droid (bukan dari Play Store) untuk versi yang stabil dan kompatibel:
   [Unduh Termux via F-Droid](https://f-droid.org/en/packages/com.termux/)

* **Andronix:** Unduh dari Play Store untuk menginstal sistem Linux di Android:
   [Unduh Andronix via Play Store](https://play.google.com/store/apps/details?id=studio.com.techriz.andronix&hl=id)

### 2. Persiapan Termux

Buka aplikasi Termux, lalu jalankan perintah berikut untuk memperbarui paket:

```bash
pkg update && pkg upgrade
```

Izinkan akses penyimpanan ke Termux:

```bash
termux-setup-storage
```

### 3. Instalasi Ubuntu via Andronix

* Buka aplikasi **Andronix**, masuk ke menu **Linux Distributions**.
* Pilih **Ubuntu 20**, kemudian pilih opsi **CLI Only** (tanpa antarmuka grafis agar ringan).
* Setelah menekan tombol *CLI Only*, akan muncul notifikasi bahwa skrip telah disalin.
* Buka kembali **Termux**, *paste* skrip tersebut, lalu jalankan. Tunggu hingga proses instalasi selesai.

### 4. Konfigurasi Dasar Ubuntu

Setelah berhasil masuk ke terminal Ubuntu, perbarui sistem:

```bash
apt update
```

Install dependensi yang diperlukan:

```bash
apt install git wget nano
```

### 5. Instalasi Node.js Menggunakan NVM

Ikuti petunjuk resmi NVM di sini:
 [NVM GitHub](https://github.com/nvm-sh/nvm)

Atau langsung gunakan skrip berikut untuk instalasi cepat:

```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
```

Setelah instalasi selesai, salin *export* code yang muncul di terminal, contohnya:

```bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

*Jangan salin contoh di atas, salin dari terminal Anda.*

### 6. Instal Node.js, NPM, dan PNPM

Setelah NVM aktif, jalankan:

```bash
nvm install v22
apt install npm
npm install -g pnpm
```

### 7. Clone dan Jalankan Proyek WA-Gemini

Clone repository:

```bash
git clone https://github.com/paijoe29/wa-aichatbot.git
cd wa-aichatbot
pnpm install
cp .env.example .env
```



Edit file `.env` untuk menambahkan API key dari Google Gemini:

* Buat API key terlebih dahulu:
   [Google AI Studio](https://aistudio.google.com/app/apikey)

* Edit file:

```bash
nano .env
```

Masukkan API key. Tekan `Ctrl + X`, lalu `Y` untuk menyimpan dan keluar.


Akses dashboard melalui browser:
 `http://localhost:3002`

Klik ke menu **starbot**, lalu **scan QR Code** menggunakan WhatsApp Anda untuk menautkan akun.

---

 **Proyek selesai. WA-aichatbot siap digunakan.**
