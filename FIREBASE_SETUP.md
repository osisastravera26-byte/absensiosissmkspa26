# Setup Firebase untuk Absensi OSIS

## Masalah yang Diperbaiki
Aplikasi sebelumnya menggunakan localStorage yang hanya menyimpan data di browser lokal. Ketika link dibagikan ke perangkat berbeda, data tidak tersedia.

## Solusi: Firebase Firestore
Kami mengubah penyimpanan ke Firebase Firestore yang menyimpan data di cloud dan dapat diakses dari semua perangkat.

## Langkah Setup:

### 1. Buat Proyek Firebase
1. Buka [Firebase Console](https://console.firebase.google.com/)
2. Klik "Create a project" atau "Tambah proyek"
3. Masukkan nama proyek (contoh: "absensi-osis-singaparna")
4. Ikuti langkah-langkah setup

### 2. Aktifkan Firestore
1. Di menu sebelah kiri, klik "Firestore Database"
2. Klik "Create database"
3. Pilih "Start in test mode" (untuk development)
4. Pilih lokasi (contoh: asia-southeast1)

### 3. Dapatkan Konfigurasi Firebase
1. Klik ikon gear (settings) > "Project settings"
2. Scroll ke bawah ke bagian "Your apps"
3. Klik ikon web (</>) untuk menambah web app
4. Masukkan nama app (contoh: "Absensi OSIS Web")
5. Copy konfigurasi yang diberikan

### 4. Update Konfigurasi di Semua File HTML
Ganti bagian `firebaseConfig` di semua file HTML dengan konfigurasi Anda:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyD...g", // Ganti dengan API key Anda
  authDomain: "your-project-id.firebaseapp.com",
  projectId: "your-project-id",
  storageBucket: "your-project-id.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abcdef123456"
};
```

### File yang Perlu Diupdate:
- index.html
- admin-dashboard.html
- admin-members.html
- admin-edit-attendance.html
- admin-osis-structure.html
- admin-set-code.html
- admin-login.html
- profil-osis.html
- recap.html
- recap-detail.html

### 5. Test Aplikasi
1. Buka aplikasi di browser
2. Login sebagai admin
3. Tambahkan anggota atau data
4. Buka link di perangkat berbeda
5. Data sekarang harus tersedia di semua perangkat

## Keamanan
- Untuk production, ubah Firestore rules dari "test mode" ke rules yang lebih ketat
- Pertimbangkan menambahkan authentication jika diperlukan

## Troubleshooting
- Jika data tidak muncul, periksa console browser untuk error Firebase
- Pastikan konfigurasi Firebase sudah benar
- Periksa koneksi internet