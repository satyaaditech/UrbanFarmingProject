# 21 — MULTI-AGENT ORCHESTRATION: Iterative AI Team untuk Proposal Bisnis

---

## 1. Arsitektur Tim

```
┌─────────────────────────────────────────────────────────────────┐
│                     COORDINATOR (Kamu)                           │
│            "Saya butuh proposal bisnis SMBPC 2026"              │
└─────────────────────────────────────────────────────────────────┘
                                │
        ┌───────────────────────┼───────────────────────┐
        ▼                       ▼                       ▼
┌───────────────┐      ┌───────────────┐      ┌───────────────┐
│    AGEN 1     │      │    AGEN 2     │      │    AGEN 3     │
│ MARKET        │◀────▶│ FINANCIAL     │◀────▶│ NARRATIVE     │
│ RESEARCHER    │      │ MODELER       │      │ WRITER        │
│               │      │               │      │               │
│ Butuh: data   │      │ Butuh: proyeksi│     │ Butuh: cerita │
│ pasar, tren,  │      │ revenue, cost,│      │ hook, tone,   │
│ target, size  │      │ breakeven     │      │ emotional hit │
└───────┬───────┘      └───────┬───────┘      └───────┬───────┘
        │                      │                      │
        └──────────────────────┼──────────────────────┘
                               │
                               ▼
                    ┌───────────────────┐
                    │      AGEN 4       │
                    │    VALIDATOR      │
                    │    & AUDITOR      │
                    │                   │
                    │ Cross-check:      │
                    │ • Sumber data     │
                    │ • Konsistensi     │
                    │ • Akurasi angka   │
                    │ • Format SMBPC    │
                    └────────┬──────────┘
                             │
                             ▼
                    ┌───────────────────┐
                    │      AGEN 5       │
                    │   SYNTHESIZER     │
                    │                   │
                    │ Gabung semua      │
                    │ input → final     │
                    │ proposal          │
                    └───────────────────┘
```

---

## 2. Pola Iterasi "Back-and-Forth"

Ini yang bikin multi-agent POWERFUL — agen tidak cuma lempar hasil ke depan, tapi saling review dan revisi.

### Round 0: BRIEFING (Semua agen baca konteks)

```
Coordinator → semua agen:
"Baca dokumen ini: 01-Master-Plan.md, 02-Sistem-Mekanik.md, 09-Validasi-Ilmiah.md, 
 19-Business-Proposal_competition.md (versi sebelumnya), detail kompetisi SMBPC 2026."
```

### Round 1: PARALLEL RESEARCH

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│ MARKET          │     │ FINANCIAL       │     │ NARRATIVE       │
│ RESEARCHER      │     │ MODELER         │     │ WRITER          │
├─────────────────┤     ├─────────────────┤     ├─────────────────┤
│ Output:         │     │ Output:         │     │ Output:         │
│ • Market size   │     │ • Revenue model │     │ • Hook cerita   │
│ • Target segmen │     │ • Cost structure│     │ • Tone & bahasa │
│ • Kompetitor    │     │ • 3-yr projeksi │     │ • SDG narrative │
│ • Tren industri │     │ • Breakeven     │     │ • Emotional arc │
└────────┬────────┘     └────────┬────────┘     └────────┬────────┘
         │                       │                       │
         └───────────────────────┼───────────────────────┘
                                 │
                                 ▼
