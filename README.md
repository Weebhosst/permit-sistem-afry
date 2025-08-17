# Sistem Permit Kendaraan - Barcode + QR Code + Scanner + Database

## 🎯 **Overview**
Sistem manajemen permit kendaraan yang lengkap dengan fitur barcode 1D, QR Code 2D, scanner otomatis, dan database cloud. Dirancang untuk mengelola akses kendaraan dengan efisien dan aman.

## ✨ **Fitur Utama**

### 🔍 **Barcode & QR Code System**
- **Barcode 1D (CODE128)**: Generate dan scan barcode tradisional
- **QR Code 2D**: Generate, print, download, dan scan QR Code modern
- **Bulk Generation**: Generate multiple barcode/QR Code sekaligus
- **Hardware Scanner Support**: Kompatibel dengan USB/Bluetooth scanner
- **Camera Scanner**: Scan menggunakan kamera smartphone/komputer

### 📊 **Data Management**
- **Local Storage**: SQLite database di browser
- **Cloud Sync**: Supabase integration untuk sinkronisasi multi-perangkat
- **CSV Import/Export**: Import dari Google Sheets, export ke CSV
- **Real-time Updates**: Data tersinkron otomatis

### 🔐 **Security & Access Control**
- **Admin Protection**: Role-based access control
- **Authentication**: Login/logout system
- **Audit Trail**: Log semua aktivitas
- **Data Validation**: Validasi input dan output

### 📱 **Mobile & PWA Features**
- **Progressive Web App**: Install sebagai aplikasi mobile
- **Touch Interface**: Optimized untuk layar sentuh
- **Offline Mode**: Bekerja tanpa internet
- **Mobile Gestures**: Swipe navigation

### 🔊 **Audio & Visual Feedback**
- **Success Beeps**: Audio feedback saat scan berhasil
- **Visual Notifications**: Notifikasi real-time
- **Status Indicators**: Indikator status operasi

## 🚀 **Quick Start**

### 1. **Setup Database**
```bash
# Clone repository
git clone [repository-url]
cd permit-system

# Setup Supabase (Optional)
# 1. Buat project di supabase.com
# 2. Jalankan SQL script dari supabase-setup.sql
# 3. Copy URL dan ANON KEY ke aplikasi
```

### 2. **Run Application**
```bash
# Start local server
python -m http.server 8000

# Atau gunakan live server di VS Code
# Buka http://localhost:8000
```

### 3. **First Time Setup**
1. **Login sebagai Admin**: Masukkan kredensial Supabase
2. **Import Data**: Upload CSV atau tambah manual
3. **Generate Barcode/QR**: Buat barcode untuk permit
4. **Test Scanner**: Coba scan barcode/QR Code

## 📋 **Data Structure**

### Permit Fields
```json
{
  "permit_code": "PRM-2025-001",
  "plate": "B 1234 ABC",
  "owner": "John Doe",
  "type": "Mobil",
  "stnk_exp": "2025-06-30",
  "simc_exp": "2025-08-15",
  "sima_exp": "2025-10-20",
  "status": "active",
  "notes": "Karyawan tetap"
}
```

### Log Structure
```json
{
  "ts": "2025-01-15T10:30:00.000Z",
  "event": "SCAN",
  "permit_code": "PRM-2025-001",
  "plate": "B 1234 ABC"
}
```

## 🎨 **User Interface**

### Dashboard
- **Statistics**: Total permit, aktif, kadaluarsa, scan hari ini
- **Quick Actions**: Generate, scan, import/export
- **Status Overview**: Visual status semua permit

### Data Management
- **Table View**: Tampilan data dalam tabel
- **Search & Filter**: Cari dan filter data
- **Bulk Operations**: Operasi massal
- **Preview Cards**: Preview kartu permit

### Scanner Interface
- **Camera Selection**: Pilih kamera (prioritas belakang)
- **Hardware Scanner**: Input field untuk scanner fisik
- **Real-time Preview**: Preview hasil scan
- **Auto-log**: Otomatis catat log

### QR Code System
- **Individual Generation**: Generate QR Code per permit
- **Bulk Generation**: Generate multiple QR Code
- **Print & Download**: Export QR Code
- **Scanner**: Scan QR Code dengan kamera

## 🔧 **Technical Stack**

### Frontend
- **HTML5**: Semantic markup
- **CSS3**: Tailwind CSS framework
- **JavaScript**: Vanilla JS (ES6+)
- **PWA**: Service worker, manifest

### Libraries
- **JsBarcode**: Barcode generation
- **QRCode.js**: QR Code generation
- **ZXing**: Barcode/QR Code scanning
- **sql.js**: SQLite in browser
- **Supabase**: Cloud database

### Browser APIs
- **getUserMedia**: Camera access
- **Canvas API**: Image generation
- **File API**: File upload/download
- **Storage API**: Local storage

## 📱 **Mobile Features**

### PWA Capabilities
- **Installable**: Install sebagai aplikasi
- **Offline**: Bekerja tanpa internet
- **Push Notifications**: Notifikasi real-time
- **Background Sync**: Sync data di background

### Touch Optimization
- **Touch Targets**: Minimal 44px untuk touch
- **Swipe Gestures**: Navigasi dengan swipe
- **Responsive Design**: Adaptif ke semua ukuran layar
- **Mobile-first**: Optimized untuk mobile

## 🔐 **Security Features**

