# Backend API Aplikasi Manajemen Masjid
Sistem manajemen masjid terintegrasi yang dibangun menggunakan Clean Architecture dengan pendekatan Domain-Driven Design (DDD) untuk mengelola operasional, keuangan, hingga sinergi bantuan antar-masjid (inter-masjid aid) guna menghilangkan kebutuhan penggalangan dana di jalanan.

## 🕌 Domain & Bounded Contexts
Sistem ini dibagi menjadi beberapa domain mandiri (Vertical Slices):

>**🏃SEDANG DIKERJAKAN (ACTIVE)**
1. Member (Anggota): Manajemen identitas Jamaah dan struktur Pengurus Masjid (DKM).
2. Finance (Keuangan): Manajemen Infaq, Kas Masjid, integrasi QRIS Syariah, dan Laporan Publik.
<br>
<br>
> **📅 RENCANA KE DEPAN (PLANNING)**
3. Synergy (Sinergi): Modul Core untuk distribusi bantuan antar-masjid (pembangunan/kegiatan) secara digital.
4. Social (Ziswaf): Statistik distribusi Zakat dan manajemen pendaftaran/pembagian Qurban.
5. Event (Agenda): Pengurusan jadwal Shalat Jumat, penugasan Imam/Khatib, dan acara keagamaan lainnya.
6. Asset (Inventaris): Pendataan aset dan inventaris milik masjid.

## 🏗️ Tech Stack
- **Language:** Go (Golang) 1.25+
- **Database:** PostgreSQL (GORM / SQLX)
- **Architecture:** Domain-Driven Design (Vertical Slicing)
- **API:** RESTful API (Gin)
- **Security:** JWT for Authentication & RBAC


📁 Project Structure
text

├── cmd/api/main.go            # Entry point & Dependency Injection
├── internal/
│   ├── member/                # Domain: Jamaah & Pengurus
│   ├── finance/               # Domain: Infaq, Kas, QRIS
│   ├── synergy/               # Domain: Inter-masjid Aid (Core)
│   ├── social/                # Domain: Zakat & Qurban
│   ├── event/                 # Domain: Shalat & Agenda
│   ├── asset/                 # Domain: Inventaris
│   └── shared/                # Kernel: Utility (Prayer Times), Config, DB, Response
├── pkg/                       # Helper libraries (Logger, Validator)
└── scripts/                   # Database migrations & seeds

Gunakan kode dengan hati-hati.
🛠️ Getting Started
1. Prasyarat

    Go 1.21 ke atas
    PostgreSQL
    Docker (opsional)

2. Instalasi
bash

# Clone repository
git clone https://github.com

# Install dependencies
go mod tidy

# Setup environment
cp .env.example .env

Gunakan kode dengan hati-hati.
3. Running
bash

go run cmd/api/main.go

Gunakan kode dengan hati-hati.