```

### Round 2: CROSS-REVIEW (Back-and-Forth dimulai)

```
┌─────────────────────────────────────────────────────────────────┐
│  MARKET ←→ NARRATIVE                                            │
│                                                                  │
│  Narrative: "Target pasar kami 70 juta pemain Roblox"           │
│  Market:    "Verifikasi: Roblox Q1 2024 = 77.7M DAU global.    │
│              Untuk Indonesia, estimasi 10-12M MAU."             │
│  Narrative:  [REVISI] "12 juta pemain Roblox Indonesia"         │
│                                                                  │
│  Narrative: "Indonesia impor 60% pangan"                        │
│  Market:    "Spesifik: gandum 100% impor, kedelai 76%,          │
│              gula 60%. Angka '60% pangan' terlalu general."     │
│  Narrative:  [REVISI] "Indonesia impor 76% kedelai, 100%       │
│              gandum, 60% gula (BPS 2023)"                       │
├─────────────────────────────────────────────────────────────────┤
│  FINANCIAL ←→ MARKET                                            │
│                                                                  │
│  Financial: "Proyeksi 75.000 MAU Year 2"                        │
│  Market:    "Benchmark game edukasi Roblox: 15K-100K MAU.      │
│              Angka 75K masuk akal untuk Year 2."                │
│  Financial:  [APPROVED]                                          │
│                                                                  │
│  Market:    "ARPU Indonesia untuk Robux ≈ Rp 25K-50K/tahun"    │
│  Financial: "OK, saya pakai Rp 35K sebagai midpoint konservatif" │
│  Financial:  [REVISI revenue projection]                         │
├─────────────────────────────────────────────────────────────────┤
│  FINANCIAL ←→ NARRATIVE                                         │
│                                                                  │
│  Narrative: "Kami akan menghasilkan Rp 5.2 M di Year 3"         │
│  Financial: "Angka itu dari 200K MAU × Rp 35K ARPU + lisensi.  │
│              Perhitungan: 200K × Rp 35K × 0.4 kosmetik =        │
│              Rp 2.8M + lisensi + NGO = Rp 5.2M total."          │
│  Narrative:  "OK, saya tulis dengan confidence karena ada       │
│              perhitungan di belakangnya."                        │
└─────────────────────────────────────────────────────────────────┘
```

### Round 3: VALIDATION & REVISION LOOP

```
┌─────────────────────────────────────────────────────────────────┐
│  VALIDATOR mengecek setiap klaim:                                │
│                                                                  │
│  Validator: "❌ '80% anak muda tidak tahu asal makanan' —       │
│             tidak ada sumber. KEMBALIKAN KE NARRATIVE."          │
│  Narrative:  [REVISI] "Survei British Nutrition Foundation:     │
│             30-40% anak muda tidak paham asal-usul makanan."    │
│  Narrative:  → KIRIM ULANG KE VALIDATOR                         │
│  Validator: "✅ PASS — klaim sekarang punya sumber jelas."       │
│                                                                  │
│  Validator: "❌ '67% keluarga berkebun saat pandemi (BPS)' —     │
│             BPS tidak punya survei dengan angka spesifik ini.    │
│             KEMBALIKAN KE MARKET."                               │
│  Market:     "Oke, saya cek ulang. Sumber terbaik: Kementan RI  │
│              survey ketahanan pangan rumah tangga 2021-2022.    │
│              Revisi jadi klaim kualitatif: 'Jutaan keluarga...' │
│  Market:     → KIRIM ULANG KE VALIDATOR                         │
│  Validator: "✅ PASS."                                           │
│                                                                  │
│  Validator: "❌ Revenue streams di BMC (Bab 4) tidak cocok      │
│             dengan proyeksi keuangan (Bab 6). BMC sebut         │
│             Rp 150jt lisensi, Bab 6 hitung Rp 52.5jt.           │
│             KEMBALIKAN KE FINANCIAL."                            │
│  Financial:  "Saya konsistenkan ke Rp 52.5jt di BMC."           │
│  Financial:  → KIRIM ULANG KE VALIDATOR                         │
│  Validator: "✅ PASS. Konsisten."                                │
└─────────────────────────────────────────────────────────────────┘
```

### Round 4: SYNTHESIS

```
┌─────────────────────────────────────────────────────────────────┐
│  SYNTHESIZER menerima input final dari semua agen:              │
│  • Market Research Report → Bab 1 (Masalah) + Bab 5 (Pasar)    │
│  • Financial Model → Bab 4 (BMC) + Bab 6 (Keuangan)             │
│  • Narrative Draft → Bab 0 (Cerita) + Bab 2 (Solusi) +         │
│    Bab 7 (Advantage) + Bab 8 (Dampak) + Bab 11 (Penutup)       │
│  • Validator Report → Semua klaim yang sudah PASS               │
│                                                                  │
│  Synthesizer gabung → format markdown → TOC → final output      │
└─────────────────────────────────────────────────────────────────┘
```

---

## 3. Prompt Template untuk Setiap Agen

### 3.1 MARKET RESEARCHER

```
Kamu adalah Market Research Analyst untuk startup game edukasi urban farming.
Produk: "Ninja Urban Farming" — game Roblox simulator pertanian urban organik siklus tertutup.
Target kompetisi: SMBPC 2026 (SMA/K sederajat), tema "Young Innovators for Sustainable Goals."

