# STATUS — tiny-chess-01 round 3 (siap submit)

Syarat: main.py ≤4.096 B, tree ≤8.192 B, Python 3.13 stdlib, main.py mandiri (tak baca file repo lain). Trial vs gauntlet rumah; langkah ≤10.000 ms; trial ≤1.800 dtk; lantai practice 1.154; replay penantang byte-identik (search node-tetap, tanpa jam). Tutup 2026-11-24T17:00Z, maks 5 submit/hari, 10 total. $500/20 tempat.

Round 2 DITOLAK practice_floor: skor 1.099 < 1.154. Trial-0 lokal round 2: W2 D0 L4 = 2,0 poin (depth-2 W, depth-3 W, sisanya L).

Perubahan round 3 (ditulis di sesi ini ke engine_src.py, 10.057 B):
- Killer moves (2/ply) + history heuristic di move ordering.
- Bishop pair +30; PST pion: pion rank 7/6 bonus lebih besar.
- Anggaran node 50.000 → 80.000; killer/history direset tiap bm() agar deterministik.

Uji lokal (env asli kit, tanpa artefak):
- Perft eksak: startpos d3 8902, kiwipete d3 97862, pos3 2812, pos4 9467. Mate-in-1 ✓, determinisme 2 run identik ✓.
- Trial-0 round 3: W4 D1 L1 = 4,5 poin → Elo practice ~1.545 (lantai 1.154). depth-2 W, depth-3 W, depth-4 W, nodes-100k L, nodes-250k W, nodes-500k D (threefold).
- Trial-1 (validasi, instance lain): W5 D0 L1 = 5,0 poin → Elo ~1.654 (hanya kalah dari nodes-500k). Rerata 2 trial ~1.600.
- Mock match: 4-0 semua checkmate (greedy 2x, ab2 2x); 0 bad request; langkah maks 3,31 dtk, rerata 2,51 dtk.
- Ukuran: main.py 4.003 B (kit compress resmi, sha256 d3226d75…), tree ~7,6 kB.

Sisa submit (parent): commit main.py + STATUS ini (engine_src.py tetap uncommitted di folder repo); bundle transkrip sesi pembangun (builder r1/r2, fixer, improver ini, top-level); submit round 3 sebelum 2026-11-25 00:00 WIB.
