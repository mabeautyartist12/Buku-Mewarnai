# Buku Mewarnai

Generator prompt halaman aktivitas mewarnai edukatif (A4 portrait, siap cetak) berdasarkan Framework Buku Mewarnai by Evegrow.

Setiap parameter brief punya opsi siap pakai dan pilihan **Isi sendiri**. Prompt dibuat otomatis, bisa disalin atau diunduh .txt.

Situs statis (HTML + JavaScript), tanpa build step dan tanpa backend.

## Cara kerja
1. User mengisi parameter, lalu klik **Buka di ChatGPT**.
2. ChatGPT terbuka di tab baru dengan prompt sudah terisi di kolom chat (prompt juga otomatis tersalin ke clipboard sebagai cadangan, tinggal tekan Ctrl+V).
3. **Mode prompt lengkap** (default): prompt = isi framework PDF (otak AI, ada di `framework.js`) + parameter pengguna. Karena sangat panjang, prompt disalin ke clipboard dan ChatGPT dibuka; tempel dengan Ctrl+V lalu kirim.
4. **Mode GPT Evegrow** (disarankan): buat Custom GPT, tempel isi framework PDF ke Instructions, lalu isi kolom *Link GPT* di aplikasi (atau isi `DEFAULT_GPT` di `index.html`). Aplikasi hanya mengirim brief ringkas.

## Jalankan lokal
Buka `index.html` lewat browser (Safari/Chrome), jangan lewat pratinjau file. Atau jalankan `npx serve .`

## Deploy ke GitHub dan Vercel
1. Buat repository baru di GitHub (mis. `buku-mewarnai`), lalu unggah semua file di folder ini.
2. Buka vercel.com, klik **Add New â Project**, lalu import repository tersebut.
3. Framework Preset: **Other**. Biarkan Build Command dan Output Directory kosong. Klik **Deploy**.
4. Setiap push ke GitHub akan otomatis ter-deploy ulang.

## Jika link Vercel malah mengunduh file
- File harus bernama persis `index.html` (bukan `index`) dan berada di root repository, sejajar dengan `framework.js` dan `vercel.json`.
- Jangan unggah file .zip ke GitHub. Ekstrak dulu, lalu unggah isinya.
- Setelah memperbaiki, Vercel otomatis deploy ulang; buka link di tab baru.

## Kustomisasi
- Parameter dan opsi: array `FIELDS` di `index.html`.
- Template prompt: fungsi `build()` di `index.html`.
- Warna brand: variabel CSS `--p50` sampai `--p700` di bagian `:root`.

Â© Evegrow.Digital
