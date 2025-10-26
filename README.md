# PalmVision AI - Solusi Identifikasi Hama & Gulma Kelapa Sawit

PalmVision AI adalah aplikasi berbasis web yang menggunakan kecerdasan buatan (AI) untuk mengidentifikasi hama dan gulma pada perkebunan kelapa sawit. Aplikasi ini dirancang khusus untuk membantu petani dalam mendeteksi dan mengatasi masalah hama/gulma secara cepat dan akurat.

## 📋 Daftar Isi

- [Fitur Utama](#fitur-utama)
- [Persyaratan Sistem](#persyaratan-sistem)
- [Instalasi](#instalasi)
- [Konfigurasi](#konfigurasi)
- [Penggunaan](#penggunaan)
- [Struktur Project](#struktur-project)
- [Teknologi yang Digunakan](#teknologi-yang-digunakan)
- [Dukungan](#dukungan)
- [Kontribusi](#kontribusi)
- [Lisensi](#lisensi)

## ✨ Fitur Utama

- **🔍 Identifikasi AI**: Sistem AI canggih untuk identifikasi hama dan gulma dengan akurasi tinggi
- **📱 Responsif**: Desain yang optimal untuk semua perangkat (desktop, tablet, smartphone)
- **⚡ Real-time**: Hasil identifikasi langsung dalam hitungan detik
- **🌱 Ramah Lingkungan**: Membantu petani mengurangi penggunaan pestisida berlebihan
- **💡 Rekomendasi**: Memberikan saran penanganan dan pencegahan yang tepat
- **🎯 User-Friendly**: Interface yang sederhana dan mudah digunakan untuk petani
- **📊 Informasi Lengkap**: Menampilkan nama ilmiah, deskripsi, dan tingkat kepercayaan

## 🔧 Persyaratan Sistem

### Server/Backend Requirements
- Node.js v14.0 atau lebih tinggi
- Webhook server (N8N, Zapier, atau custom)
- API endpoint untuk AI processing

### Browser Requirements
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

### Mobile Requirements
- iOS 12+
- Android 8.0+

## 📥 Instalasi

### 1. Clone Repository

```bash
git clone https://github.com/your-username/palmvision-ai.git
cd palmvision-ai
```

### 2. Setup Webhook/Backend

PalmVision AI menggunakan webhook endpoint untuk pemrosesan AI. Anda perlu mengkonfigurasi webhook server:

#### Menggunakan N8N (Recommended)

1. Install N8N:
```bash
npm install -g n8n
```

2. Jalankan N8N:
```bash
n8n start
```

3. Import workflow dari file `PalmVision-Ai (1).json`
4. Konfigurasi webhook URL sesuai dokumentasi N8N

#### Menggunakan Backend Custom

Jika Anda menggunakan backend custom:

1. Setup API endpoint untuk processing
2. Update URL webhook di konfigurasi (lihat bagian Konfigurasi)

### 3. Setup Assets

Pastikan semua file di folder `assets/` tersedia:
- `Logo.png` - Logo aplikasi
- `Banner.png` - Banner utama
- `Adan.jpeg` - Foto developer
- `Rizal.jpeg` - Foto developer

## ⚙️ Konfigurasi

### 1. Webhook Configuration

Buka file `index.html` dan cari bagian script JavaScript, update URL webhook:

```javascript
const payload = {
  image: base64Image,
  analysis_type: "pest_detection",
  user_id: "demo_user",
  farm_id: "demo_farm",
  webhookUrl: "http://localhost:5678/webhook-test/PalmVision-Ai"  // Update URL ini
};
```

**Untuk Production:**
- Ganti `localhost:5678` dengan domain/production URL Anda
- Pastikan menggunakan HTTPS untuk keamanan

### 2. Font Awesome CDN

Font Awesome sudah dikonfigurasi via CDN, tidak perlu instalasi tambahan:
```html
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
```

### 3. Google Fonts

Aplikasi menggunakan Google Fonts (Inter & Poppins):
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
```

### 4. Logo dan Branding

Untuk mengganti logo:
1. Ganti file `assets/Logo.png` dengan logo Anda
2. Sesuaikan ukuran jika diperlukan (default: 34x34px untuk header)

## 🚀 Penggunaan

### 1. Membuka Aplikasi

Buka file `index.html` di browser modern, atau:
- Served via HTTP server (recommended)
- Buka langsung dari file system (limited functionality)

### 2. Identifikasi Hama/Gulma

1. **Siapkan Gambar**:
   - Ambil foto hama atau gulma
   - Pastikan pencahayaan cukup
   - Objek harus fokus dan jelas

2. **Unggah Gambar**:
   - Klik area "Drag & drop gambar di sini"
   - Atau klik tombol "Pilih Gambar"
   - Format yang didukung: JPG, PNG, GIF (Maks 10MB)

3. **Analisis**:
   - Klik tombol "Analisis Gambar"
   - Tunggu proses identifikasi (beberapa detik)

4. **Lihat Hasil**:
   - Nama ilmiah dan umum
   - Tingkat kepercayaan (accuracy)
   - Deskripsi lengkap
   - Rekomendasi penanganan
   - Tips pencegahan

### 3. Tips Penggunaan

**Untuk Hasil Terbaik:**
- ✅ Gunakan pencahayaan alami yang cukup
- ✅ Pastikan gambar fokus dan tidak blur
- ✅ ✅ Objek memenuhi 30% frame
- ✅ Latar belakang kontras dengan objek
- ✅ Ambil dari beberapa sudut
- ✅ Gunakan resolusi tinggi (minimal 1080p)

## 📁 Struktur Project

```
palmvision-ai/
│
├── assets/                      # Folder gambar dan media
│   ├── Logo.png                 # Logo aplikasi
│   ├── Banner.png               # Banner hero section
│   ├── Adan.jpeg                # Foto developer
│   └── Rizal.jpeg               # Foto developer
│
├── index.html                   # Halaman utama
├── usage.html                   # Halaman cara penggunaan
├── developer.html               # Halaman tentang developer
├── PalmVision-Ai (1).json       # Workflow N8N untuk AI processing
└── README.md                    # Dokumentasi ini
```

### Penjelasan File

- **index.html**: Halaman utama dengan fitur upload dan identifikasi hama/gulma
- **usage.html**: Panduan lengkap cara menggunakan aplikasi beserta tips
- **developer.html**: Halaman tentang tim developer dan teknologi yang digunakan
- **assets/**: Folder berisi logo, banner, dan foto developer
- **PalmVision-Ai (1).json**: Workflow N8N untuk integrasi dengan AI backend

## 🛠️ Teknologi yang Digunakan

### Frontend
- **HTML5**: Struktur dasar website
- **CSS3**: Styling dan animasi modern
- **JavaScript (Vanilla)**: Interaktivitas dan logika aplikasi
- **Font Awesome 6.0**: Ikon yang digunakan
- **Google Fonts**: Tipografi (Inter & Poppins)

### Backend/AI Integration
- **N8N**: Workflow automation dan webhook handling
- **AI/ML**: Machine Learning untuk identifikasi hama/gulma
- **RESTful API**: Komunikasi antara frontend dan backend

### Design Features
- **Responsive Design**: Mobile-first approach
- **Gradient Backgrounds**: Modern visual effects
- **Smooth Animations**: User experience enhancement
- **Shimmer Effects**: Interactive visual feedback

## 📞 Dukungan

### Kontak
- **Email**: info@palmvision.ai
- **Telepon**: +62 81343145435
- **Support**: 24/7

### Social Media
- Twitter: [@PalmVision](https://twitter.com)
- GitHub: [github.com/palmvision](https://github.com)

### Bantuan
Jika mengalami masalah atau memiliki pertanyaan:
1. Cek bagian FAQ di halaman Cara Penggunaan
2. Hubungi tim support melalui kontak di atas
3. Buat issue di repository GitHub

## 🤝 Kontribusi

Kami sangat terbuka untuk kontribusi! Jika Anda ingin berkontribusi:

1. Fork repository ini
2. Buat branch baru untuk fitur (`git checkout -b feature/AmazingFeature`)
3. Commit perubahan Anda (`git commit -m 'Add some AmazingFeature'`)
4. Push ke branch (`git push origin feature/AmazingFeature`)
5. Buat Pull Request

### Guidelines
- Ikuti style guide yang ada
- Test perubahan Anda dengan baik
- Update dokumentasi jika diperlukan
- Buat commit messages yang jelas

## 👥 Tim Developer

**Frontend Developer:**
- **Adan Sobirin** - HTML, CSS, JavaScript, Responsive Design

**Backend Developer:**
- **Muhamad Rizal Wihel** - Python, Node.js, API Development, AI Integration

## 📝 Lisensi

© 2025 PalmVision. Semua hak dilindungi.

Aplikasi ini dibuat dengan tujuan membantu petani Indonesia dalam identifikasi dan penanganan hama/gulma pada perkebunan kelapa sawit.

## 🔒 Kebijakan Privasi

- Data gambar yang diunggah akan diproses secara aman
- Data tidak disimpan permanen di server
- Informasi pengguna dijaga kerahasiaannya

## 📖 Versi

**Current Version:** 1.0.0

**Release Date:** 2025

## 🎯 Roadmap

- [ ] Tambah lebih banyak jenis hama/gulma
- [ ] Peningkatan akurasi AI
- [ ] Fitur offline mode
- [ ] Aplikasi mobile (iOS & Android)
- [ ] Dashboard analytics untuk petani
- [ ] Integrasi dengan sistem manajemen perkebunan

## 🌟 Tips untuk Petani

1. **Ambil Foto yang Jelas**: Pastikan objek fokus dan pencahayaan baik
2. **Beberapa Sudut**: Ambil foto dari berbagai sudut untuk hasil lebih akurat
3. **Ukuran yang Ideal**: Jangan terlalu kecil atau terlalu besar
4. **Waktu yang Tepat**: Gunakan aplikasi di pagi atau sore hari
5. **Ikuti Rekomendasi**: Gunakan saran penanganan yang diberikan

## 📚 Referensi

- Dokumentasi API: [Link Dokumentasi]
- Tutorial Video: [Link Video Tutorial]
- User Guide: Lihat halaman Cara Penggunaan

---

**Made with ❤️ for Indonesian Farmers**

**PalmVision AI** - Teknologi Cerdas untuk Masa Depan Pertanian Indonesia

