# Productivity Data Lake (PDL) – MPC

Sistem dalaman Malaysia Productivity Corporation untuk mencari, menganalisis dan memetik data produktiviti buruh (nasional, negeri, sektor, Productivity Nexus dan antarabangsa), dengan Ejen AI yang menjawab berdasarkan data rasmi dan menunjukkan sumber setiap angka.

*An internal MPC system to find, analyse and cite labour productivity data, with an AI Agent that answers from official data and shows the source of every figure.*

---

## Status penting / Important status

| | |
|---|---|
| **Versi langsung (berfungsi penuh)** | Dijalankan sebagai Artifact di claude.ai dan dikongsi dengan organisasi MPC. |
| **Repositori ini** | Salinan kod sumber dan data awam, untuk simpanan, semakan dan pembangunan versi web sendiri. |
| **GitHub Pages** | `index.html` boleh dibuka, tetapi **tidak akan berfungsi sepenuhnya** di luar claude.ai: pangkalan data, log masuk, storan fail dan Ejen AI disediakan oleh runtime claude.ai (`window.claude`). Halaman akan memaparkan skrin log masuk sahaja. |

*The live, fully working system runs as a claude.ai Artifact. This repository holds the source and public data. On GitHub Pages the page opens but stays on the sign-in screen, because the database, login, file storage and AI come from the claude.ai runtime.*

## Kandungan / Contents

```
index.html                       Aplikasi lengkap (HTML + CSS + JS, satu fail)
data/
  produktiviti_suku_tahunan.csv  DOSM – produktiviti buruh suku tahunan mengikut aktiviti ekonomi
  produktiviti_buruh_negeri.csv  DOSM – produktiviti buruh mengikut negeri dan sektor
  nexus.csv                      Produktiviti 11 Productivity Nexus (sumber: DOSM / MPC)
  antarabangsa_ilo.csv           ILO ILOSTAT – output per pekerja dan per jam (USD PPP 2021)
```

**Tidak disertakan dengan sengaja** (hak cipta / lesen pihak ketiga): PDF APO Productivity Databook 2021–2026, set data APO yang ditranskripsi, dan ranking IMD/WEF. Data ini kekal dalam versi claude.ai sahaja.

*Intentionally excluded for third-party copyright/licence reasons: APO Databook PDFs, the transcribed APO dataset, and IMD/WEF rankings.*

## Ciri utama / Key features

- Ringkasan: KPI dengan garis trend, panel peranan (Pentadbir / Pengguna), carta trend, kemas kini terkini
- Ejen AI dengan label sumber mudah: **Sumber**, **Dikira**, **Rujukan**; tidak meneka angka
- Carian pintar BM/EN yang mencari dalam isi data, dengan cadangan segera
- Analitik dan Penanda Aras Antarabangsa: pilihan jenis graf (bar, lajur, lolipop, garis, kawasan, jadual) dan peta haba interaktif
- Istilah & Definisi (Lampiran A MPC)
- Laporan & muat turun (CSV, Excel, PDF)
- Pentadbiran: muat naik (xlsx/csv/json/pdf/docx), versi, pengesahan, arkib, sejarah, ekstrak teks PDF
- Log masuk e-mel @mpc.gov.my, lawatan berpandu, notifikasi, BM/EN, mesra telefon

## Konfigurasi / Configuration

Senarai pentadbir dalam `index.html`:

```js
const ADMIN_EMAILS = []; // cth. ['nama@mpc.gov.my']
```

E-mel pentadbir sengaja dikosongkan dalam repositori awam ini.

## Langkah seterusnya untuk laman web sendiri / Next steps for a standalone website

Untuk menjalankan sistem di luar claude.ai, lapisan sambungan perlu diganti dengan backend sendiri:

- **Pilihan A:** GitHub Pages + Supabase (pangkalan data, storan, log masuk Microsoft terhad kepada @mpc.gov.my, fungsi pelayan untuk Claude API)
- **Pilihan B:** GitHub → Azure Static Web Apps + Azure Functions (log masuk tunggal Microsoft 365 MPC)

Kedua-duanya memerlukan kelulusan IT MPC, akaun awan, dan kunci Claude API milik MPC yang disimpan di pelayan (bukan dalam kod ini).

---

© Malaysia Productivity Corporation. Data DOSM dan ILO tertakluk kepada syarat penggunaan sumber masing-masing.
