# QR Code 2D Features - Sistem Permit Kendaraan

## Overview
Sistem QR Code 2D yang terintegrasi dengan sistem permit kendaraan, memungkinkan generate, print, download, dan scan QR Code untuk manajemen akses kendaraan yang lebih efisien.

## Fitur Utama

### 1. Generate QR Code Individual
- **Pemilihan Permit**: Dropdown untuk memilih permit yang akan di-generate QR Code
- **Ukuran QR Code**: Pilihan ukuran 128x128, 256x256, atau 512x512 pixel
- **Error Correction**: Level L (7%), M (15%), Q (25%), H (30%)
- **Data Lengkap**: QR Code berisi semua informasi permit dalam format JSON
- **Preview Real-time**: Tampilan QR Code langsung setelah generate

### 2. Print & Download QR Code
- **Print QR Code**: Cetak QR Code dengan detail permit lengkap
- **Download PNG**: Download QR Code dalam format PNG
- **Layout Print**: Tampilan print yang rapi dengan informasi permit

### 3. Bulk QR Code Generation
- **Multi-Select**: Pilih multiple permit sekaligus
- **Format Output**: PNG, SVG, atau PDF
- **Grid Layout**: Tampilan grid untuk multiple QR Code
- **Print All**: Cetak semua QR Code dalam satu halaman

### 4. QR Code Scanner
- **Camera Selection**: Pilih kamera (prioritas kamera belakang)
- **Real-time Scanning**: Scan QR Code secara real-time
- **Auto-log**: Otomatis mencatat log saat scan berhasil
- **Visual Feedback**: Tampilan hasil scan yang informatif
- **Audio Feedback**: Beep saat scan berhasil

## Data Format QR Code

### Struktur JSON
```json
{
  "permit_code": "PRM-2025-001",
  "plate": "B 1234 ABC",
  "owner": "John Doe",
  "type": "Mobil",
  "valid_from": "2025-01-01",
  "valid_to": "2025-12-31",
  "stnk_exp": "2025-06-30",
  "simc_exp": "2025-08-15",
  "sima_exp": "2025-10-20",
  "status": "active",
  "timestamp": "2025-01-15T10:30:00.000Z"
}
```

### Informasi yang Disimpan
- **permit_code**: Kode unik permit
- **plate**: Nomor plat kendaraan
- **owner**: Nama pemilik kendaraan
- **type**: Jenis kendaraan (Mobil/Motor/Truck)
- **valid_from/valid_to**: Periode berlaku umum
- **stnk_exp**: Masa berlaku STNK
- **simc_exp**: Masa berlaku SIM C
- **sima_exp**: Masa berlaku SIM A
- **status**: Status permit (active/expired/pending)
- **timestamp**: Waktu generate QR Code

## Cara Penggunaan

### Generate QR Code Individual
1. Buka tab "QR Code"
2. Pilih permit dari dropdown "Pilih Permit"
3. Atur ukuran dan error correction level
4. Klik "Generate QR"
5. QR Code akan muncul di area display
6. Gunakan tombol "Print" atau "Download" sesuai kebutuhan

### Generate Bulk QR Code
1. Scroll ke bagian "Bulk QR Code Generation"
2. Pilih multiple permit (Ctrl/Cmd + klik)
3. Atur ukuran dan format output
4. Klik "Generate Bulk"
5. Semua QR Code akan ditampilkan dalam grid
6. Gunakan "Print All" untuk mencetak semua QR Code

### Scan QR Code
1. Buka tab "QR Code"
2. Pilih kamera dari dropdown
3. Klik "Mulai Scan"
4. Arahkan kamera ke QR Code
5. Sistem akan otomatis membaca dan menampilkan hasil
6. Jika auto-log aktif, akan otomatis mencatat log

## Technical Details

### Libraries Used
- **QRCode.js**: Library untuk generate QR Code
- **ZXing**: Library untuk scan QR Code
- **Canvas API**: Untuk rendering QR Code

### Browser Compatibility
- **Chrome**: Full support
- **Firefox**: Full support
- **Safari**: Full support (iOS 11+)
- **Edge**: Full support

### Mobile Support
- **Camera Access**: Menggunakan getUserMedia API
- **Touch Interface**: Optimized untuk layar sentuh
- **Responsive Design**: Menyesuaikan ukuran layar
- **PWA Ready**: Dapat diinstall sebagai aplikasi

## Error Handling

