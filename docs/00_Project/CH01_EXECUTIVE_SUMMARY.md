---
chapter: CH01
title: Executive Summary
status: Draft
version: 1.0.0
last_updated: 2026-07-09
author: D'CrunchyWan + OpenAI
review_status: In Review
---

# Executive Summary

## 1. Latar Belakang

D'CrunchyWan POS v3 adalah sistem Point of Sale (POS) yang dikembangkan berdasarkan pengalaman operasional toko selama lebih dari dua tahun menggunakan Google Sheets dan Google Apps Script.

Selama periode tersebut, sistem telah membantu operasional harian, namun ditemukan beberapa keterbatasan yang semakin terasa seiring bertambahnya kompleksitas bisnis.

Beberapa kendala utama yang menjadi dasar pengembangan sistem baru adalah:

- Ketergantungan terhadap koneksi internet.
- Halaman mengalami error ketika browser direfresh dalam kondisi offline.
- Struktur aplikasi sulit dikembangkan menjadi Progressive Web App (PWA) yang stabil.
- Performa mulai menurun ketika jumlah data bertambah.
- Sulit melakukan sinkronisasi realtime yang andal.
- Dashboard owner dan operasional masih saling bergantung.

Blueprint ini disusun sebagai fondasi resmi pembangunan D'CrunchyWan POS v3 agar seluruh implementasi mengikuti satu sumber kebenaran (Single Source of Truth).

---

## 2. Tujuan Proyek

Tujuan utama proyek ini adalah membangun sistem POS modern yang memiliki karakteristik berikut:

### Untuk Kasir

- Cepat dipelajari.
- Dapat digunakan tanpa koneksi internet.
- Tidak kehilangan transaksi ketika browser direfresh.
- Antarmuka sederhana dengan jumlah klik seminimal mungkin.
- Tetap nyaman digunakan pada tablet Android.

### Untuk Owner

- Memiliki dashboard yang lengkap.
- Seluruh transaksi dapat diaudit.
- Rekonsiliasi QRIS menjadi lebih mudah.
- Perubahan harga tercatat.
- Laporan dapat diakses dari mana saja.

### Untuk Pengembangan

- Mudah dipelihara.
- Mudah dikembangkan.
- Memiliki dokumentasi lengkap.
- Menggunakan arsitektur modern.


---

## 3. Visi Proyek

Visi utama D'CrunchyWan POS v3 adalah menjadi sistem Point of Sale yang mampu mendukung operasional toko secara cepat, stabil, dan mudah digunakan, tanpa mengorbankan kualitas data maupun fleksibilitas pengembangan di masa depan.

Proyek ini dibangun berdasarkan pengalaman operasional nyata, sehingga setiap fitur memiliki tujuan bisnis yang jelas dan bukan sekadar menambah kompleksitas aplikasi.

Prinsip utama yang digunakan adalah:

- Cepat untuk Kasir.
- Detail untuk Owner.
- Offline tanpa rasa khawatir.
- Mudah dipelajari.
- Mudah dikembangkan.

---

## 4. Filosofi Pengembangan

Blueprint ini mengikuti pendekatan **Business Driven Development**.

Artinya, setiap keputusan teknis harus mendukung proses bisnis, bukan sebaliknya.

Beberapa prinsip yang digunakan selama pengembangan adalah:

### 4.1 Offline First

Seluruh operasional kasir harus tetap berjalan ketika internet terputus.

Internet diperlakukan sebagai media sinkronisasi, bukan sebagai syarat utama agar aplikasi dapat digunakan.

---

### 4.2 Local First

Seluruh transaksi kasir akan disimpan terlebih dahulu pada penyimpanan lokal (IndexedDB).

Server hanya berfungsi sebagai pusat sinkronisasi dan konsolidasi data.

---

### 4.3 Simplicity

Apabila terdapat dua solusi dengan hasil yang sama, maka solusi yang lebih sederhana harus dipilih.

Kompleksitas hanya boleh ditambahkan apabila benar-benar memberikan manfaat operasional.

---

### 4.4 Business Driven

Seluruh fitur harus memiliki alasan bisnis yang jelas.

Fitur yang tidak memberikan manfaat nyata terhadap operasional tidak akan dimasukkan ke dalam sistem.

---

### 4.5 Auditability

Seluruh aktivitas penting harus dapat ditelusuri kembali.

Contohnya:

- perubahan harga,
- void transaksi,
- pengeluaran,
- perubahan stok,
- login pengguna,
- perubahan konfigurasi.

Tujuannya adalah menjaga transparansi operasional dan mempermudah proses audit apabila terjadi kesalahan.


---

## 5. Sasaran Bisnis

D'CrunchyWan POS v3 dikembangkan untuk meningkatkan efisiensi operasional toko tanpa menambah beban kerja kasir.

Sasaran bisnis utama meliputi:

### Operasional

- Mengurangi waktu transaksi.
- Mengurangi kesalahan input kasir.
- Mempermudah proses penutupan toko.
- Mempermudah rekonsiliasi QRIS.

### Owner

- Memiliki laporan yang akurat.
- Mengetahui kondisi usaha secara realtime.
- Mempermudah pengambilan keputusan.
- Mengurangi pekerjaan administrasi manual.

### Pengembangan

- Sistem mudah dipelihara.
- Mudah ditambah fitur baru.
- Tidak perlu mengubah fondasi database ketika bisnis berkembang.

---

## 6. Sasaran Teknis

