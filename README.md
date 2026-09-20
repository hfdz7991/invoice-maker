# Invoice Maker

Aplikasi pembuat invoice untuk usaha jasa maupun barang dalam **satu file HTML** — tanpa instalasi, tanpa internet, tanpa dependensi.

## Cara Pakai

1. Unduh `invoice-maker.html`
2. Buka file-nya di browser (dobel-klik)
3. Isi profil usaha di menu **Pengaturan** (nama, logo, alamat, rekening)
4. Buat invoice lewat menu **Buat Invoice**, lalu klik **Unduh PDF**

Data tersimpan otomatis di browser (localStorage). Gunakan **Ekspor/Impor JSON** di Pengaturan sebagai cadangan atau untuk memindahkan data ke komputer lain.

## Fitur

- Invoice untuk **jasa** maupun **barang** (toggle tipe: label & satuan menyesuaikan)
- Live preview A4 dengan tombol **Perbesar**
- Unduh **PDF** langsung dari browser (generator PDF builtin, hasil rapi multi-halaman)
- Penomoran otomatis `INV/YYYY/MM/NNN` (bisa dioverride)
- Diskon per item, diskon global, pajak %, ongkir/biaya tambahan
- Terbilang rupiah otomatis
- Direktori klien tersimpan + autocomplete
- Status invoice: Draft / Terkirim / Lunas / Batal, dengan filter & pencarian
- Kalkulasi desimal 2 digit, pembulatan per langkah
- Ekspor / Impor semua data (JSON)

## Catatan

- Data tersimpan per-browser pada domain aplikasi — gunakan Ekspor → Impor untuk memindahkan data antar perangkat
- 100% offline: tidak ada server, tidak ada API, tidak ada tracking

## Deploy (Cloudflare Workers)

Aplikasi ini murni client-side, sehingga cukup disajikan sebagai aset statis:

```bash
npx wrangler deploy
```

Sudah live di: https://invoice-maker.howfidz.workers.dev

> Catatan: `public/index.html` adalah salinan dari `invoice-maker.html`.
> Jika mengubah aplikasi, salin ulang ke `public/` sebelum deploy.
