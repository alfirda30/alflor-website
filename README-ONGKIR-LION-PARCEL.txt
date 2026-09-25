ALFLOR.ID — INTEGRASI ONGKIR LION PARCEL

TUJUAN
Website Alflor.id dapat dibuat agar pembeli memasukkan lokasi tujuan,
lalu sistem menghitung ongkir Lion Parcel secara otomatis berdasarkan
asal, tujuan, dan berat total produk.

Alur:
Pembeli pilih alamat -> sistem mencari ID lokasi tujuan ->
sistem menghitung ongkir Lion Parcel -> ongkir tampil di checkout ->
total otomatis diperbarui -> ongkir ikut dikirim ke WhatsApp admin.

PENTING
README ini adalah dokumentasi konfigurasi. Agar ongkir benar-benar
muncul otomatis, website harus terhubung ke API Shipping Cost
RajaOngkir/Komerce melalui backend/serverless.

Jangan menaruh API key langsung di index.html atau JavaScript frontend
yang dipublikasikan di GitHub.

YANG DIBUTUHKAN
1. RajaOngkir/Komerce Shipping Cost API Key
2. ID kecamatan asal toko
3. Berat masing-masing produk
4. Backend/serverless untuk menyimpan API key

KONFIGURASI
ORIGIN_DISTRICT_ID = jatiasih, bekasi
PRODUCT_WEIGHT_GRAM = 1 sweater = 1000 gram

Contoh:
1 sweater = 700 gram
2 sweater = 1400 gram
3 sweater = 2100 gram

FORM CHECKOUT
Nama
No. WhatsApp
Provinsi
Kabupaten/Kota
Kecamatan
Kode Pos
Alamat Lengkap

Setelah kecamatan dipilih:
[ Cek Ongkir Lion Parcel ]

Contoh hasil:
Lion Parcel
Regular
Rp18.000
Estimasi 2-3 hari

Total otomatis:
Subtotal     Rp150.000
Diskon       -Rp15.000
Ongkir        Rp18.000
TOTAL        Rp153.000

API
Base URL:
https://rajaongkir.komerce.id/api/v1/

Pencarian lokasi:
destination/domestic-destination

Kalkulasi ongkir:
calculate/domestic-cost

Kode kurir Lion Parcel:
lion

KEAMANAN
Simpan API key sebagai environment variable di backend.

JANGAN:
const API_KEY = "xxxxx";

di index.html.

Gunakan:
Frontend -> Backend Alflor -> RajaOngkir -> Backend -> Frontend

STATUS PROTOTYPE
Website saat ini sudah memiliki produk, keranjang, voucher,
checkout, WhatsApp, stok ukuran, dan admin lokal.

Untuk ongkir otomatis perlu:
- Form alamat bertingkat
- Berat otomatis
- Backend ongkir
- Hasil Lion Parcel
- Total checkout otomatis
- Ongkir masuk ke pesan WhatsApp

CHECKLIST
[ ] API key Shipping Cost RajaOngkir
[ ] Kecamatan asal toko
[ ] Berat sweater
[ ] Backend/serverless
[ ] API key sebagai secret/environment variable
[ ] Pencarian tujuan
[ ] Kalkulasi Lion Parcel
[ ] Tarif + estimasi tampil
[ ] Total diperbarui
[ ] WhatsApp menerima ongkir
[ ] Tes beberapa alamat

DOKUMENTASI RESMI
https://www.rajaongkir.com/docs/shipping-cost/getting_started/apikey
https://www.rajaongkir.com/docs/shipping-cost/getting_started/endpoint
https://www.rajaongkir.com/docs/shipping-cost/endpoint-rajaongkir-for-search-base/calculate-domestic-cost
