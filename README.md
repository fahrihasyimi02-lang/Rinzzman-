# Remote Admin Dashboard — revisi 1.1

Proyek Android Java bertema dark hitam-hijau untuk dashboard administrasi yang transparan.

## Yang diperbaiki
- Ditambahkan GitHub Actions workflow untuk membangun APK di cloud tanpa Android Studio di PC.
- Target SDK ditetapkan ke 34 agar perilaku tampilan edge-to-edge tetap lebih konsisten pada perangkat Android baru.
- Pemeriksaan status jaringan memakai `NetworkCapabilities` (bukan API `NetworkInfo` yang deprecated).
- Status baterai yang tidak tersedia ditampilkan sebagai `N/A`.
- Menghapus variabel UI yang tidak digunakan dan memperjelas status sesi.
- Tidak menambahkan izin internet, aksesibilitas, mikrofon, kamera, SMS, kontak, atau lokasi.

## Fitur
- Ringkasan model perangkat dan versi Android.
- Persentase baterai, ruang penyimpanan bebas, status jaringan.
- Persetujuan eksplisit sebelum sesi demo lokal.
- Tombol untuk mengakhiri sesi.
- Log aktivitas lokal.

## Build APK hanya dengan HP (via GitHub Actions)
1. Unduh ZIP ini lalu ekstrak di HP.
2. Buat repositori baru di GitHub melalui browser, misalnya `remote-admin-dashboard`.
3. Unggah seluruh isi folder proyek ke repositori (pastikan `settings.gradle`, `build.gradle`, folder `app`, dan `.github` ada di root repositori, bukan di subfolder tambahan).
4. Buka tab **Actions** pada repositori. Jika diminta, aktifkan GitHub Actions.
5. Pilih workflow **Build Android APK**, tekan **Run workflow** (atau tunggu workflow berjalan setelah push).
6. Setelah workflow selesai dengan status hijau, buka hasil run dan bagian **Artifacts**, lalu unduh `remote-admin-dashboard-debug-apk`.
7. Ekstrak file artifact ZIP untuk mendapatkan `app-debug.apk`. Buka APK di HP untuk memasang; Android mungkin meminta izin “Install unknown apps” untuk aplikasi browser/file manager yang digunakan.

## Build lokal
Memerlukan JDK 17 dan Android SDK Platform 35, lalu jalankan `gradle assembleDebug` dengan Gradle 8.9 atau buka proyek di Android Studio.

## Batasan penting
Ini masih dashboard demo lokal, bukan produk remote-control yang terhubung ke server. Tidak mengirim data dan tidak menjalankan perintah pada perangkat lain. Kompilasi APK belum bisa dijalankan di lingkungan pembuatan ZIP ini karena Android SDK/Gradle tidak tersedia; gunakan workflow cloud di atas untuk menghasilkan APK dan melihat hasil kompilasi yang sebenarnya.
