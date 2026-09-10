# GJR White-Space & Distributor Map 🗺️

Peta interaktif **coverage & white-space analysis** untuk Greater Jakarta Region (GJR), dilengkapi tagging titik distributor untuk perencanaan kunjungan lapangan.

## 🔗 Live Demo
Setelah GitHub Pages aktif, peta bisa diakses di:
```
https://<username>.github.io/<nama-repo>/
```

## ✨ Fitur
- **Basemap satelit** (Esri World Imagery) + tampilan Jalan (OSM) — tekstur perumahan langsung terlihat.
- **White-space residensial** — area berpenduduk yang belum ada outlet, diberi prioritas P1–P4 (kepadatan × potensi Podes).
- **12 titik distributor** berwarna + label; tiap white-space di-assign ke **distributor terdekat**.
- **Klik white-space** → info kepadatan, distributor terdekat, jarak, dan tombol **Buka di Google Maps** untuk navigasi visit.
- Dua resolusi grid: **Jabodetabek 500 m** · **Banten luar 1 km**.

## 📊 Ringkasan Data
| Metrik | Nilai |
|---|---|
| White-space residensial | 4.725 cell |
| Prioritas P1 (Top 5%) | 237 cell |
| Titik distributor | 12 (10 perusahaan) |
| Jarak median ke distributor | 9,3 km |

## 🧮 Metodologi (singkat)
1. **Spatial join** outlet → kecamatan (point-in-polygon).
2. **Settlement score** dari kepadatan outlet ber-bobot jarak → memisahkan permukiman vs hutan/rawa.
3. **Dasymetric mapping** — populasi & outlet universe (BPS Podes) disebar ke grid berdasarkan bobot permukiman.
4. **White-space** = cell tanpa outlet tapi ada permukiman; prioritas dari kepadatan × potensi Podes.
5. **Assignment** white-space → distributor terdekat (haversine).

## 🚀 Cara Deploy ke GitHub Pages
1. Buat repo baru (Public), upload `index.html`.
2. **Settings → Pages** → Source: branch `main`, folder `/ (root)` → Save.
3. Tunggu ±1–2 menit, buka link Pages.

## ⚠️ Catatan
- File `index.html` **self-contained** (data & basemap tertanam) — cukup upload 1 file ini.
- Data outlet & populasi bersifat internal; pertimbangkan repo **private** atau **Netlify (private)** bila sensitif.

---
*Dibuat untuk analisis Route-to-Market GJR — Distribution & Field Practices.*