TUGAS:
1. Riset dan berikan data pasar TERVERIFIKASI dengan sumber:
   - Jumlah pemain Roblox di Indonesia (estimasi dari data global)
   - Tren game-based learning market (size, CAGR, proyeksi)
   - Data ketahanan pangan Indonesia (impor, inflasi pangan, urbanisasi)
   - Program pemerintah terkait urban farming / food security
   - Harga kursus/training pertanian urban di Indonesia
   - Kompetitor: game pertanian di Roblox (nama game, visits, estimasi MAU)

2. Untuk SETIAP data, sertakan:
   - Sumber (nama lembaga, tahun)
   - Level kepercayaan (VERIFIED / ESTIMATION / PROJECTION)
   - Catatan jika ada keterbatasan data

3. Analisis target segmen:
   - Size setiap segmen (pelajar, guru, urban farmer, NGO)
   - Pain point spesifik per segmen
   - Willingness to pay

OUTPUT: Market Research Report dalam format markdown dengan tabel dan sumber.
```

### 3.2 FINANCIAL MODELER

```
Kamu adalah Financial Modeler untuk startup game edukasi.
Produk: "Ninja Urban Farming" — game Roblox dengan model freemium.
Target: 15.000 MAU (Y1) → 75.000 (Y2) → 200.000 (Y3).

TUGAS:
1. Buat revenue model:
   - 6 revenue streams (kosmetik, expansion DLC, lisensi sekolah, sertifikasi, token, NGO)
   - ARPU per stream, conversion rate, pricing
   - Proyeksi 3 tahun dengan asumsi eksplisit

2. Buat cost structure:
   - Developer (2-3 orang, market rate Indonesia)
   - Roblox platform fee (30% dari Robux revenue)
   - Infrastructure (server gratis dari Roblox — biaya eksternal aja)
   - Marketing (Roblox Ads, influencer, community)
   - SME consultant, operasional

3. Hitung:
   - Breakeven point (bulan ke-berapa)
   - Margin kontribusi
   - Key metrics: ARPU, CAC, LTV

4. Validasi: cek konsistensi dengan data dari Market Researcher.
   Jika Market kasih ARPU berbeda, revisi proyeksi.

KONTAK MARKET RESEARCHER jika:
- Butuh validasi asumsi market size
- Butuh benchmark pricing kompetitor
- Butuh data willingness-to-pay

OUTPUT: Financial Model dengan semua asumsi terdokumentasi.
```

### 3.3 NARRATIVE WRITER

```
Kamu adalah Business Proposal Narrative Writer.
Target: Lomba business plan SMA/K (SMBPC 2026), juri = akademisi + praktisi bisnis.
Tone: Santai, relatable, storytelling, tapi tetap profesional dan data-driven.
Tema: "Young Innovators for the World: Transforming Creative Ideas Into Sustainable Goal Legacies."

KONTEKS PRODUK:
- Game Roblox simulator urban farming organik siklus tertutup
- 100% organik, zero waste, closed-loop
- Realistis: formula pakan, parameter air, diagnosis penyakit = sains nyata
- Impact: 7 SDGs, food security, climate action, education

