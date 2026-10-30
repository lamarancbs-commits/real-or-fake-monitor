# Real or Fake Monitor

Website mobile untuk mengecek apakah foto menu makanan asli atau buatan AI. Pengunjung tidak perlu login.

## Isi folder

- `index.html`: halaman website
- `api/analyze.js`: fungsi server yang mengirim foto ke model AI Claude lalu mengembalikan hasil
- `Nexa-ExtraLight.ttf`, `Nexa-Heavy.ttf`, `monimer.otf`: font
- `soto.jpg`: foto di halaman awal dan contoh hasil

## Cara online-kan

### 1. API key (console.anthropic.com)
1. Daftar di console.anthropic.com.
2. Billing: isi saldo kecil, lalu pasang spend limit.
3. API Keys: Create Key. Simpan key di catatan pribadi. Jangan dibagikan ke siapa pun.

### 2. GitHub
1. Buat akun di github.com.
2. New repository, nama `real-or-fake-monitor`, pilih Public atau Private.
3. Add file, Upload files: masukkan SEMUA isi folder ini, termasuk folder `api`. Klik Commit changes.

### 3. Vercel
1. Daftar di vercel.com memakai akun GitHub.
2. Add New, Project, pilih repo `real-or-fake-monitor`, Import.
3. Environment Variables:
   - `ANTHROPIC_API_KEY` = key dari langkah 1
4. Deploy. Link publik muncul setelah sekitar 1 menit.

### Pengaturan tambahan (opsional, lewat Environment Variables)
- `ANTHROPIC_MODEL`: default `claude-sonnet-5-5`. Isi `claude-haiku-5-5` untuk biaya lebih murah.
- `PER_IP_PER_DAY`: batas analisis per pengunjung per hari, default 15.
- `TOTAL_PER_DAY`: batas total analisis per hari, default 300.

Batas di atas bersifat perkiraan karena server bisa restart. Pengaman biaya yang pasti adalah spend limit di Anthropic Console.

## Catatan
- Foto diperkecil di HP sebelum dikirim dan tidak disimpan di server.
- Kalau analisis gagal atau batas harian tercapai, halaman menampilkan contoh hasil dengan label "Contoh hasil".
- Font Monimer Serif berlisensi personal use. Untuk pemakaian komersial, beli lisensinya di mansgreback.com.