Blueprint ini menetapkan beberapa target teknis yang harus dipenuhi oleh implementasi.

### Offline First

- Kasir tetap dapat melakukan transaksi ketika internet terputus.
- Browser dapat direfresh tanpa kehilangan transaksi yang belum tersinkronisasi.
- Sinkronisasi dilakukan otomatis ketika koneksi kembali tersedia.

### Performance

Target minimum:

- Waktu membuka aplikasi ≤ 2 detik.
- Pencarian produk ≤ 100 ms.
- Checkout ≤ 1 detik.
- Perpindahan halaman terasa instan.

### Reliability

- Tidak ada kehilangan data transaksi.
- Tidak ada duplikasi transaksi.
- Semua aktivitas penting tercatat pada Audit Log.

### Maintainability

- Setiap modul berdiri sendiri.
- Business Rule tidak boleh diduplikasi.
- Dokumentasi menjadi acuan utama implementasi.

---

## 5. Ruang Lingkup MVP (Minimum Viable Product)

Versi pertama D'CrunchyWan POS v3 difokuskan untuk memenuhi seluruh kebutuhan operasional toko saat ini tanpa menambahkan kompleksitas yang belum dibutuhkan.

Fitur yang termasuk dalam MVP adalah:

### Operasional Kasir

- Login menggunakan PIN.
- Pencarian produk.
- Kategori produk.
- Keranjang belanja.
- Checkout.
- Quick Cash.
- Popup Keypad.
- Digital Receipt.

### Metode Pembayaran

- Tunai.
- QRIS.
- Transfer.

### Dapur

- Input Ayam Supplier.
- Input Goreng Ayam.
- Input Ayam Waste.
- Input Minyak.

Dashboard dapur harus menampilkan kondisi stok operasional secara realtime.

### Keuangan

- Kas Awal.
- Pengeluaran.
- Tarik Tunai QRIS.
- Setor Owner.
- Mutasi Kas.

### Dashboard Owner

- Laporan Harian.
- Laporan Bulanan.
- Laporan Tahunan.
- Grafik Penjualan.
- Rekonsiliasi QRIS.
- Riwayat Pengeluaran.
- Riwayat Perubahan Harga.

### Master Data

- Produk.
- Kategori.
- Business Unit.
- Pengguna.
- Pengaturan.

---

## 6. Fitur di Luar MVP

Fitur berikut **tidak termasuk** dalam versi pertama sistem, namun arsitekturnya harus dipersiapkan agar dapat ditambahkan di masa mendatang tanpa perubahan besar.

Daftar fitur tersebut meliputi:

- Multi Outlet.
- Member / Loyalty.
- Voucher & Promo.
- Integrasi Printer Struk.
- Integrasi Marketplace.
- Integrasi Delivery Online.
- Integrasi Akuntansi.
- Multi Gudang.
- Purchase Order.
- Supplier Management.
- Recipe Management.
- Modifier Produk yang kompleks.

Keputusan untuk menunda fitur-fitur tersebut bertujuan menjaga aplikasi tetap sederhana, cepat, dan mudah digunakan pada tahap awal implementasi.

---

## 7. Kriteria Keberhasilan (Success Criteria)

Blueprint dan implementasi dianggap berhasil apabila memenuhi kriteria berikut.

### Operasional

- Kasir dapat menyelesaikan transaksi dengan cepat dan konsisten.
- Tidak ada transaksi yang hilang meskipun koneksi internet terputus.
- Browser dapat direfresh tanpa kehilangan transaksi yang belum tersinkronisasi.
- Kesalahan input kasir dapat diminimalkan.

### Owner

- Dashboard menampilkan data yang akurat.
- Rekonsiliasi QRIS sesuai dengan mutasi rekening.
- Riwayat perubahan harga dapat ditelusuri.
- Seluruh aktivitas penting tercatat pada Audit Log.

### Teknis

- Sistem mudah dikembangkan.
- Struktur database tetap konsisten.
- Business Rule tidak diduplikasi.
- Dokumentasi selalu diperbarui sebelum implementasi fitur baru.

---

## 8. Stakeholder

Pihak yang terlibat dalam pengembangan maupun penggunaan sistem.

### Owner

Bertanggung jawab terhadap pengambilan keputusan bisnis, konfigurasi sistem, laporan, serta persetujuan perubahan fitur.

### Kasir

Menggunakan aplikasi untuk melayani transaksi pelanggan, melakukan operasional dapur, serta mencatat aktivitas harian.

### Developer

Mengimplementasikan sistem sesuai Blueprint dan tidak mengubah Business Rule tanpa persetujuan.

### Artificial Intelligence (AI)

AI digunakan sebagai asisten pengembangan, dokumentasi, review kode, dan pembuatan implementasi berdasarkan Blueprint yang telah disetujui.

---

## 9. Batasan Proyek (Constraints)

Untuk menjaga ruang lingkup proyek tetap terkendali, beberapa batasan berikut ditetapkan.

- Prioritas utama adalah kebutuhan operasional toko saat ini.
- Sistem dirancang untuk satu outlet terlebih dahulu.
- Sistem mendukung satu shift operasional pada tahap awal.
- Seluruh transaksi menggunakan satu QRIS yang sama.
- Printer struk tidak termasuk dalam MVP.
- Membership belum diimplementasikan.
- Multi Outlet dipersiapkan pada level arsitektur, namun belum diaktifkan.

Perubahan terhadap batasan proyek hanya dapat dilakukan melalui proses RFC (Request For Change).