### Authentication
- **Supabase Auth**: Secure authentication
- **Role-based Access**: Admin vs user roles
- **Session Management**: Secure session handling
- **Password Protection**: Encrypted passwords

### Data Protection
- **Input Validation**: Sanitasi input
- **SQL Injection Prevention**: Parameterized queries
- **XSS Protection**: Output encoding
- **CSRF Protection**: Token-based protection

### Privacy
- **Local Storage**: Data tersimpan lokal
- **Cloud Encryption**: Data terenkripsi di cloud
- **Audit Logging**: Track semua aktivitas
- **Data Retention**: Policy data retention

## 🌐 **Deployment**

### Local Development
```bash
# Install dependencies (if any)
npm install

# Start development server
python -m http.server 8000

# Access at http://localhost:8000
```

### Production Deployment
```bash
# Build for production
# (No build step required - static files)

# Deploy to Netlify/Vercel/GitHub Pages
# Upload all files to hosting service

# Configure environment variables
# SUPABASE_URL, SUPABASE_KEY
```

### Environment Variables
```env
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_ANON_KEY=your-anon-key
```

## 📊 **Database Setup**

### Supabase Configuration
1. **Create Project**: Buat project di supabase.com
2. **Run SQL Script**: Jalankan `supabase-setup.sql`
3. **Configure RLS**: Set Row Level Security policies
4. **Get Credentials**: Copy URL dan ANON KEY

### Local Storage
- **SQLite**: Database lokal di browser
- **localStorage**: Fallback storage
- **IndexedDB**: Advanced local storage
- **Sync**: Otomatis sync dengan cloud

## 🔍 **Scanner Setup**

### Camera Scanner
1. **Permission**: Izinkan akses kamera
2. **Camera Selection**: Pilih kamera belakang
3. **Focus**: Pastikan fokus optimal
4. **Lighting**: Pencahayaan yang cukup

### Hardware Scanner
1. **Connect**: Hubungkan USB/Bluetooth scanner
2. **Driver**: Install driver jika diperlukan
3. **Test**: Test scanner dengan input field
4. **Configure**: Set scanner mode jika diperlukan

## 📈 **Analytics & Reporting**

### Usage Analytics
- **Scan Statistics**: Jumlah scan per hari/bulan
- **User Activity**: Aktivitas user
- **Error Tracking**: Track error dan issues
- **Performance Metrics**: Load time, response time

### Reports
- **Permit Status**: Status semua permit
- **Expiry Report**: Permit yang akan kadaluarsa
- **Access Log**: Log akses kendaraan
- **Export Data**: Export untuk analisis

## 🛠 **Troubleshooting**

### Common Issues

#### Scanner Tidak Berfungsi
1. **Check Permissions**: Pastikan izin kamera
2. **HTTPS Required**: Gunakan HTTPS untuk camera access
3. **Browser Support**: Pastikan browser support getUserMedia
4. **Hardware Issues**: Test dengan scanner lain

#### Data Tidak Tersimpan
1. **Check Connection**: Pastikan koneksi internet
2. **Supabase Setup**: Verifikasi konfigurasi Supabase
3. **RLS Policies**: Check Row Level Security
4. **Console Errors**: Periksa console untuk error

#### QR Code Tidak Ter-generate
1. **Library Load**: Pastikan QRCode.js ter-load
2. **Data Validation**: Periksa data permit
3. **Browser Support**: Pastikan support Canvas API
4. **Memory Issues**: Refresh halaman

### Debug Mode
- **Console Logs**: Detailed logging
- **Network Tab**: Monitor network requests
- **Error Messages**: User-friendly errors
- **Status Indicators**: Visual status

## 📚 **Documentation**

### User Guides
- [Quick Start Guide](quick-start.md)
- [QR Code Features](qr-code-features.md)
- [Scanner Setup](scanner-setup.md)
- [Database Setup](database-setup.md)

### Technical Docs
- [API Reference](api-reference.md)
- [Database Schema](database-schema.md)
- [Security Guide](security-guide.md)
- [Deployment Guide](deployment-guide.md)

### Troubleshooting
- [Debug Checklist](debug-checklist.md)
- [Common Issues](troubleshooting.md)
- [FAQ](faq.md)

## 🤝 **Contributing**

### Development Setup
1. **Fork Repository**: Fork project
2. **Create Branch**: Buat feature branch
3. **Make Changes**: Implementasi fitur
4. **Test**: Test thoroughly
5. **Submit PR**: Submit pull request

### Code Standards
- **ESLint**: Follow linting rules
- **Prettier**: Consistent formatting
- **Comments**: Document complex code
- **Testing**: Write tests for new features

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 **Acknowledgments**

- **JsBarcode**: Barcode generation library
- **QRCode.js**: QR Code generation library
- **ZXing**: Barcode/QR Code scanning library
- **Supabase**: Backend-as-a-Service
- **Tailwind CSS**: CSS framework

## 📞 **Support**

### Getting Help
- **Documentation**: Check documentation first
- **Issues**: Report bugs on GitHub
- **Discussions**: Ask questions in discussions
- **Email**: Contact for enterprise support

### Community
- **GitHub**: [Repository](https://github.com/your-repo)
- **Discussions**: [GitHub Discussions](https://github.com/your-repo/discussions)
- **Issues**: [GitHub Issues](https://github.com/your-repo/issues)

---

**Sistem Permit Kendaraan** - Solusi lengkap untuk manajemen akses kendaraan dengan teknologi modern! 🚗✨
