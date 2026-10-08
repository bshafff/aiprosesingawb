# Memori Proyek: Dashboard Processing AWB

## 1. Deskripsi Proyek
Dashboard internal untuk memproses dan memonitor AWB (Air Waybill). 
Aplikasi berbasis web yang berjalan sebagai PWA (Progressive Web App) dengan backend Google Apps Script.

## 2. Stack & Arsitektur
- **Backend:** Google Apps Script (`Code.gs`)
- **Frontend:** HTML5, CSS3, Vanilla JavaScript (tanpa framework)
- **PWA:** Menggunakan `manifest.json` dan `sw.js` (Service Worker) untuk caching & offline mode
- **Entry Point:** `index.html` dan `home.html`

## 3. Struktur File & Modul
- **Core Logic:**
  - `app.js` : Logika utama aplikasi, routing, dan inisialisasi.
  - `core.js` : Fungsi utilitas bersama (helper, API calls, format data).
  - `style.css` : Styling global.
  - `sw.js` : Service Worker untuk PWA (caching aset, offline support).
- **Modul Dashboard:**
  - `dashboard-mika.html` + `mod-dashboard-mika.js`
  - `dashboard-panen.html` + `mod-dashboard-panen.js`
  - `rekap-panen.html` + `mod-rekap-panen.js`
  - `stok-mika.html` + `mod-stok-mika.js`
  - `lks.html` + `mod-lks.js`
- **Aset:**
  - `logo-awb.png` : Logo utama aplikasi.
  - `icon-192.png` & `icon-512.png` : Ikon PWA.

## 4. Aturan Pengembangan (Rules)
1. Selalu gunakan `core.js` untuk fungsi yang dipakai berulang kali. Jangan duplikasi kode di `mod-*.js`.
2. Setiap halaman dashboard punya file JS sendiri dengan prefix `mod-`.
3. Jangan mengubah `manifest.json` atau `sw.js` tanpa mengetes ulang PWA (pastikan tetap bisa offline).
4. Gunakan `logo-awb.png` untuk branding.
5. Backend `Code.gs` berkomunikasi dengan Google Sheets/Database. Pastikan format response konsisten (JSON).

## 5. Konteks Bisnis (AWB)
- AWB adalah dokumen farm. Dashboard ini memproses data AWB masuk, tracking status, dan rekap.
- Modul "Mika" dan "Panen" adalah bagian spesifik dari alur bisnis yang sedang dikerjakan.

## 6. TODO / Issue
- (Tambahkan di sini jika ada bug, fitur yang belum selesai, atau request dari user)
