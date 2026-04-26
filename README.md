# Backend API Aplikasi Manajemen Masjid
Sistem manajemen masjid terintegrasi yang dibangun menggunakan Clean Architecture dengan pendekatan Domain-Driven Design (DDD) untuk mengelola operasional, keuangan, hingga sinergi bantuan antar-masjid (inter-masjid aid) guna menghilangkan kebutuhan penggalangan dana di jalanan.

## 🕌 Domain & Bounded Contexts
Sistem ini dibagi menjadi beberapa domain mandiri (Vertical Slices):

> **🏃 SEDANG DIKERJAKAN (ACTIVE)**
>
> 1. Member (Anggota): Manajemen identitas Jamaah dan struktur Pengurus Masjid (DKM).
> 2. Finance (Keuangan): Manajemen Infaq, Kas Masjid, integrasi QRIS Syariah, dan Laporan Publik.

<br>

> **📅 RENCANA KE DEPAN (PLANNING)**
>
> 3. Synergy (Sinergi): Modul Core untuk distribusi bantuan antar-masjid (pembangunan/kegiatan) secara digital.
> 4. Social (Ziswaf): Statistik distribusi Zakat dan manajemen pendaftaran/pembagian Qurban.
> 5. Event (Agenda): Pengurusan jadwal Shalat Jumat, penugasan Imam/Khatib, dan acara keagamaan lainnya.
> 6. Asset (Inventaris): Pendataan aset dan inventaris milik masjid.


## 🏗️ Tech Stack
- **Language:** Go (Golang) 1.25+
- **Database:** PostgreSQL (GORM / SQLX)
- **Architecture:** Domain-Driven Design (Vertical Slicing)
- **API:** RESTful API (Gin)
- **Security:** JWT for Authentication & RBAC


## 📁 Project Structure
```
├── cmd/api/main.go            # Entry point & Dependency Injection
├── internal/
│   ├── member/                # Domain: Jamaah & Pengurus
│   │   ├── delivery/
│   │   │   └── http/          # HTTP Handler/Controller
│   │   ├── entity/            # Model
│   │   ├── repository/        # Implementasi Database
│   │   └── usecase/           # Aplication Logic
│   ├── finance/               # Domain: Infaq, Kas, QRIS
│   ├── synergy/               # Domain: Inter-masjid Aid (Core)
│   ├── social/                # Domain: Zakat & Qurban
│   ├── event/                 # Domain: Shalat & Agenda
│   ├── asset/                 # Domain: Inventaris
│   └── shared/                # Kernel: Utility (Prayer Times), Config, DB, Response
├── pkg/                       # Helper libraries (Logger, Validator)
└── migrations/                   # Database migrations & seeds
```

## 🛠️ Getting Started

### 1. Prasyarat
Pastikan Anda sudah menginstal perangkat lunak berikut:
- **Go** (versi 1.21 ke atas)
- **PostgreSQL**

### 2. Instalasi
Ikuti langkah-langkah berikut untuk menyiapkan proyek di lokal:

```bash
# Clone repository
git clone https://github.com/Yayasan-Digital-Islami-Indonesia/amm-api.git
cd amm-api

# Install dependencies
go mod tidy

# Setup environment
cp .env.example .env
```
> **Catatan:** Setelah menyalin `.env`, pastikan untuk menyesuaikan konfigurasi database Anda.

### 3. Menjalankan Aplikasi
Gunakan perintah berikut untuk menjalankan server:

```bash
go run cmd/api/main.go
```


