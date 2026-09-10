# 🗺️ GJR White-Space & Distributor Map

Peta interaktif **analisis white-space (area kosong outlet)** berbasis kepadatan penduduk untuk wilayah **Greater Jakarta Region (GJR)** — mencakup Jabodetabek dan Banten luar. Dibuat untuk mendukung strategi ekspansi coverage & produktivitas distribusi (General Trade).

🔗 **Live demo:** [https://barnabasra.github.io/WhitespaceGJR/](https://barnabasra.github.io/WhitespaceGJR/)

---

## 📌 Tentang Proyek

Tool ini memetakan **37.698 outlet terdaftar** ke level kecamatan, lalu mendeteksi **white-space residensial** — yaitu area yang **ada permukiman tapi belum tergarap outlet**. Area hutan, rawa, dan lahan kosong otomatis difilter agar hasilnya benar-benar *actionable* untuk kunjungan lapangan.

Setiap white-space cell bisa **diklik langsung menuju Google Maps** untuk mempermudah navigasi saat visit.

---

## ✨ Fitur Utama

| Fitur | Deskripsi |
|-------|-----------|
| 🛰️ **Basemap satelit** | Toggle antara Satelit (berlabel/polos) dan peta jalan (OSM) — tekstur perumahan langsung terlihat |
| 🎯 **White-space prioritas** | Klasifikasi P1 (Top 5%) → P4 berdasarkan kepadatan penduduk × potensi Podes |
| 📍 **Klik → Google Maps** | Setiap cell white-space punya tombol navigasi langsung ke koordinat |
| 🏢 **Titik distributor** | 12 titik distributor dengan info area & jarak ke white-space terdekat |
| 🌡️ **Choropleth kepadatan** | Layer kepadatan penduduk per km² (dasymetric mapping) |
| 🔵 **Sebaran outlet** | 37.698 titik outlet existing |

---

## 🧭 Cara Menggunakan

1. **Buka** [live demo](https://barnabasra.github.io/WhitespaceGJR/)
2. **Pilih basemap** (kanan atas) — default: Satelit
3. **Aktif/nonaktifkan layer**: White-space, Kepadatan, Outlet, Distributor
4. **Klik kotak white-space** → baca info prioritas → tekan **📍 Buka di Google Maps** untuk visit
5. **Fokus prioritas** P1 (merah) untuk target kunjungan tercepat

---

## 🔬 Metodologi

| Tahap | Penjelasan |
|-------|-----------|
| **Grid** | Jabodetabek = **500m** (presisi tinggi) · Banten luar = **1km** (area rural luas) |
| **Settlement score** | Kepadatan outlet ber-bobot jarak (radius ~2km) → sinyal permukiman |
| **Dasymetric mapping** | Populasi & Outlet Universe (BPS Podes) disebar ke cell berdasarkan bobot permukiman |
| **White-space residensial** | Cell **tanpa outlet** tapi **ada permukiman** (hutan/rawa difilter) |
| **Prioritas (WS Score)** | Kepadatan penduduk × potensi Podes/km² → P1 (Top 5%), P2 (Top 20%), P3 (Top 50%), P4 |

---

## 📊 Ringkasan Angka

- **Total white-space residensial:** 4.725 cell
  - Jabodetabek (500m): 3.989
  - Banten luar (1km): 736
- **Prioritas P1 (Top 5%):** 237 cell
- **Coverage vs Podes:** Metro 25,7% · Urban 12,1% · Rural 5,1%

---

## 🎨 Legenda Prioritas

| Warna | Tier | Arti |
|-------|------|------|
| 🔴 Merah | **P1** | Top 5% — prioritas tertinggi |
| 🟠 Oranye | **P2** | Top 20% |
| 🟡 Kuning | **P3** | Top 50% |
| 🟢 Hijau | **P4** | Sisanya |

Tag grid: 🔵 `500m` Jabodetabek · 🟣 `1km` Banten luar

---

## 📁 Struktur Repo

```
WhitespaceGJR/
├── index.html      # Peta interaktif (self-contained, semua data ter-embed)
└── README.md       # Dokumentasi ini
```

> **Catatan:** File `index.html` bersifat *self-contained* — seluruh data GeoJSON & basemap sudah tertanam, jadi tidak perlu file data terpisah.

---

## 🚀 Deploy (GitHub Pages)

1. Upload `index.html` ke root repo
2. Buka **Settings → Pages**
3. Source: branch `main` + folder `/ (root)` → **Save**
4. Tunggu ±1–2 menit, akses di `https://<username>.github.io/<repo>/`

> ⚠️ File **harus** bernama `index.html` agar tampil di URL root.

---

## 🛠️ Dibangun Dengan

- [Leaflet 1.9.4](https://leafletjs.com/) — peta interaktif
- [Esri World Imagery](https://www.esri.com/) — basemap satelit
- [OpenStreetMap](https://www.openstreetmap.org/) — basemap jalan
- Python (GeoPandas, Shapely) — pemrosesan geospasial
- Data: EagleEyes Outlet Registered · BPS Podes · Batas kecamatan GeoJSON

---

## 📝 Lisensi & Catatan

Proyek internal untuk analisis distribusi GJR. Data outlet & populasi bersifat internal — harap perhatikan kerahasiaan sebelum membagikan repo secara publik.

---

*Dibuat untuk mendukung strategi coverage & produktivitas General Trade — Greater Jakarta Region.*