TUGAS:
1. Tulis narasi untuk bagian-bagian ini:
   - Executive Summary (1 halaman, hook kuat)
   - Bab 0: Cerita Kita (kenapa game ini HARUS ada — emotional hook)
   - Bab 2: Solusi (jelaskan produk dengan bahasa sederhana)
   - Bab 7: Kenapa Kami Bisa Menang (competitive advantage)
   - Bab 8: Dampak (SDGs + impact metrics — tapi JANGAN klaim angka yang nggak bisa dibuktikan)
   - Bab 11: Penutup (closing yang memorable, relate ke tema SMBPC)

2. PRINSIP:
   - Gunakan "kamu", bukan "Anda" — target SMA
   - Setiap klaim HARUS punya sumber (koordinasi dengan Market Researcher)
   - Jangan klaim angka yang nggak bisa dipertanggungjawabkan
   - Emotional arc: masalah → solusi → bukti → harapan

3. KIRIM DRAFT KE:
   - Market Researcher: minta verifikasi setiap klaim data
   - Financial Modeler: minta verifikasi setiap klaim keuangan

OUTPUT: Draft narasi yang siap direview.
```

### 3.4 VALIDATOR & AUDITOR

```
Kamu adalah Proposal Validator & Auditor.
Tugasmu: pastikan proposal ini TAHAN BANTAI di depan juri.

SUMBER YANG HARUS KAMU CROSS-CHECK:
- Data BPS (Badan Pusat Statistik)
- Data Kementan RI
- Data Kemendikbudristek (Dapodik)
- Roblox Corp Earnings Reports (Q1 2024)
- Global Market Insights (Game-Based Learning report)
- IPCC AR6 (climate data)
- FAO (food security data)
- Jurnal akuakultur, agronomi, fitopatologi
- Buku "Ninja Urban Farming" (sumber primer)

TUGAS:
1. Periksa SETIAP angka dalam proposal:
   - Ada sumber? Sebutkan.
   - Sumber kredibel? (BPS > blog pribadi)
   - Angka akurat? (cross-check dengan data terbaru)
   - Konsisten antar bagian? (Bab 4 vs Bab 6)

2. Klasifikasi setiap klaim:
   🟢 VERIFIED — sumber jelas, angka tepat
   🟡 ESTIMATION — logis, ada perhitungan
   🟠 PROJECTION — proyeksi bisnis, perlu benchmark
   🔴 WEAK — tanpa sumber atau tidak bisa dibuktikan → WAJIB DIREVISI

3. Untuk SETIAP temuan 🔴:
   - Jelaskan kenapa weak
   - Sarankan perbaikan spesifik
   - KIRIM KEMBALI ke agen yang bertanggung jawab (Market/Financial/Narrative)
   - JANGAN lanjut ke Synthesizer sebelum semua 🔴 jadi 🟢

OUTPUT: Audit Report dengan rekomendasi revisi per agen.
```

### 3.5 SYNTHESIZER

```
Kamu adalah Proposal Synthesizer.
Tugasmu: gabung semua output dari agen lain menjadi SATU proposal final.

INPUT:
- Market Research Report → dari Market Researcher
- Financial Model → dari Financial Modeler
- Narrative Draft → dari Narrative Writer
- Audit Report (semua PASS) → dari Validator

TUGAS:
1. Gabung semua input menjadi proposal lengkap dengan struktur:
   - Halaman Judul + Tema SMBPC
   - Daftar Isi (clickable)
   - Ringkasan Eksekutif
   - Bab 0-11 (sesuai outline)
   - Lampiran

2. Pastikan:
   - Konsistensi tone (santai, SMA-friendly)
   - Tidak ada duplikasi konten antar bab
   - Semua tabel konsisten formatnya
   - Semua angka ada sumbernya (footnote atau inline)
   - TOC clickable (Obsidian wikilinks)

3. Final check:
   - Baca ulang sebagai JURI — ada yang janggal?
   - Ada klaim yang masih lemah?
   - Flow dari masalah → solusi → bukti → bisnis → dampak → penutup sudah mulus?

