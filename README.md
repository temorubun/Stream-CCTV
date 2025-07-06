# RTSP Camera Stream Viewer

Aplikasi web sederhana untuk menampilkan stream video dari kamera RTSP menggunakan Flask dan OpenCV.

## Fitur
- Streaming video langsung dari kamera RTSP
- Antarmuka web yang responsif
- Mudah dikonfigurasi

## Persyaratan Sistem
- Python 3.9 atau lebih baru
- Docker (opsional)
- Koneksi jaringan ke kamera RTSP

## Dependensi
- Flask 3.0.2
- OpenCV Python (Headless) 4.8.1.78
- NumPy 1.24.3

## Cara Instalasi

### Menggunakan Python Langsung

1. Clone repositori ini
2. Install dependensi:
```bash
pip install -r requirements.txt
```
3. Jalankan aplikasi:
```bash
python app.py
```

### Menggunakan Docker

1. Clone repositori ini
2. Jalankan container Docker:
```bash
docker run -it --network host --name python_dev -v ${PWD}:/app -w /app python:3.9 bash
```
3. Di dalam container, install dependensi dan jalankan aplikasi:
```bash
pip install -r requirements.txt
python app.py
```

## Konfigurasi

Konfigurasi URL RTSP dapat diubah di file `app.py`:

```python
rtsp_url = 'rtsp://admin:BGENWW@192.168.100.28:554/stream'
```

Ganti URL sesuai dengan konfigurasi kamera RTSP Anda.

## Penggunaan

1. Pastikan kamera RTSP Anda aktif dan dapat diakses
2. Jalankan aplikasi menggunakan salah satu metode di atas
3. Buka browser web dan akses:
```
http://localhost:5000
```

## Troubleshooting

1. **Stream tidak muncul**
   - Periksa apakah URL RTSP benar
   - Pastikan kredensial (username/password) benar
   - Periksa koneksi jaringan ke kamera
   - Lihat log terminal untuk pesan error

2. **Port 5000 sudah digunakan**
   - Ubah port di `app.py` dengan menambahkan parameter port:
   ```python
   app.run(debug=True, port=5001)
   ```

3. **Masalah Performa**
   - Pastikan koneksi jaringan stabil
   - Kurangi resolusi video jika diperlukan
   - Periksa penggunaan CPU dan memori

## Keamanan

- Jangan menyimpan kredensial RTSP langsung dalam kode
- Gunakan variabel lingkungan atau file konfigurasi terpisah
- Batasi akses ke aplikasi web menggunakan autentikasi jika diperlukan

## Lisensi

Proyek ini dilisensikan di bawah MIT License - lihat file LICENSE untuk detail. 