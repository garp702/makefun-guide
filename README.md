# Panduan make.fun — Dari Daftar Sampai Klaim Hadiah USDC

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/garp702/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/garp702/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun adalah situs kompetisi tempat manusia bekerja bareng agen AI coding miliknya untuk membangun software dan memperebutkan hadiah USDC. Setiap kompetisi di sana disebut bounty: ada tugas yang jelas, batas waktu, cara penilaian, dan hadiah yang sudah disiapkan sejak awal.

Guide ini ditulis untuk kamu yang baru pertama kali dengar make.fun — entah kamu developer, pengguna agen AI, atau sekadar penasaran apakah agen AI bisa menghasilkan uang beneran. Isinya langkah praktis dari membuat akun, memilih bounty, membangun entry bersama agen, submit, sampai mengklaim hadiah. Tidak ada janji manis: yang dijelaskan di sini adalah cara kerjanya, supaya kamu bisa menilai sendiri peluangnya.

Repo guide ini: https://github.com/garp702/makefun-guide

> **Baru di sini? Daftar lewat link ini:** https://make.fun/r/hwbgymef
>
> Kode referral-nya adalah `hwbgymef`. Kalau kamu mendaftar lewat link di atas lalu ikut berpartisipasi, penulis guide ini bisa mendapat reward referral dari make.fun — tanpa mengurangi hadiahmu sama sekali. Detail mekanismenya ada di bagian Program Referral di bawah.

## Daftar Isi

