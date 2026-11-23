# Claros

Claros is a browser-based set of exercises for examining your own beliefs and training how you reason, aimed at the kind of thinking traps social media and algorithmic feeds tend to reinforce: confirmation bias, groupthink and unexamined assumptions. Everything runs client-side: a visitor's answers are scored by a local routine and saved to `localStorage`, so there is no account, no server, and no data leaving the browser.

[Baca dalam Bahasa Indonesia di bawah](#bahasa-indonesia)

## Modules

| Route | Module | What it does |
| --- | --- | --- |
| `/` | Dashboard | An overview of past audits and scores, plus a short note on where the name "Claros" comes from |
| `/audit` | Belief Audit | Record a specific belief, then work through a structured audit of where it came from and how strongly you hold it |
| `/gym` | Critical Gym | Two kinds of drill: a steel-manning challenge (build the strongest version of the argument you disagree with, to counter conformity bias) and a scenario simulator that walks a dialogue tree against common cognitive biases |
| `/map` | Origin Map | Plots each recorded belief's source against your confidence in it, so patterns (for example, high confidence in beliefs with a weak source) become visible |
| `/score` | Clarity Score | Tracks how your belief map shifts session to session, as a score |

## How the scoring works

`src/services/aiService.js` holds the scoring logic. Its comment describes it as matching the shape of a future `POST /api/analyze` endpoint, but today it runs entirely in the browser: no network request is made, and nothing is sent anywhere. `src/services/dbService.js` is the storage layer, reading and writing everything to `localStorage` under a small set of keys, and seeding sensible defaults the first time someone opens the app.

## Tech stack

React, Vite, React Router, Recharts for the charts on the Dashboard and Clarity Score pages, Tailwind CSS. Deployed on Vercel.

## Getting started

```bash
npm install
npm run dev        # development server with hot reload
npm run build       # production build into dist/
npm run lint
```

There is nothing to configure: no environment variables, no backend to stand up, and no account to create. Opening the dev server is enough to use every module.

## Project structure

```
src/pages        one file per module (BeliefAudit, ClarityScore, CriticalGym, Dashboard, OriginMap)
src/components    UI shared across pages
src/context       app-wide state (the current user's audits and progress)
src/services      aiService.js (local scoring) and dbService.js (localStorage persistence)
prototype/        the project's earlier static HTML version of the four modules
```

`prototype/` comes from the former Verity repository, merged into this one together with its own commit history, so the earlier iteration of the idea is kept rather than discarded.

---

## Bahasa Indonesia

Claros adalah kumpulan latihan berbasis peramban untuk menelaah keyakinan sendiri dan melatih cara bernalar, menyasar jenis jebakan berpikir yang sering diperkuat media sosial dan feed algoritmik: bias konfirmasi, groupthink, dan asumsi yang tidak pernah diuji. Semuanya berjalan di sisi klien: jawaban pengunjung dinilai oleh rutinitas lokal dan disimpan di `localStorage`, jadi tidak ada akun, tidak ada server, dan tidak ada data yang keluar dari peramban.

### Modul

| Rute | Modul | Fungsi |
| --- | --- | --- |
| `/` | Dashboard | Ringkasan audit dan skor sebelumnya, ditambah catatan singkat tentang asal nama "Claros" |
| `/audit` | Belief Audit | Mencatat satu keyakinan tertentu, lalu menelusurinya lewat audit terstruktur tentang asalnya dan seberapa kuat kamu memegangnya |
| `/gym` | Critical Gym | Dua jenis latihan: tantangan steel-manning (menyusun argumen terkuat dari sisi yang tidak kamu setujui, untuk melawan bias konformitas) dan simulator skenario yang menjalankan pohon dialog melawan bias kognitif umum |
| `/map` | Origin Map | Memetakan sumber tiap keyakinan yang tercatat terhadap tingkat keyakinanmu padanya, sehingga pola (misalnya keyakinan tinggi pada sumber yang lemah) jadi terlihat |
| `/score` | Clarity Score | Memantau pergeseran peta keyakinanmu dari sesi ke sesi, sebagai sebuah skor |

### Cara penilaian bekerja

`src/services/aiService.js` menyimpan logika penilaiannya. Komentarnya menyebut bentuk keluarannya disamakan dengan rencana endpoint `POST /api/analyze` di masa depan, tapi sekarang semuanya berjalan sepenuhnya di peramban: tidak ada permintaan jaringan yang dibuat, dan tidak ada apa pun yang dikirim ke mana pun. `src/services/dbService.js` adalah lapisan penyimpanannya, membaca dan menulis semuanya ke `localStorage` di bawah beberapa kunci, dan mengisi nilai awal yang masuk akal saat pertama kali aplikasi dibuka.

### Teknologi

React, Vite, React Router, Recharts untuk grafik di halaman Dashboard dan Clarity Score, Tailwind CSS. Dideploy di Vercel.

### Menjalankan

```bash
npm install
npm run dev        # server pengembangan dengan hot reload
npm run build       # build produksi ke dist/
npm run lint
```

Tidak ada yang perlu dikonfigurasi: tidak ada variabel lingkungan, tidak ada backend yang harus disiapkan, dan tidak ada akun yang harus dibuat. Membuka server dev saja sudah cukup untuk memakai semua modul.

### Struktur

```
src/pages        satu berkas per modul (BeliefAudit, ClarityScore, CriticalGym, Dashboard, OriginMap)
src/components    komponen UI yang dipakai bersama di banyak halaman
src/context       state di seluruh aplikasi (audit dan progres pengguna saat ini)
src/services      aiService.js (penilaian lokal) dan dbService.js (penyimpanan localStorage)
prototype/        versi HTML statis awal proyek ini untuk keempat modul
```

`prototype/` berasal dari repositori Verity yang dulu terpisah, digabung ke sini beserta riwayat commit-nya sendiri, sehingga iterasi awal dari gagasan ini tetap tersimpan, bukan dibuang.
