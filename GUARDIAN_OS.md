# GUARDIAN OS

Version : 1.0.0

---

## Purpose

Guardian OS adalah aturan utama yang wajib dipatuhi oleh seluruh AI, developer, maupun contributor yang bekerja pada proyek D'CrunchyWan POS v3.

Blueprint adalah sumber kebenaran utama (Single Source of Truth).

---

# Core Principles

## 1. Blueprint First

Seluruh implementasi harus mengikuti Blueprint.

Apabila terdapat perbedaan antara kode dan Blueprint, maka implementasi harus disesuaikan dengan Blueprint.

---

## 2. Business Rule First

Tidak boleh mengubah Business Rule tanpa persetujuan Owner.

---

## 3. Offline First

Seluruh fitur operasional kasir harus tetap dapat berjalan tanpa koneksi internet.

---

## 4. Immutable Transaction

Transaksi yang telah selesai tidak boleh diubah.

Perbaikan dilakukan melalui Void atau transaksi koreksi.

---

## 5. Decision Driven

Seluruh keputusan besar harus dicatat pada DECISION_INDEX.md.

Tidak boleh ada keputusan penting yang hanya berada di chat.

---

## 6. Documentation First

Blueprint diperbarui terlebih dahulu.

Baru implementasi dilakukan.

---

## 7. Keep It Simple

Apabila terdapat dua solusi dengan hasil yang sama, gunakan solusi yang lebih sederhana.

---

## 8. No Duplicate Business Logic

Business Rule hanya boleh ditulis pada satu tempat.

Tidak boleh diduplikasi.

---

## 9. Versioning

Seluruh perubahan Blueprint harus melalui Git.

Setiap perubahan penting harus memiliki commit yang jelas.

---

## 10. Continuous Improvement

Blueprint adalah dokumen hidup.

Namun perubahan hanya boleh dilakukan melalui review.