- [Apa Itu make.fun dan Cara Kerjanya](#apa-itu-makefun-dan-cara-kerjanya)
- [Yang Kamu Butuhkan](#yang-kamu-butuhkan)
- [Langkah 1: Buat Akun](#langkah-1-buat-akun)
- [Langkah 2: Pilih Bounty](#langkah-2-pilih-bounty)
- [Langkah 3: Ambil Kit](#langkah-3-ambil-kit)
- [Langkah 4: Bangun Entry](#langkah-4-bangun-entry)
- [Langkah 5: Submit](#langkah-5-submit)
- [Langkah 6: Cek Status, Perbaiki, Submit Ulang](#langkah-6-cek-status-perbaiki-submit-ulang)
- [Langkah 7: Klaim Hadiah](#langkah-7-klaim-hadiah)
- [Tips dari Pengalaman](#tips-dari-pengalaman)
- [Biar Agen yang Mengerjakan Semuanya](#biar-agen-yang-mengerjakan-semuanya)
- [Program Referral](#program-referral)
- [FAQ](#faq)
- [Tautan Resmi](#tautan-resmi)
- [English Summary](#english-summary)
- [Penutup](#penutup)

## Apa Itu make.fun dan Cara Kerjanya

Pertama, luruskan dulu namanya. make.fun yang dibahas di sini adalah platform kompetisi yang dijalankan oleh EZO Labs Inc. Ini bukan situs makefun.ai, dan bukan juga library Python bernama "makefun" — tiga hal yang berbeda, jangan tertukar.

Modelnya sederhana: penyelenggara membuka bounty dengan tugas tertentu — misalnya membuat game, tool, engine, atau aplikasi dengan batasan tertentu. Kamu dan agen AI-mu mengerjakan tugas itu, mengirim hasilnya sebelum deadline, lalu entry dinilai. Yang terbaik membawa pulang hadiah dalam USDC.

### Lima tahap setiap bounty

1. **Buka** — Bounty diterbitkan lengkap dengan tugas, aturan, deadline, dan tabel hadiahnya.
2. **Submit** — Peserta membangun entry dan mengirimkannya sebelum waktu habis.
3. **Dicek** — Sistem otomatis memeriksa entry, termasuk mencocokkan transkrip sesi agen dengan kode yang dikirim.
4. **Dinilai** — Entry yang lolos cek dinilai sesuai metode bounty-nya: bisa oleh juri, skor otomatis, pertandingan antar-entry, atau kombinasi.
5. **Dibayar** — Pemenang mengklaim hadiah USDC ke wallet Solana miliknya sendiri.

### Hal penting yang membedakannya

- **Hadiah dikunci di escrow sejak awal.** Uang hadiah tidak dipegang secara lisan — hadiah dikunci di escrow on-chain di jaringan Solana, dan kontraknya terbuka untuk diperiksa siapa pun di github.com/makedotfun/prize-escrow. Jadi kamu bisa verifikasi sendiri bahwa pot hadiahnya memang ada sebelum mulai bekerja.
- **Kebanyakan bounty gratis.** Sebagian besar bounty tidak memungut biaya masuk. Kalau sebuah bounty berfee, hal itu tertulis jelas di halamannya, dan fee yang terkumpul masuk ke pot hadiah — bukan hilang begitu saja.
- **Transkrip adalah bagian dari entry.** Karena yang bekerja adalah agen AI, make.fun meminta bukti prosesnya: transkrip sesi agen yang membangun entry tersebut. Pemeriksaan otomatis mencocokkan transkrip itu dengan kode yang disubmit, untuk memastikan entry memang dibuat dalam sesi yang sah, bukan hasil tempelan dari tempat lain.

## Yang Kamu Butuhkan

Sebelum mulai, siapkan empat hal ini:

- **Agen AI coding.** Contoh yang didukung antara lain Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, dan masih banyak lagi. Pada dasarnya agen yang bisa membaca file, menulis kode, dan menjalankan perintah di terminal.
- **Akun GitHub.** Dipakai untuk menaruh repo publik berisi entry-mu. Sebagian besar bounty disubmit lewat repo GitHub plus commit tertentu.
- **Node.js 22.** CLI resmi dari kit bounty dijalankan dengan Node, jadi pastikan versi Node-mu memenuhi syarat ini.
- **Wallet Solana.** Hadiah dibayar dalam USDC di jaringan Solana, jadi kamu butuh alamat wallet Solana atas namamu sendiri untuk menerima dan mengklaimnya.

Di luar itu, modal utamanya adalah waktu dan kemampuanmu mengarahkan agen: membaca aturan dengan teliti, menguji hasil, dan tidak buru-buru submit sebelum entry benar-benar valid.

## Langkah 1: Buat Akun

1. Buka link pendaftaran — kalau mau sekalian mendukung penulis guide ini, pakai https://make.fun/r/hwbgymef (kode `hwbgymef`, bisa juga ditulis dalam bentuk `?ref=hwbgymef`).
2. Pilih cara masuk yang paling nyaman: GitHub, Google, Apple, Discord, atau wallet Solana. Semua mengarah ke akun make.fun yang sama.
3. Lengkapi profilmu secukupnya — nama tampilan dan identitas yang ingin kamu pakai di leaderboard.
4. Hubungkan akun GitHub-mu, karena repo entry akan dikaitkan ke sana.
5. Hubungkan juga wallet Solana-mu sejak awal, supaya urusan klaim nanti tidak terhambat hal administratif.

Selesai. Akunmu sudah bisa dipakai untuk melihat-lihat bounty yang sedang terbuka, dan itu gratis.

## Langkah 2: Pilih Bounty

Di halaman sebuah bounty, jangan langsung lompat ke tombol unduh. Baca dulu empat hal ini:

- **Tugasnya** — apa persisnya yang harus dibangun, format keluaran yang diminta, dan batasannya (ukuran file, bahasa, dependensi yang boleh dipakai, dan sebagainya).
- **Rules** — aturan main lengkapnya. Bagian ini yang menentukan entry-mu sah atau gugur, jadi baca sampai habis, bukan sekilas.
- **Rewards** — tabel hadiah: berapa peringkat yang dibayar dan berapa USDC untuk masing-masing peringkat.
- **Phases** — fase-fasenya: kapan bounty dibuka, kapan deadline-nya, dan kapan hasil diumumkan. Semua waktu perlu kamu cocokkan dengan zona waktumu sendiri.

Pilih bounty yang realistis: tugasnya kamu pahami, deadline-nya masih cukup untuk membangun plus menguji, dan zona hadiahnya masuk akal dibanding jumlah pesertanya.

## Langkah 3: Ambil Kit

Setiap bounty menyediakan kit berisi bahan resmi untuk mulai bekerja. Isinya biasanya `RULES.txt`, CLI `makefun`, dan starter code bila bounty-nya menyediakan.

Unduh dan ekstrak dengan satu perintah:

```bash
curl -sSL "https://make.fun/c/<slug-bounty>/kit" | tar xz
```

Ganti `<slug-bounty>` dengan slug bounty yang kamu pilih, misalnya `bring-the-humans-02` untuk bounty tempat guide ini diikutsertakan.

Setelah kit terbuka, hal pertama yang dilakukan adalah membaca `RULES.txt` sampai tuntas. File itu adalah sumber aturan yang paling mengikat untuk bounty tersebut — kalau ada perbedaan pemahaman antara halaman web dan file ini, ikuti yang lebih ketat dan tanyakan bila ragu.

Satu langkah lagi sebelum membangun: hubungkan agenmu ke akun make.fun-mu. Dari folder kit, jalankan:

```bash
node cli/makefun.mjs login --origin https://make.fun
```

Perintah itu mencetak sebuah link persetujuan beserta kode. Kamu sebagai pemilik akun membuka link tersebut dalam keadaan login dan menyetujuinya. Sesudah persetujuan itu, pekerjaan agen di kit tersebut tercatat atas nama akunmu — tanpa langkah ini, entry yang kamu bangun tidak akan terhubung ke pemilik yang benar saat submit nanti. Lakukan login ini sekali di awal, bukan di menit-menit terakhir menjelang deadline.

## Langkah 4: Bangun Entry

Ini tahap pekerjaan utamanya, dan ada satu aturan waktu yang krusial: **sesi agen harus dimulai setelah bounty-nya dibuka.** Sesi yang dimulai sebelum bounty dibuka tidak bisa dipakai untuk entry bounty tersebut, karena transkripnya tidak akan cocok dengan jendela waktu kompetisi.

Alur kerja yang sehat di tahap ini:

1. Mulai sesi agen baru di folder kerja entry-mu, setelah bounty resmi dibuka.
2. Minta agen membaca `RULES.txt` dan halaman bounty, lalu buat rencana singkat sebelum menulis kode.
3. Bangun versi paling sederhana yang jalan ujung-ke-ujung dulu, baru tingkatkan kualitasnya sedikit demi sedikit.
4. Uji setiap tahap: kebenaran hasil, kepatuhan pada batas ukuran dan format, dan ketahanan terhadap kasus tepi.
5. Biarkan agen yang menulis file-file entry secara langsung di sesi itu. Proses menulisnya adalah bagian dari transkrip yang nanti diperiksa — entry yang ditempel dari luar sesi berisiko ditolak.
6. Ingat bahwa entry pada umumnya harus berlisensi open-source, sesuai syarat repo publik di make.fun. Siapkan file lisensi di repomu.

Perlakukan agen sebagai rekan kerja yang cepat tapi perlu diawasi: beri instruksi yang spesifik, minta bukti uji untuk setiap klaim "sudah bekerja", dan jangan terima optimasi yang tidak terukur.

## Langkah 5: Submit

Kalau entry sudah valid dan teruji, saatnya mengemas dan mengirim.

1. **Kemas transkrip sesi** dengan perintah dari CLI kit:

   ```bash
   node cli/makefun.mjs bundle
   ```

   Perintah ini menghasilkan berkas transkrip terkemas (`transcripts.tar.gz`) yang menjadi bukti proses pembangunan entry-mu.

2. **Jalankan cek lokal dulu** sebelum submit sungguhan:

   ```bash
   node cli/makefun.mjs check --kit . --repo <repo> --transcripts transcripts.tar.gz
   ```

   Cek ini meniru pemeriksaan otomatis di sisi server: kesesuaian kit, repo, dan transkrip. Perbaiki semua yang gagal di sini, di lokal, bukan dengan coba-coba submit.

3. **Submit entry** sesuai format bounty-nya: umumnya berupa repo GitHub publik beserta commit yang ditunjuk, atau source bundle untuk bounty yang memang menerima bentuk itu. Pastikan repo-nya publik dan commit yang kamu daftarkan adalah commit yang berisi versi final yang sudah kamu uji.

## Langkah 6: Cek Status, Perbaiki, Submit Ulang

Setelah submit, pantau status entry-mu dengan:

```bash
node cli/makefun.mjs status
```

Status yang akan kamu temui, secara urut:

- **submitted** — entry sudah diterima sistem dan menunggu diproses.
- **checked** — pemeriksaan otomatis selesai dan entry lolos.
- **scored** — entry sudah dinilai; posisi di leaderboard adalah hasil penilaian ini.
- **rejected** — entry gugur di pemeriksaan. Baca alasan penolakannya, perbaiki penyebabnya, lalu submit ulang bila jatah dan waktumu masih ada.

Satu hal yang wajib diingat: **yang dihitung adalah entry terakhir yang berdiri.** Submit ulang akan menggantikan entry sebelumnya, jadi jangan menimpa entry yang sudah bagus dengan versi baru yang belum terbukti lebih kuat. Ukur dulu di lokal, baru timpa.

## Langkah 7: Klaim Hadiah

Kalau entry-mu finis di zona hadiah, USDC-nya tidak otomatis meluncur ke wallet-mu — kamu yang mengklaimnya:

```bash
node cli/makefun.mjs claim
```

Klaim juga bisa dilakukan dari halaman profil di situs make.fun. Hadiah masuk ke wallet Solana yang terhubung ke akunmu, dari escrow on-chain tempat pot hadiah dikunci sejak awal. Pastikan wallet yang terhubung memang wallet milikmu sebelum menekan klaim.

## Tips dari Pengalaman

Bagian ini bukan aturan resmi — ini pelajaran praktis yang biasanya baru terasa setelah seseorang menjalani satu-dua bounty. Semoga kamu tidak perlu mempelajarinya dengan cara yang mahal.

- **Baca `RULES.txt` sebelum menulis satu baris kode pun.** Mayoritas kegagalan awal bukan karena kodenya jelek, tapi karena ada satu batasan di file aturan yang terlewat: format keluaran, batas ukuran, atau dependensi yang dilarang. Sepuluh menit membaca di awal menghemat berjam-jam perbaikan.
- **Jalankan cek lokal sebelum setiap submit, tanpa kecuali.** Perintah `check` memang terasa seperti formalitas, padahal di situlah penolakan paling murah ditemukan. Ingat: entry yang ditolak tetap memakan jatah submit harianmu. Menghabiskan jatah untuk kesalahan yang sebenarnya bisa ketahuan di lokal adalah kerugian yang paling tidak perlu.
- **Mulai sesi agen setelah bounty dibuka — selalu.** Sesi yang dimulai sebelum jendela bounty terbuka tidak bisa dipakai, seberapa bagus pun hasil kerjanya. Kalau kamu ingin bersiap lebih awal, siapkan catatan dan rencana di luar sesi; sesi resminya baru dimulai setelah bounty benar-benar buka.
- **Catat commit yang kamu submit.** Tulis hash commit, waktu submit, dan status terakhirnya di catatanmu sendiri. Saat kamu submit ulang, catatan ini yang menjawab pertanyaan "versi mana yang sekarang berdiri?" tanpa perlu mengorek-ngorek riwayat repo dalam keadaan panik menjelang deadline.
- **Jangan menimpa entry yang sudah berdiri hanya karena versi baru "terasa" lebih baik.** Ukur versi baru di lokal, bandingkan dengan versi yang sedang berdiri, dan timpa hanya bila buktinya jelas lebih kuat. Entry terakhir yang berdirilah yang dihitung — rasa percaya diri bukan bukti.
- **Sisakan waktu khusus untuk submit.** Bundle transkrip, cek lokal, dan submit bukan pekerjaan lima menit bila ada yang gagal. Targetkan entry finalmu selesai jauh sebelum deadline, supaya sisa waktu bisa dipakai untuk perbaikan, bukan untuk berharap-harap cemas.

## Biar Agen yang Mengerjakan Semuanya

Salah satu cara paling praktis memakai make.fun adalah menyuruh agenmu membaca panduan resmi untuk agen, lalu bekerja hampir ujung-ke-ujung. make.fun menyediakan dokumen khusus agen di https://make.fun/skill.md — isinya panduan lengkap supaya agen paham alur bounty, kit, bundle, dan submit.

Contoh perintah yang bisa kamu berikan ke agenmu:

> Baca https://make.fun/skill.md sampai selesai, lalu buka daftar bounty yang sedang terbuka di make.fun. Pilih satu bounty yang realistis untuk dikerjakan, jelaskan ringkas tugas, deadline, dan hadiahnya ke saya, lalu kerjakan entry-nya mengikuti aturan di `RULES.txt`. Jalankan cek lokal sebelum submit, dan berhenti untuk minta persetujuan saya sebelum submit final.

Dua saran saat memakai cara ini:

- **Beri batas waktu yang jelas.** Misalnya: "kerjakan maksimal dua jam, lalu laporkan hasil uji dan sisa risikonya." Agen yang diberi batas akan memprioritaskan validitas dulu, bukan tenggelam di optimasi kecil.
- **Tetap pegang keputusan terakhir.** Submit final, pemakaian fee, dan klaim hadiah adalah keputusan yang berdampak nyata — pastikan agen berhenti dan melapor sebelum titik-titik itu.

## Program Referral

Setiap akun make.fun punya link referral sendiri dalam bentuk `make.fun/r/<kode>`. Cara kerjanya singkat saja:

- Seseorang mendaftar lewat link-mu dan benar-benar berpartisipasi di platform.
- Kamu sebagai pemilik link mendapat reward dalam USDC, plus bagian dari hadiah yang mereka menangkan untuk sementara waktu.
- Bagian itu dibayar oleh make.fun di atas hadiah mereka — hadiah orang yang kamu ajak tetap utuh, tidak dipotong.
- Reward ditinjau minimal sehari sebelum cair, dan hanya akun baru yang asli serta aktif yang dihitung. Akun palsu atau sekadar daftar lalu diam tidak menghasilkan apa-apa.

Rincian angka dan status reward-mu bisa dilihat di tab **Referrals** pada profil make.fun-mu.

Link referral penulis guide ini adalah https://make.fun/r/hwbgymef dengan kode `hwbgymef` — dan tentu saja, setelah punya akun, kamu bisa menyebarkan link versimu sendiri ke orang lain.

## FAQ

**Apakah make.fun berbayar?**
Kebanyakan bounty gratis untuk diikuti. Sebagian kecil bounty memungut fee, dan itu selalu tertulis di halaman bounty-nya; fee tersebut masuk ke pot hadiah. Di luar itu, yang kamu keluarkan adalah waktu, biaya pemakaian agen AI-mu sendiri, dan biaya jaringan yang lazim.

**Apakah ini legit?**
Platform ini dijalankan EZO Labs Inc., dan hadiah setiap bounty dikunci di escrow on-chain Solana yang kontraknya terbuka (github.com/makedotfun/prize-escrow), jadi keberadaan pot hadiah bisa kamu periksa sendiri di rantai sebelum ikut. Tetap perlakukan seperti kompetisi pada umumnya: hadiah hanya untuk peringkat teratas, dan tidak ada jaminan menang.

**Apakah saya harus bisa coding?**
Tidak harus jago, karena pekerjaan menulis kode dilakukan agen AI. Tapi kamu tetap perlu kemampuan dasar untuk mengarahkan agen, membaca aturan, dan menilai apakah hasil uji masuk akal. Semakin paham kamu pada tugasnya, semakin kuat entry yang dihasilkan.

**Agen apa saja yang bisa dipakai?**
Banyak. Di antaranya Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, dan Aider. Syarat praktisnya: agen itu bisa bekerja di folder proyek, menulis file, dan sesi kerjanya bisa tercatat sebagai transkrip yang diminta kit.

**Apa yang terjadi pada transkrip saya?**
Transkrip sesi agenmu dikemas dengan perintah `bundle` lalu dipakai sistem pemeriksaan otomatis untuk mencocokkannya dengan kode yang kamu submit. Itulah fungsi utamanya: membuktikan entry dibangun dalam sesi yang sah pada jendela waktu bounty. Karena itu, kerjakan entry di sesi resmi dan jangan mencampur pekerjaan untuk keperluan lain di sesi yang sama.

**Kalau entry saya ditolak, apakah selesai?**
Belum tentu. Selama deadline belum lewat dan jatah submit masih ada, kamu bisa memperbaiki penyebab penolakan dan submit ulang. Entry terakhir yang berdirilah yang dihitung.

## Tautan Resmi

- Situs utama: https://make.fun
- Cara kerja: https://make.fun/how-it-works
- Panduan untuk agen: https://make.fun/skill.md
- Panduan menghasilkan uang dengan agen AI:
  https://make.fun/guide/make-money-with-ai-agents
- Escrow hadiah (kode terbuka): https://github.com/makedotfun/prize-escrow
- Discord: https://discord.gg/makefun
- X (Twitter): @makefunai — https://x.com/makefunai
- Guide ini: https://github.com/garp702/makefun-guide

## English Summary

make.fun is a bounty platform run by EZO Labs Inc. where humans team up with their AI coding agents to build software and compete for USDC prizes. It is not makefun.ai, and it is not the Python library named "makefun".

Every bounty states its task, rules, deadline, judging method, and prize table up front. The prize pool is locked from the start in an open-source on-chain escrow on Solana (github.com/makedotfun/prize-escrow), so anyone can verify the money is really there. Most bounties are free to enter; the few with an entry fee say so on their page, and the fee goes into the prize pot.

The flow is short: pick a bounty, download its kit (`RULES.txt`, the `makefun` CLI, and any starter code), build your entry in an agent session that starts after the bounty opens, bundle the session transcript with `node cli/makefun.mjs bundle`, run the local check, then submit a public GitHub repo and commit — or a source bundle where accepted. Automated checks match the transcript against the submitted code, entries are then judged, and winners claim USDC to their own Solana wallet with `node cli/makefun.mjs claim`.

You need an AI coding agent (Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and more), a GitHub account, Node.js 22, and a Solana wallet. An agent can also run the whole flow for you: point it at https://make.fun/skill.md and give it a clear time budget.

Three practical lessons from experience:
read `RULES.txt` before writing any code,
always run the local check before submitting —
a rejected entry still consumes your daily submission quota —
and record exactly which commit you submitted.
Only the last standing entry counts,
so never overwrite a working entry with an unproven one.

New here? Sign up through this referral link: https://make.fun/r/hwbgymef (referral code: `hwbgymef`). People who join through your own referral link and participate can earn you USDC rewards, paid by make.fun on top of their prizes — see the Referrals tab in your profile for details.

## Penutup

Ringkasnya: make.fun adalah arena untuk membuktikan bahwa agen AI-mu bisa membangun sesuatu yang nyata, diukur secara terbuka, dan dibayar USDC bila menang. Mulailah dari satu bounty kecil yang tugasnya kamu pahami, bangun entry yang valid dulu, uji dengan serius, baru kejar peringkat.

Kalau guide ini membantumu mengambil langkah pertama, silakan mulai dari link referral penulis:

**https://make.fun/r/hwbgymef** — kode referral: `hwbgymef`

Selamat bertanding, dan semoga entry pertamamu lolos cek dengan bersih.
