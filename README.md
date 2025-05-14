# Script Ryu untuk Routing & Filtering Antar UMKM
Kita akan modifikasi simple_switch_13 dari Ryu dengan fitur:
- Static forwarding (MAC learning)
- Filtering trafik berdasarkan IP sumber/tujuan
- Contoh: UMKM resellerjakarta (10.0.0.4) tidak boleh langsung akses batikjogja (10.0.0.1) → hanya boleh ke cloud

🛠️ Cara Menjalankan:
1. Simpan file sebagai fashion_firewall_ryu.py
2. Jalankan Ryu dengan:
ryu-manager fashion_firewall_ryu.py
3. Jalankan topology.py di Mininet seperti sebelumnya
sudo python3 topology.py
4. Coba:
resellerjakarta ping batikjogja   # Akan gagal
resellerjakarta ping cloud        # Akan berhasil

✅ Fitur Tambahan Yang Bisa Ditambahkan (opsional):
- Logging ke file audit
- Bypass dengan role tertentu (jika nanti diintegrasikan ke ZTNA)
- Dynamic ACL via REST API
