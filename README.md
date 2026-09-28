# 💼 Business & System Analyst Portfolio

Portfolio ini menampilkan proyek-proyek *end-to-end* yang mencakup **Mobile Application Engineering (Flutter)**, **System Architecture & Specification (PRD, SRS, SDD, UML)**, hingga **Big Data Analytics (Google BigQuery SQL & Data Marts)**.

---

## 📋 Table of Contents
- [🏍️ Project 1: MotoGP Schedule — Android App](#-project-1-motogp-schedule--android-app)
- [📍 Project 2: App Destinasi Wisata — Android App](#-project-2-app-destinasi-wisata--android-app)
- [💊 Project 3: Kimia Farma Sales & Business Performance Analysis](#-project-3-kimia-farma-sales--business-performance-analysis-20202023)

---

## 🏍️ Project 1: MotoGP Schedule — Android App

[![Repository](https://img.shields.io/badge/GitHub-moto__gp__schedule-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/RahmatAbdianto02/moto_gp_schedule)
[![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?style=for-the-badge&logo=dart&logoColor=white)](https://dart.dev)
[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://developer.android.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

Aplikasi agregator jadwal balap MotoGP dengan fitur **notifikasi pengingat sesi (exact alarm)**, penyesuaian **zona waktu otomatis (WIB/WITA/WIT)**, dan **dukungan offline (offline-first architecture)**.

Dibuat dari nol sebagai proyek portofolio Android/Flutter pribadi — mencakup perencanaan proyek (*PRD, SRS, SDD*), perancangan arsitektur terstruktur (**MVVM + Repository Pattern**), hingga implementasi penuh.

---

### 💡 Latar Belakang & Solusi

**Masalah:**  
Penggemar MotoGP di Indonesia sering **ketinggalan sesi latihan, kualifikasi, atau balapan** karena:
1. Perbedaan zona waktu negara penyelenggara balapan yang membingungkan.
2. Tidak ada notifikasi otomatis yang fleksibel tanpa harus membuka aplikasi resmi atau mengecek browser secara manual.

**Solusi:**  
MotoGP Schedule menyediakan satu tempat ringkas untuk memantau seluruh jadwal GP musim berjalan secara otomatis disesuaikan ke waktu lokal (WIB/WITA/WIT), lengkap dengan notifikasi pengingat fleksibel per sesi yang tetap bekerja tanpa koneksi internet.

---

### ✨ Fitur Utama (MVP)

- 📅 **Jadwal Musim Berjalan:** Daftar lengkap seluruh Grand Prix (GP) musim berjalan.
- 🕒 **Dukungan Zona Waktu Indonesia:** Pengguna dapat berpindah antara **WIB**, **WITA**, dan **WIT** secara instan di seluruh aplikasi.
- 🔔 **Pengingat Sesi Tingkat Lanjut (Exact Alarm):** Pasang *multiple reminder* (10, 15, 30, 60, atau 120 menit sebelum sesi dimulai).
- ⚡ **Offline-First (Caching 24 Jam):** Data tersimpan otomatis di SQLite lokal sehingga aplikasi tetap dapat diakses tanpa koneksi internet.
- 🚦 **Status Sesi Otomatis:** Deteksi status sesi secara *real-time* (*Upcoming*, *Berlangsung*, atau *Selesai*).

---

### 🏗️ Arsitektur & Desain Sistem

Aplikasi ini menerapkan **MVVM (Model-View-ViewModel)** dipadukan dengan **Repository Pattern** untuk memisahkan logika bisnis, data, dan tampilan UI secara bersih (*Separation of Concerns*).

```text
┌─────────────────────────────────────────────────────────────┐
│                     PRESENTATION LAYER                      │
│  [Screens / UI]           [Providers / State Management]    │
│  - HomeScreen              - ScheduleProvider               │
│  - ScheduleScreen          - ReminderProvider               │
│  - DetailScreen                                             │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│                        DOMAIN LAYER                         │
│  [Repository Pattern]                                       │
│  - MotoGpRepository (Konversi Timezone & Business Logic)    │
└──────────────────────────────┬──────────────────────────────┘
                               │
        ┌──────────────────────┴──────────────────────┐
        ▼                                             ▼
┌──────────────────────────────┐    ┌──────────────────────────────┐
│    DATA LAYER (REMOTE)       │    │     DATA LAYER (LOCAL)       │
│  - MotoGpRemoteDataSource    │    │  - MotoGpLocalDataSource     │
│  - REST API (HTTP & JSON)    │    │  - SQLite (sqflite)          │
└──────────────────────────────┘    └──────────────────────────────┘
```

---

## 📍 Project 2: App Destinasi Wisata — Android App

[![Repository](https://img.shields.io/badge/GitHub-prototype__app__destinasi-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/RahmatAbdianto02/prototype_app_destinasi)
[![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?style=for-the-badge&logo=dart&logoColor=white)](https://dart.dev)
[![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)

---

### 📌 Overview

Aplikasi mobile berbasis Android yang berfungsi sebagai platform agregator & direktori destinasi wisata. Aplikasi ini dirancang untuk membantu pengguna mengeksplorasi berbagai objek wisata secara terstruktur, cepat, dan interaktif dalam satu genggaman.

---

### 🔍 Problem & Objective

#### Problem Statement
Penggemar *travel* atau wisatawan lokal sering menghadapi kendala berikut:
- **Informasi Tersebar:** Kesulitan menemukan informasi destinasi wisata yang lengkap di satu tempat.
- **Data Tidak Terstruktur:** Detail mengenai jam buka, harga tiket masuk, dan fasilitas sering kali simpang siur atau tidak diperbarui.
- **Proses Pencarian Rumit:** Membutuhkan waktu lama untuk membandingkan opsi destinasi wisata beserta lokasinya.

#### Objective
- Menyediakan direktori informasi destinasi wisata yang lengkap dan terstruktur.
- Memudahkan proses eksplorasi lokasi, fasilitas, estimasi biaya/harga tiket, dan rating tempat wisata.
- Menyajikan antarmuka pengguna (UI) yang responsif, modern, dan intuitif.

---

### 📋 Requirements

#### Functional Requirements
- Pengguna dapat melihat daftar destinasi wisata (kategori, rating, lokasi).
- Pengguna dapat melihat detail lengkap destinasi wisata.
- Pengguna dapat mengeksplorasi galeri foto tempat wisata.
- Pengguna dapat melihat rincian fasilitas tempat wisata.
- Pengguna dapat mengecek informasi harga tiket masuk & lokasi.

#### Non-Functional Requirements
- **Usability:** Antarmuka yang simpel, elegan, dan mudah digunakan oleh awam.
- **Performance:** Data dan gambar dimuat secara dinamis dan responsif.
- **Compatibility:** Berjalan dengan lancar pada sistem operasi Android.

---

### 📐 System Diagrams & Design

| Artefak Diagram | Deskripsi |
| :--- | :--- |
| **Use Case Diagram** | Menjelaskan aktor (pengguna) dan interaksi utama terhadap fitur-fitur sistem. |
| **Activity Diagram** | Menjelaskan alur aktivitas pengguna saat menavigasi aplikasi dari halaman utama hingga ke detail destinasi. |
| **Entity Relationship Diagram (ERD)** | Menjelaskan struktur database dan hubungan antar-entitas data wisata. |
| **Flowchart** | Menjelaskan logika proses utama aplikasi secara menyeluruh. |
| **User Flow** | Menjelaskan perjalanan dan langkah-langkah navigasi pengguna dalam aplikasi. |

#### Visualisasi Diagram
- **Use Case Diagram:**  
  ![Use Case Diagram](docs/use-case.png)
- **Activity Diagram:**  
  ![Activity Diagram](docs/activity-diagram.png)
- **Entity Relationship Diagram (ERD):**  
  ![ERD](docs/erd.png)
- **Flowchart:**  
  ![Flowchart](docs/flowchart.png)
- **User Flow:**  
  ![User Flow](docs/user-flow.png)

---

### 🎨 Wireframe & Prototyping

Wireframe dan antarmuka UI/UX dirancang terlebih dahulu menggunakan Figma untuk memastikan tata letak dan navigasi aplikasi konsisten sebelum tahap implementasi.

![Wireframe](docs/wireframe.png)

---

### 🚀 Implementation & Features

Aplikasi dibangun menggunakan **Flutter** dan **Firebase** sebagai backend/database.

- 🚀 **Splash Screen:** Tampilan awal aplikasi saat pertama dimuat.
- 📜 **Daftar Destinasi:** List tempat wisata dinamis dengan kartu informasi ringkas.
- 🔍 **Detail Destinasi:** Informasi rinci mengenai tempat wisata terpilih.
- 🎟️ **Informasi Tiket & Fasilitas:** Estimasi biaya tiket masuk dan daftar fasilitas yang tersedia.
- 🖼️ **Galeri Foto:** Tampilan koleksi foto berkualitas dari lokasi wisata.
- 📍 **Informasi Lokasi:** Detail petunjuk lokasi dan alamat tempat wisata.
- ☁️ **Integrasi Database:** Fetch data dinamis melalui Firebase backend.

---

### 🛠️ Tools & Technologies

| Tools / Tech | Penggunaan |
| :--- | :--- |
| **Flutter** | Framework UI Lintas Platform |
| **Dart** | Bahasa Pemrograman Utama |
| **Firebase** | Cloud Database / Backend Services |
| **Figma** | UI/UX Prototyping & Wireframing |
| **Git & GitHub** | Version Control & Collaboration |
| **VS Code** | Integrated Development Environment (IDE) |

---

### 🔗 Links & Resources

- **GitHub Repository:** [https://github.com/RahmatAbdianto02/prototype_app_destinasi](https://github.com/RahmatAbdianto02/prototype_app_destinasi)

---

### 📄 Lisensi

Proyek ini dirilis di bawah lisensi **MIT License**.

---

## 💊 Project 3: Kimia Farma Sales & Business Performance Analysis (2020–2023)

> **Program:** Project-Based Virtual Internship Program — Big Data Analytics  
> **Author:** Rahmat Abdianto Bolota  
> **Final Score:** 88.72 / 100 (Excellent)  
> **Repository:** [GitHub Project Link](https://github.com/RahmatAbdianto02/Project-Based-Internship-PBI-Big-Data-Analytics-Kimia-Farma-x-Rakamin-Academy)

---

### 📌 1. Overview

Proyek ini merupakan bagian dari **Project-Based Virtual Internship Program (Kimia Farma x Rakamin Academy)**. Tujuan utama dari proyek ini adalah melakukan analisis komprehensif terhadap data kinerja penjualan dan profitabilitas **PT Kimia Farma Tbk** selama periode 2020 hingga 2023. 

Dengan memproses lebih dari **670.000+ baris data transaksi**, proyek ini menghasilkan *interactive executive dashboard* serta rekomendasi bisnis strategis berbasis data untuk mendukung pengambilan keputusan manajemen.

---

### 🏬 2. Business Problem

Sebagai salah satu perusahaan farmasi terbesar di Indonesia, PT Kimia Farma Tbk memerlukan evaluasi mendalam terhadap performa rantai cabang dan produknya. Tantangan bisnis utama yang dianalisis meliputi:
- Kesulitan dalam memantau tren pendapatan bersih (*Nett Sales*) dan margin keuntungan secara *real-time* di seluruh wilayah Indonesia.
- Perlu adanya evaluasi kinerja cabang untuk mengidentifikasi cabang mana yang memiliki performa tinggi vs. cabang yang memerlukan perbaikan operasional.
- Perlunya pemetaan wilayah geografis untuk mengidentifikasi potensi ekspansi pasar baru di luar Pulau Jawa.

---

### 📊 3. Dataset Structure

Dataset yang digunakan mencakup data transaksi historis PT Kimia Farma Tbk dari tahun **2020 hingga 2023** dengan total **670.000+ baris data**.

Struktur data terdiri dari beberapa tabel relasional utama:
- **`kf_final_transaction`**: Data transaksi detail (ID transaksi, tanggal, cabang, harga, diskon, rating, dll).
- **`kf_kantor_cabang`**: Master data cabang (ID cabang, nama cabang, kota, provinsi, rating cabang).
- **`kf_product`**: Master data produk obat/farmasi (ID produk, nama produk, harga).
- **`kf_inventory`**: Data stok dan persediaan barang per cabang.

---

### ❓ 4. Business Questions

Untuk menyelesaikan masalah bisnis di atas, analisis ini menjawab beberapa pertanyaan kunci:
1. Bagaimana tren pertumbuhan *Nett Sales* dan *Nett Profit* PT Kimia Farma Tbk dari tahun 2020 hingga 2023?
2. Provinsi dan cabang mana yang memberikan kontribusi pendapatan dan keuntungan terbesar?
3. Apakah terdapat korelasi antara *Rating Cabang* dengan total penjualan yang dihasilkan?
4. Bagaimana distribusi keuntungan berdasarkan skema *Gross Profit Margin Tiering* pada tiap kategori harga produk?

---

### 💻 5. Data Analysis / SQL Logic

Pengolahan *Big Data* dilakukan menggunakan **Google BigQuery SQL** untuk menggabungkan (*JOIN*), membersihkan, dan menghitung variabel finansial secara otomatis.

#### Logika Bisnis & Kalkulasi Utama:
- **Nett Sales:** `Harga Barang * (1 - Diskon)`
- **Nett Profit Margin Tiering:**
  - Harga $\le$ Rp 50.000 → Margin 10%
  - Harga > Rp 50.000 s/d Rp 100.000 → Margin 15%
  - Harga > Rp 100.000 s/d Rp 300.000 → Margin 20%
  - Harga > Rp 300.000 s/d Rp 500.000 → Margin 25%
  - Harga > Rp 500.000 → Margin 30%
- **Nett Profit:** `Nett Sales * Persentase Profit Margin`

```sql
-- Query SQL Datamart di Google BigQuery
CREATE OR REPLACE TABLE `kimia_farma.datamart_sales_performance` AS
SELECT 
    ft.transaction_id,
    ft.date,
    kc.branch_id,
    kc.branch_name,
    kc.provinsi,
    kc.rating AS rating_cabang,
    p.product_name,
    ft.price AS harga_barang,
    ft.discount_percentage,
    
    -- Hitung Nett Sales
    (ft.price * (1 - ft.discount_percentage)) AS nett_sales,
    
    -- Menentukan Profit Margin (%)
    CASE 
        WHEN ft.price <= 50000 THEN 0.10
        WHEN ft.price > 50000 AND ft.price <= 100000 THEN 0.15
        WHEN ft.price > 100000 AND ft.price <= 300000 THEN 0.20
        WHEN ft.price > 300000 AND ft.price <= 500000 THEN 0.25
        ELSE 0.30
    END AS persentase_gross_profit,
    
    -- Hitung Nett Profit
    ((ft.price * (1 - ft.discount_percentage)) * 
    CASE 
        WHEN ft.price <= 50000 THEN 0.10
        WHEN ft.price > 50000 AND ft.price <= 100000 THEN 0.15
        WHEN ft.price > 100000 AND ft.price <= 300000 THEN 0.20
        WHEN ft.price > 300000 AND ft.price <= 500000 THEN 0.25
        ELSE 0.30
    END) AS nett_profit

FROM `kimia_farma.kf_final_transaction` ft
LEFT JOIN `kimia_farma.kf_kantor_cabang` kc ON ft.branch_id = kc.branch_id
LEFT JOIN `kimia_farma.kf_product` p ON ft.product_id = p.product_id;
```
