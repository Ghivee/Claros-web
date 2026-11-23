# Claros

Aplikasi peramban untuk menelusuri asal keyakinanmu dan melatih cara berargumen. Claros berjalan sepenuhnya di peramban: jawabanmu dinilai, hasilnya tampil di dashboard, dan riwayatnya disimpan di `localStorage`.

[English](README.md)

## Modul

| Rute | Modul | Fungsi |
| --- | --- | --- |
| `/` | Dashboard | Ringkasan, termasuk catatan singkat tentang asal nama Claros |
| `/audit` | Belief Audit | Mencatat sebuah keyakinan lalu mengauditnya |
| `/gym` | Critical Gym | Tantangan steel-manning dan simulator skenario untuk bias kognitif |
| `/map` | Origin Map | Memetakan sumber tiap keyakinan terhadap tingkat keyakinanmu |
| `/score` | Clarity Score | Memantau pergeseran peta keyakinanmu dari waktu ke waktu |

Analisis di `src/services/aiService.js` adalah rutinitas penilaian lokal yang bentuk keluarannya disamakan dengan respons `POST /api/analyze` di masa depan. Tidak ada data yang dikirim ke server.

## Teknologi

React, Vite, React Router, Recharts, Tailwind CSS. Dideploy di Vercel (`vercel.json`).

## Menjalankan

```bash
npm install
npm run dev        # server pengembangan
npm run build      # build produksi ke dist/
npm run lint
```

## Struktur

```
src/pages        satu berkas per modul
src/components   komponen UI bersama
src/context      state aplikasi
src/services     penilaian (aiService.js) dan penyimpanan (dbService.js)
prototype/       versi HTML statis awal dari keempat modul
```

`prototype/` berasal dari repositori Verity yang dulu terpisah, digabung ke sini beserta riwayatnya.
