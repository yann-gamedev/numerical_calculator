# Numerical Root Finder

Aplikasi HTML statis untuk metode Newton-Raphson, Bisection, Regula Falsi, dan Secant.

## Environment

- Tidak membutuhkan backend, build, package manager, atau environment variable.
- Browser memerlukan internet untuk memuat Tailwind CSS, Math.js, Chart.js, dan Google Fonts dari CDN.
- Jangan menaruh secret/API key dalam HTML: semua kode frontend dapat dilihat pengunjung.
- Tailwind saat ini menggunakan Play CDN (untuk pengembangan). Untuk produksi jangka panjang, sebaiknya kompilasi CSS dan pin versi seluruh dependensi CDN.

## Deploy melalui Git + Vercel

Folder ini belum diinisialisasi sebagai repository Git. Buat repository kosong di GitHub, lalu jalankan dari folder proyek:

```powershell
git init
git add .
git commit -m "Prepare static app for Vercel"
git branch -M main
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```

Ganti USERNAME dan REPOSITORY dengan repository tujuan Anda.

1. Di Vercel, pilih **Add New > Project**, kemudian import repository tersebut.
2. Gunakan **Framework Preset: Other** dan **Root Directory: .**.
3. Tidak perlu Build Command atau Install Command; Output Directory adalah `.` (diatur dalam konfigurasi).
4. Biarkan Environment Variables kosong, lalu pilih **Deploy**.
5. Push berikutnya ke branch production memicu deployment otomatis.

Konfigurasi Vercel memetakan URL `/` ke halaman aplikasi tanpa mengganti nama file sumber. URL `/numerical_root_finder.html` juga tetap tersedia. Rute lain tidak diarahkan otomatis ke aplikasi.

## Alternatif: deploy langsung lewat CLI

Memerlukan Node.js dan npm, tetapi tidak memerlukan repository Git:

```powershell
npx vercel@latest
```

Login dan hubungkan proyek ketika diminta. Perintah tersebut membuat preview deployment. Setelah preview diperiksa:

```powershell
npx vercel@latest --prod
```

Folder `.vercel` dan file `.env*` diabaikan agar konfigurasi lokal dan secret tidak ikut diunggah.

## Pemeriksaan setelah deploy

- Buka URL utama `/` dan pastikan aplikasi tampil.
- Hitung fungsi default `x^3 - x - 2`; akar mendekati `1.52138`.
- Periksa grafik dan coba keempat metode.
- Pastikan Console/Network browser tidak menunjukkan kegagalan pemuatan CDN.

Deployment ke akun Vercel belum dijalankan oleh proses penyiapan ini.
