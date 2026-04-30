# Panduan Struktur Spreadsheet untuk Pengambilan MBG Per Kelas

## Deskripsi
Dokumen ini menjelaskan struktur dan kolom yang diperlukan untuk spreadsheet pengambilan MBG per kelas.

---

## Struktur Kolom Spreadsheet

Spreadsheet harus memiliki **8 kolom** dengan urutan sebagai berikut:

| No. | Nama Kolom | Tipe Data | Deskripsi | Contoh |
|-----|-----------|-----------|-----------|---------|
| 1 | **No** | Angka | Nomor urut kelas | 1, 2, 3, ... |
| 2 | **Tingkat Kelas** | Teks | Tingkat/jenjang kelas | Kelas 1, Kelas 2, ... |
| 3 | **Nama Kelas** | Teks | Nama atau identitas kelas | Kelas 1A, Kelas 1B, ... |
| 4 | **Wali Kelas** | Teks | Nama guru wali kelas | Ibu Siti, Pak Budi, ... |
| 5 | **Jumlah Siswa** | Angka | Jumlah siswa di kelas | 28, 30, 29, ... |
| 6 | **Status Pengambilan** | Teks | Status pengambilan MBG | Sudah Mengambil / Belum Mengambil |
| 7 | **Catatan** | Teks | Catatan tambahan (opsional) | Sudah diambil pagi ini, dll |
| 8 | **Tanggal Dibuat** | Tanggal | Tanggal data dibuat | 01/01/2024, 02/01/2024, ... |

---

## Contoh Data Spreadsheet

```
No | Tingkat Kelas | Nama Kelas | Wali Kelas | Jumlah Siswa | Status Pengambilan | Catatan | Tanggal Dibuat
---|---|---|---|---|---|---|---
1 | Kelas 1 | Kelas 1A | Ibu Siti | 28 | Belum Mengambil | Kelas dengan siswa aktif | 01/01/2024
2 | Kelas 1 | Kelas 1B | Pak Budi | 30 | Sudah Mengambil | | 01/01/2024
3 | Kelas 2 | Kelas 2A | Ibu Rina | 29 | Sudah Mengambil | Sudah diambil pagi ini | 01/01/2024
4 | Kelas 3 | Kelas 3A | Pak Ahmad | 31 | Belum Mengambil | | 01/01/2024
```

---

## Cara Menggunakan Export Data

### Opsi 1: Export ke CSV (Download File)
1. Klik tombol **"📊 Export ke Spreadsheet"** di aplikasi
2. File CSV akan otomatis diunduh dengan nama: `pengambilan-mbg-YYYY-MM-DD.csv`
3. Buka file dengan:
   - Microsoft Excel
   - Google Sheets
   - LibreOffice Calc
   - Atau aplikasi spreadsheet lainnya

### Opsi 2: Import ke Google Sheets
1. Klik tombol **"📊 Export ke Spreadsheet"**
2. Data akan disalin ke clipboard
3. Buka [Google Sheets](https://sheets.google.com)
4. Buat spreadsheet baru atau buka yang sudah ada
5. Klik pada sel **A1**
6. Paste data dengan **Ctrl+V** (Windows) atau **Cmd+V** (Mac)
7. Data akan otomatis terformat ke kolom-kolom

---

## Format Data yang Diekspor

### Format CSV
```csv
No,Tingkat Kelas,Nama Kelas,Wali Kelas,Jumlah Siswa,Status Pengambilan,Catatan,Tanggal Dibuat
1,"Kelas 1","Kelas 1A","Ibu Siti",28,"Belum Mengambil","Kelas dengan siswa aktif","01/01/2024"
2,"Kelas 1","Kelas 1B","Pak Budi",30,"Sudah Mengambil","","01/01/2024"
```

---

## Rekomendasi Formatting di Spreadsheet

Setelah data diimport, Anda dapat melakukan formatting berikut untuk tampilan yang lebih baik:

### 1. Header Row
- **Warna Background**: Biru atau warna lain yang kontras
- **Warna Text**: Putih
- **Bold**: Ya
- **Alignment**: Center

### 2. Kolom Status Pengambilan
- **Conditional Formatting**:
  - "Sudah Mengambil" → Background Hijau, Text Putih
  - "Belum Mengambil" → Background Merah, Text Putih

### 3. Kolom Jumlah Siswa
- **Alignment**: Center
- **Number Format**: Angka bulat (0)

### 4. Kolom Tanggal Dibuat
- **Format**: DD/MM/YYYY
- **Alignment**: Center

### 5. Semua Kolom
- **Border**: Tambahkan border untuk semua sel
- **Freeze Header**: Freeze baris pertama agar selalu terlihat saat scroll

---

## Fitur Tambahan yang Bisa Ditambahkan di Spreadsheet

### 1. Summary/Dashboard
Buat sheet terpisah dengan ringkasan:
- Total Kelas
- Total Sudah Mengambil
- Total Belum Mengambil
- Persentase Pengambilan

**Formula Contoh:**
```
Total Kelas: =COUNTA(Sheet1!A2:A)
Sudah Mengambil: =COUNTIF(Sheet1!F:F,"Sudah Mengambil")
Belum Mengambil: =COUNTIF(Sheet1!F:F,"Belum Mengambil")
Persentase: =SUDAH_MENGAMBIL/TOTAL_KELAS*100
```

### 2. Filter dan Sort
- Gunakan **Data > Create a filter** untuk memfilter berdasarkan:
  - Tingkat Kelas
  - Status Pengambilan
  - Wali Kelas

### 3. Chart/Grafik
- Buat pie chart untuk perbandingan "Sudah Mengambil" vs "Belum Mengambil"
- Buat bar chart untuk jumlah siswa per kelas

### 4. Pivot Table
- Buat pivot table untuk analisis lebih lanjut:
  - Jumlah kelas per tingkat
  - Total siswa per tingkat
  - Status pengambilan per tingkat

---

## Troubleshooting

### Data tidak terformat dengan benar
- Pastikan menggunakan delimiter koma (,) saat import
- Jika menggunakan paste langsung, Google Sheets akan otomatis mendeteksi format

### Karakter khusus tidak terbaca
- File CSV sudah menggunakan UTF-8 encoding
- Jika ada masalah, coba buka dengan aplikasi lain atau ubah encoding

### Catatan dengan koma tidak terbaca
- Catatan dengan koma sudah di-escape dengan tanda kutip (")
- Aplikasi spreadsheet akan menangani ini secara otomatis

---

## Tips Penggunaan

1. **Backup Reguler**: Simpan backup file CSV secara berkala
2. **Update Berkala**: Update status pengambilan secara real-time di aplikasi
3. **Share dengan Tim**: Bagikan link Google Sheets dengan tim untuk kolaborasi
4. **Archive Data**: Buat sheet terpisah untuk data bulan-bulan sebelumnya
5. **Print Report**: Gunakan fitur print di Google Sheets untuk membuat laporan fisik

---

## Kontak & Support

Jika ada pertanyaan atau masalah dengan export data, silakan hubungi administrator sistem.
