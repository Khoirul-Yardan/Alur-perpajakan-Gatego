
# Rumus Perhitungan Tarif Penumpukan Petikemas (TPK Semarang)

Dokumen ini menjelaskan **rumus perhitungan tarif progresif penumpukan petikemas internasional** di Terminal Petikemas (TPK) Semarang,
berdasarkan ketentuan resmi PT Pelabuhan Indonesia (Persero) dan Kementerian Perhubungan RI.

---

## 1. Definisi Variabel

- **B** = Tarif dasar per hari (Rp/hari), berbeda tergantung ukuran & jenis petikemas  
  Contoh: 20' full container = Rp 26.700/hari  
- **N** = Jumlah hari petikemas berada di lapangan  
- **m(d)** = Multiplier (faktor tarif) pada hari ke-d, sesuai ketentuan masa penumpukan  
- **Total** = Total biaya penumpukan (Rp)

---

## 2. Rumus Umum

Per hari:
```
Biaya hari ke-d = B × m(d)
```

Total untuk N hari:
```
Total = Σ (B × m(d)), untuk d = 1 sampai N
```

Jika dikelompokkan per level multiplier:
```
Total = B × (n1·m1 + n2·m2 + n3·m3 + ...)
```
dengan:
- **n1, n2, n3** = jumlah hari pada tiap level
- **m1, m2, m3** = multiplier pada tiap level

---

## 3. Aturan Multiplier

### A. Import – Full Container
- Hari 1–2 → Gratis (m=0)  
- Hari 3 → 400% (m=4)  
- Hari 4–5 → 700% (m=7)  
- Hari ≥6 → 700% (m=7)  

### B. Export atau Import – Empty Container
- Hari 1–5 → 100% (m=1)  
- Hari 6–10 → 200% (m=2)  
- Hari ≥11 → 300% (m=3)  

---

## 4. Contoh Perhitungan

**Kasus:**  
20' Import Full Container, tarif dasar **B = Rp 26.700/hari**, lama penumpukan **N = 7 hari**.

- Hari 1–2: Gratis → 2 × (26.700 × 0) = Rp 0  
- Hari 3: 1 × (26.700 × 4) = Rp 106.800  
- Hari 4–7: 4 × (26.700 × 7) = Rp 747.600  

**Total = Rp 854.400**

---

## 5. Cara Praktis di Excel / Spreadsheet

### Metode 1 – Per Hari
Buat kolom:
- Hari (1..N)  
- Multiplier (isi sesuai aturan)  
- BiayaHari = B * Multiplier  

Total = `SUM(BiayaHari)`

### Metode 2 – Kelompok Hari
Jika jumlah hari & multiplier dikelompokkan, gunakan formula:
```
= B * SUMPRODUCT(JumlahHari; Multiplier)
```

---

## 6. Referensi Resmi

1. **Surat Menteri Perhubungan Republik Indonesia Nomor: PR.302/2/10/PHB/2023**  
   Tentang Rekomendasi Persetujuan Penyesuaian Tarif Jasa Kepelabuhanan pada PT Pelabuhan Indonesia (Persero)  
   (21 Maret 2023).

2. **Surat Edaran General Manager TPK Semarang Nomor: PJ.02.01/26/5/2/SMSK/GMAN/TPSM-23**  
   Tentang Tarif Pelayanan Lapangan dan Container Freight Station (CFS) di TPK Semarang  
   (26 Mei 2023).

3. **Peraturan Direksi PT Pelabuhan Indonesia III (Persero) Nomor: PER.09/PU.03/P.III-2013**  
   Tentang Tarif Pelayanan Operasi Lapangan dan Container Freight Station di Lingkungan PT Pelabuhan Indonesia III (Persero) Terminal Petikemas Semarang  
   (1 April 2013).

4. **Dokumen Tarif Pelayanan Lapangan dan CFS Petikemas Internasional – TPK Semarang** (PDF yang Anda lampirkan).

---

📌 **Catatan:** Ketentuan ini berlaku efektif mulai **5 Juni 2023 pukul 00.00 WIB** sesuai surat edaran resmi.
