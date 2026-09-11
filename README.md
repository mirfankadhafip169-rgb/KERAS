# Filter Withdraw

Aplikasi web lokal untuk **filter & format data withdraw** + matching **NTT ⇄ Vendor → DOC**.

## Fitur

### Tab REVIEW
- Paste data review → otomatis filter & format
- **Filter Jenis multi-checkbox** (bisa pilih 1 atau lebih bank/e-wallet)
- Auto-prefix e-wallet (DANA, OVO, GOPAY, LINKAJA)
- Deteksi antrian lama (batas menit dapat diatur)
- Copy hasil TSV siap paste ke Excel

### Tab ADMIN Withdraw
- Filter berdasarkan batas nominal maksimal
- Auto-prefix e-wallet
- Deteksi antrian lama

### Tab NTT ⇄ VENDOR → DOC
- Matching berdasarkan **Kode NTT + No. Rek + Nominal**
- Anti-dobel, auto-clear setiap ganti hari
- **MODE MINERA** — format data mentah berbeda (toggle di panel NTT)
- Filter status match, trace, verifikasi keamanan
- 100% lokal (data hanya di browser)

## Cara Pakai

1. Buka `index.html` di browser (atau deploy ke Netlify/GitHub Pages).
2. Tab **REVIEW** / **ADMIN**: paste data → hasil muncul otomatis.
3. Tab **NTT**:
   - Mode normal: paste format NTT biasa.
   - Centang **MODE MINERA** → paste format Minera.
4. Semua pengaturan (filter bank, batas menit, threshold, mode) tersimpan di `localStorage`.

## Struktur File

```
filter-withdraw/
├── index.html      # Halaman utama + tab REVIEW & ADMIN
├── script.js       # Logika filter REVIEW & ADMIN
├── style.css       # Style utama
├── ntt.html        # Tool matching NTT ⇄ Vendor → DOC (iframe)
└── README.md
```

## Catatan

- Tidak ada backend. Semua proses di browser.
- Data NTT/Vendor otomatis dibersihkan setiap ganti hari (berdasarkan tanggal lokal).
- Compatible dengan Chrome, Edge, Firefox terbaru.
