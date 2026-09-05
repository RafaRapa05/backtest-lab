# XAUUSD Backtest Lab

Konsol backtest strategi XAUUSD berasaskan pelayar. Muat naik data harga
sejarah dari MT5, uji strategi, dan lihat kurva ekuiti serta statistiknya —
tanpa perlu membuka MetaTrader.

**Laman langsung:** https://rafarapa05.github.io/backtest-lab/

## Cara guna

1. Eksport data harga dari MT5 sebagai CSV/TSV (format `DATE, TIME, OPEN,
   HIGH, LOW, CLOSE`). Format ringkas `Date, Open, High, Low, Close` juga
   diterima.
2. Muat naik fail itu — seret ke kotak muat naik atau klik untuk pilih.
3. Pilih strategi dan laraskan parameternya.
4. Klik **Jalankan Backtest**.

Timeframe M1 hingga MN1 disokong. Fail sebesar ~250,000 bar (data M1 satu
tahun) diproses dalam masa lebih kurang sesaat.

## Strategi tersedia

| Strategi | Isyarat |
|---|---|
| MA Cross | MA cepat memotong MA lambat (SMA atau EMA) |
| RSI | Masuk long bila oversold, short bila overbought |
| Bollinger | Harga menembusi jalur atas atau bawah |

Setiap strategi boleh diatur arah posisi (long sahaja / short sahaja /
kedua-duanya), stop loss, take profit, saiz lot, saiz kontrak, modal awal,
dan kos spread.

## Data anda kekal milik anda

Fail CSV yang dimuat naik **tidak pernah dihantar ke mana-mana pelayan**.
Semuanya diproses dalam pelayar dan disimpan secara setempat menggunakan
IndexedDB, jadi data kekal ada selepas tab ditutup — tetapi hanya pada
peranti itu sahaja.

## Had yang perlu diketahui

Enjin backtest ini **simulasi ringkas, bukan MT5 Strategy Tester**:

- Kemasukan dan keluar dinilai pada harga close setiap bar.
- SL/TP disemak menggunakan high/low bar yang sama, tanpa jejak harga
  dalam bar. Jika kedua-duanya dicapai dalam satu bar, SL diutamakan.
- Kos spread dikenakan sebagai jumlah tetap setiap dagangan. Tiada swap,
  komisen, slippage, atau permintaan margin.
- Simulasi berhenti apabila modal habis (stop out).

Gunakan ia untuk menapis idea strategi dengan pantas. Sahkan keputusan
akhir dalam MT5 Strategy Tester sebelum guna pada akaun sebenar.

## Menjalankan secara setempat

Muat turun `index.html` dan buka terus dalam pelayar. Ia satu fail tunggal
tanpa kebergantungan dan berfungsi tanpa sambungan internet.
