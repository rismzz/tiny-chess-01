# STATUS — tiny-chess-01 (belum disubmit)

Syarat (2026-11-16): main.py ≤4.096 B, repo ≤8.192 B, file ≤4.096 B; Python 3.13 stdlib; model call = DQ; main.py mandiri (tak membaca file repo lain). Protokol HTTP POST JSON ke MAKEFUN_ENV_URL: /game {} → status; /move {"game":n,"move":"e2e4"}. Trial 8 game vs engine rumah deterministik, opening buku 8 ply; langkah ≤10.000 ms; trial ≤1.800 dtk; skor Elo ML vs jangkar, lantai latihan 1.154; replay penantang byte-identik → search node-tetap. Akhir: mat/stalemate/materi kurang/3× ulang/100 ply/adjudikasi 200 ply (≥5 menang). Crash = kalah game berjalan + sisa. $500/20 tempat, gratis, tutup 2026-11-24T17:00:00Z, maks 5 submit/hari, 10 total.

Engine original: papan 0x88; negamax alpha-beta + PVS + LMR + null-move + TT; quiescence menyatu (tangkapan+promosi, evasi penuh saat skak); eval material 100/320/330/500/900 + PST digit-string + raja tapered MG/EG, inkremental; budget 50.000 node. Driver retry + fallback langkah legal (anti-abandon). main.py = blob lzma+base85 dari source 7.249 B (di-minify); source di scratch-tiny-chess/engine_src.py. Jangan re-pack main.py ini (double-pack 4.405 B).

Uji (mock + wasit penuh, build final): test_engine ALL OK — perft 20/400/8902, Kiwipete 48/2039/97862, suite 14/191/2812 & 6/264/9467; konsistensi hash/eval ✓; mate-in-1 ✓. Match: greedy 1/1, AB depth-2 3/3, AB depth-3 2/2 (semua skakmat); pra-golf 16/16. 0 ilegal, 0 crash, exit 0; maks 2,25 dtk, rerata ~1,4 dtk. Determinisme: 2 run identik persis ✓.

Ukuran: main.py 4.070, LICENSE 1.108, README 1.041, owner.json 57, STATUS ini; total <8.192 B.

Sisa submit: (1) repo GitHub publik dibuat >2026-11-10T17:00:00Z (CLI belum login) + commit SHA-40; ganti OWNER/REPO di README; About repo. (2) Recording kit (record dulu) + bundle transkrip + makefun-run.json. (3) Submit via API; klaim ke wallet di owner.json.
