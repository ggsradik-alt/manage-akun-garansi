# SuperGrok Account Manager — Manage Akun Garansi

Aplikasi 1 file (`index.html`) untuk mencatat & mengelola daftar akun garansi beserta
**screenshot bukti order**, agar mudah ditinjau oleh team garansi.

## Fitur

### Manajemen akun
- Tambah / edit / hapus akun
- Field garansi lengkap: email, password, status, marketplace, order ID, tanggal order, tanggal claim, alasan claim, catatan
- Status: `Claim`, `Backfree`, `Suspend`, `OK`
- Pencarian (email, order ID, marketplace, catatan, alasan)
- Filter berdasarkan status
- Quick-claim & mass mark-as-claim
- Show/hide password

### Screenshot bukti order
- Upload via klik atau drag & drop, mendukung multi-file
- Otomatis dikompres (max 1600px, JPEG 85%) supaya hemat localStorage
- Preview lightbox (klik thumbnail untuk perbesar)
- Bisa dihapus per gambar

### Untuk team garansi
- **Export HTML self-contained** — 1 file HTML yang sudah berisi seluruh data + screenshot
  embed sebagai base64. Tinggal kirim via WA/Telegram/Email, team garansi cukup buka di
  browser tanpa perlu install apa pun. Mode read-only, ada filter, search, tombol cetak/PDF.
- **Cetak / Simpan PDF** — hasil export juga punya CSS print-friendly untuk dijadikan PDF.

### Backup & restore
- **Backup ke JSON** — download semua data (termasuk screenshot) sebagai file JSON
- **Restore dari JSON** — bisa pilih timpa atau gabung dengan data saat ini
- Data utama disimpan di `localStorage` browser

## Cara pakai

1. Buka `index.html` di browser (bisa dari komputer langsung, atau host di GitHub Pages).
2. Klik **+ Tambah Akun** untuk menambah, atau **Detail** pada baris untuk edit.
3. Di modal detail, drag & drop / klik area upload untuk menambah screenshot.
4. Setelah semua data lengkap, klik **📤 Export untuk Team Garansi** → file HTML akan terdownload.
5. Kirim file HTML hasil export tersebut ke team garansi.

## Catatan teknis

- Data tersimpan di `localStorage` browser (per-domain). Hapus cache = data hilang. **Selalu backup JSON secara berkala.**
- localStorage umumnya berkapasitas 5–10 MB. Aplikasi menampilkan ukuran tersimpan di status bar. Jika mendekati limit, hapus screenshot lama atau pindahkan ke backup.
- Tidak ada server / koneksi keluar — semua berjalan di browser.

## Hosting (opsional)

File ini bisa langsung di-host gratis via GitHub Pages:

1. Settings → Pages → Source: pilih branch `main`, folder `/ (root)`.
2. Tunggu beberapa detik, akses lewat `https://<user>.github.io/manage-akun-garansi/`.