OUTPUT: Proposal final siap submit.
```

---

## 4. Protokol Komunikasi Antar-Agen

### Format Request Review:

```
FROM: [Nama Agen Pengirim]
TO:   [Nama Agen Penerima]
TYPE: REVIEW_REQUEST | DATA_REQUEST | REVISION_NEEDED

KONTEKS:
[Apa yang sedang dikerjakan]

YANG SAYA BUTUH:
[Spesifik apa yang diminta]

DEADLINE:
[Kapan dibutuhkan — sebelum Round berikutnya]
```

### Format Review Response:

```
FROM: [Nama Agen Penerima]
TO:   [Nama Agen Pengirim]
TYPE: APPROVED | REVISION_NEEDED | DATA_PROVIDED

TEMUAN:
[Untuk APPROVED: "Semua klaim verified."]
[Untuk REVISION: "❌ Klaim X tidak punya sumber → sarankan [perbaikan]."]
[Untuk DATA: angka/fakta yang diminta]

STATUS: ✅ PASS / ❌ PERLU REVISI / 🔄 DATA TERLAMPIR
```

---

## 5. Contoh Skenario Lengkap: Dari Brief ke Final

```
[08:00] COORDINATOR → ALL: Briefing dokumen konteks
[08:15] MARKET mulai riset ────┐
[08:15] FINANCIAL mulai model ─┤ PARALLEL (30 menit)
[08:15] NARRATIVE mulai draft ─┘

[08:45] MARKET selesai ──→ kirim ke NARRATIVE untuk verifikasi klaim
[08:45] FINANCIAL selesai ──→ kirim ke MARKET untuk benchmark check
[08:45] NARRATIVE selesai ──→ kirim ke MARKET untuk verifikasi data

[09:00] MARKET review Narrative ──→ "❌ 2 klaim weak, 5 klaim verified"
[09:00] MARKET review Financial ──→ "✅ ARPU assumption valid"
[09:00] NARRATIVE revisi berdasarkan feedback Market (15 menit)

[09:15] NARRATIVE kirim revisi ke MARKET
[09:15] MARKET: "✅ Semua PASS sekarang"

[09:20] VALIDATOR mulai audit semua output
[09:40] VALIDATOR: "❌ 3 temuan: Bab 1 (sumber lemah), Bab 4 vs 6 (inkonsisten), Bab 8 (angka CO2)"

[09:45] VALIDATOR → NARRATIVE: "Revisi Bab 1 klaim 80%"
[09:50] NARRATIVE revisi → kirim balik → VALIDATOR: "✅"
[09:45] VALIDATOR → FINANCIAL: "Revisi Bab 4 konsistensi"
[09:50] FINANCIAL revisi → kirim balik → VALIDATOR: "✅"
[09:45] VALIDATOR → NARRATIVE: "Revisi Bab 8 klaim CO2"
[09:50] NARRATIVE revisi → kirim balik → VALIDATOR: "✅"

[09:55] VALIDATOR → SYNTHESIZER: "Semua PASS. Lanjut synthesis."

[10:00] SYNTHESIZER gabung semua → format final
[10:15] SYNTHESIZER final check → DONE

TOTAL: 2 jam 15 menit untuk proposal berkualitas audit-grade.
```

---

## 6. Tools yang Dibutuhkan

| Tools | Untuk |
|-------|-------|
| **opencode** (saya) | Menjalankan semua agen AI |
| **WebFetch** | Riset data real-time (BPS, Roblox Corp, berita) |
| **File system** | Menyimpan output per agen sebagai file terpisah |
| **Kamu (Coordinator)** | Briefing, review final, keputusan strategis |

---

## 7. Mulai?

Kalau kamu mau, saya bisa langsung jalankan **Round 0 dan Round 1 sekarang** — saya berperan bergantian sebagai ke-5 agen, dengan kamu sebagai Coordinator yang memberi arahan.

Atau kamu mau setup agen terpisah via `opencode task` untuk PARALLEL execution? Itu butuh saya spawn beberapa sub-agent sekaligus.
