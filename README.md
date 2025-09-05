# Sistem-Kampus

## Deskripsi
Sistem-Kampus adalah smart contract berbasis **Sui Move** yang mengelola pendaftaran mahasiswa di sebuah kampus. Modul ini meliputi fitur seperti:

- Pembuatan capability untuk admin (`AdminCap`)
- Pembuatan registri kampus yang bersifat *shared* agar bisa diakses publik
- Fungsi `register_mahasiswa` untuk menambahkan mahasiswa baru secara aman dan terverifikasi
- Emit event pendaftaran mahasiswa (`MahasiswaRegistered`)

## Fitur Utama
| Fitur | Penjelasan |
|-------|------------|
| **Admin-only Access** | Fungsi-fungsi penting hanya dapat dijalankan oleh admin yang memegang `AdminCap`. |
| **Shared Registry** | `KampusRegistry` dibagikan sebagai shared object agar semua dapat akses data (misalnya jumlah mahasiswa, daftar NIM). |
| **Pendaftaran Mahasiswa** | Input data validasi NIM, buat `MahasiswaProfile`, update registri, emit event, dan transfer profile ke mahasiswa. |
| **Event-Driven** | Emit event untuk notifikasi real-time pada front-end atau indexer. |

## Struktur Project
- `AdminCap`: capability object untuk kontrol akses admin.
- `KampusRegistry`: object shared yang menyimpan data kampus.
- `MahasiswaProfile`: object yang dihasilkan saat mahasiswa baru terdaftar, kemudian ditransfer ke mahasiswa.
- `register_mahasiswa`: fungsi utama pendaftaran mahasiswa.

## Package Info
- **Package ID:**  
  `0xb6f5de2d33672a49b0de5d337fd8b9eb1093d57e17ee1a4dad50ce50ca8759c2`
- **Deployer Address:**  
  `0xd3f9393f25fd2d70df3b2aee0be7ebd9d275b088474186f1bf09cca524955297`

## Referensi
- Source: [Sui Move Basics – Mengenal Vector/Array](https://docs-sui.vercel.app/docs/day1/module2-move-basics#5-mengenal-vector-array)