### Generate Errors
- **Invalid Data**: Validasi data sebelum generate
- **Library Errors**: Fallback jika QRCode.js gagal
- **Memory Issues**: Handling untuk QR Code besar

### Scan Errors
- **Camera Permission**: Handling jika izin kamera ditolak
- **No Camera**: Fallback jika tidak ada kamera
- **Invalid QR**: Handling untuk QR Code yang tidak valid
- **Network Issues**: Offline mode support

## Performance Optimization

### Generate Optimization
- **Lazy Loading**: QR Code hanya di-generate saat diperlukan
- **Caching**: Cache QR Code yang sudah di-generate
- **Size Control**: Batasan ukuran untuk performa

### Scan Optimization
- **Frame Rate**: Optimized frame rate untuk scan
- **Memory Management**: Proper cleanup setelah scan
- **Error Recovery**: Auto-recovery dari error

## Security Features

### Data Validation
- **Input Sanitization**: Validasi input sebelum generate
- **JSON Validation**: Validasi format JSON saat scan
- **Permission Check**: Validasi izin kamera

### Access Control
- **Admin Only**: Generate dan bulk operations hanya untuk admin
- **Logging**: Semua aktivitas QR Code dicatat dalam log
- **Audit Trail**: Tracking semua generate dan scan

## Integration Points

### Database Integration
- **Supabase Sync**: QR Code data tersinkron dengan cloud
- **Local Storage**: Fallback ke localStorage
- **Real-time Updates**: Update otomatis saat data berubah

### Logging Integration
- **Auto-log**: Otomatis mencatat scan ke log
- **Event Tracking**: Tracking semua QR Code events
- **Analytics**: Data untuk analisis penggunaan

## Troubleshooting

### Common Issues

#### QR Code Tidak Ter-generate
1. Pastikan permit sudah dipilih
2. Cek console untuk error messages
3. Refresh halaman jika diperlukan
4. Pastikan browser support Canvas API

#### Scanner Tidak Berfungsi
1. Pastikan izin kamera diberikan
2. Cek apakah kamera tidak digunakan aplikasi lain
3. Coba refresh halaman
4. Pastikan QR Code dalam kondisi baik

#### Print Tidak Berfungsi
1. Pastikan popup blocker dinonaktifkan
2. Cek printer settings
3. Coba download dulu lalu print manual
4. Pastikan browser support print API

### Debug Mode
- **Console Logs**: Detailed logs untuk debugging
- **Error Messages**: User-friendly error messages
- **Status Indicators**: Visual status untuk setiap operasi

## Best Practices

### Generate QR Code
1. **Ukuran Optimal**: Gunakan 256x256 untuk kebanyakan kasus
2. **Error Correction**: Gunakan level M untuk balance
3. **Data Validation**: Pastikan data lengkap sebelum generate
4. **Testing**: Test QR Code sebelum deploy

### Scan QR Code
1. **Lighting**: Pastikan pencahayaan cukup
2. **Distance**: Jaga jarak optimal (10-30cm)
3. **Stability**: Jaga kamera stabil saat scan
4. **Clean Surface**: Pastikan QR Code tidak rusak

### Print QR Code
1. **Quality**: Gunakan printer berkualitas baik
2. **Size**: Sesuaikan ukuran dengan kebutuhan
3. **Material**: Gunakan material yang tahan lama
4. **Placement**: Tempatkan di lokasi yang mudah diakses

## Future Enhancements

### Planned Features
- **QR Code Templates**: Template kustom untuk QR Code
- **Batch Processing**: Process multiple QR Code sekaligus
- **Analytics Dashboard**: Dashboard untuk analisis QR Code usage
- **API Integration**: REST API untuk generate QR Code

### Advanced Features
- **Dynamic QR Code**: QR Code yang dapat diupdate
- **Encrypted QR Code**: QR Code dengan enkripsi
- **Multi-language**: Support multiple languages
- **Cloud Storage**: Simpan QR Code di cloud

## Support

### Documentation
- **User Guide**: Panduan lengkap penggunaan
- **API Reference**: Dokumentasi API
- **Examples**: Contoh penggunaan

### Contact
- **Technical Support**: Untuk masalah teknis
- **Feature Requests**: Untuk request fitur baru
- **Bug Reports**: Untuk melaporkan bug

---

*Dokumentasi ini akan terus diupdate sesuai dengan perkembangan fitur QR Code.*
