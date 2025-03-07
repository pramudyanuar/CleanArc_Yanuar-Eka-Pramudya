# WEEK 1 Task Arkavidia - SE Academya

## Perubahan dari MVC ke Clean Architecture
Proyek ini awalnya menggunakan **MVC (Model-View-Controller)**, kemudian direstrukturisasi menggunakan **Clean Architecture** untuk meningkatkan modularitas dan skalabilitas.

### Perubahan yang Dilakukan
1. **Penambahan Folder Baru**:
   - `domain/` → Menyimpan entitas atau model inti yang bebas dari dependensi eksternal.
   - `repository/` → Abstraksi akses data untuk memisahkan logika bisnis dari implementasi database.
   - `usecase/` → Berisi logika bisnis utama yang menghubungkan `domain` dan `repository`.

2. **Struktur Folder yang Berubah**:
   - Sebelumnya: **MVC**
     ```
     backend_architecture/
     ├── controllers/
     ├── database/
     ├── instance/
     ├── models/
     ├── routes/
     ├── venv/
     ├── .gitignore
     ├── app.py
     ├── requirements.txt
     ```
   - Sekarang: **Clean Architecture**
     ```
     backend_architecture_refactor/
     ├── controllers/
     ├── database/
     ├── domain/  # Baru
     ├── instance/
     ├── models/
     ├── repository/  # Baru
     ├── routes/
     ├── usecase/  # Baru
     ├── venv/
     ├── .gitignore
     ├── app.py
     ├── requirements.txt
     ```

3. **Pemisahan Tanggung Jawab**:
   - Sebelumnya, semua logika bisnis dan akses data langsung dikelola dalam `controllers` dan `models`.
   - Sekarang, logika bisnis dipisahkan ke dalam `usecase/`, sementara akses data dipindahkan ke `repository/`.

### Manfaat Refactor ke Clean Architecture
- **Lebih terstruktur & mudah dikelola**
- **Mudah diuji (unit testing lebih sederhana)**
- **Lebih fleksibel untuk perubahan teknologi di masa depan**

---
Jika ingin menjalankan proyek ini, pastikan untuk menginstal dependensi dengan:
```sh
pip install -r requirements.txt
```
Lalu jalankan aplikasi dengan:
```sh
python app.py
```
