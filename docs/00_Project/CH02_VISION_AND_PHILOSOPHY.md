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