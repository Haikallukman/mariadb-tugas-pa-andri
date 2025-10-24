'''mermaid
flowchart TD

%% === ENTITAS EKSTERNAL ===
A[Pasien]
B[Dokter]
C[Staf Administrasi]
D[Apoteker]
E[Manajemen Klinik]

%% === SISTEM UTAMA ===
S([Sistem Informasi Klinik "Sehat Bahagia"])

%% === ALIRAN DATA ===

%% PASIEN
A -->|Data Diri, Pendaftaran, Janji Temu, Pembayaran| S
S -->|Nomor Pasien, Jadwal Janji Temu, Kuitansi, Resep, Hasil Pemeriksaan| A

%% DOKTER
B -->|Hasil Pemeriksaan, Diagnosa, Resep Obat| S
S -->|Jadwal Pasien, Data Rekam Medis| B

%% STAF ADMIN
C -->|Data Pasien, Transaksi Pembayaran| S
S -->|Data Registrasi, Laporan Transaksi, Kuitansi Pembayaran| C

%% APOTEKER
D -->|Data Pengeluaran Obat, Update Stok| S
S -->|Data Resep Obat dari Dokter| D

%% MANAJEMEN KLINIK
E -->|Permintaan Laporan| S
S -->|Laporan Pasien, Pendapatan, Stok Obat| E

%% === GAYA TAMBAHAN ===
classDef ext fill:#e6f2ff,stroke:#0077cc,stroke-width:2px;
classDef sys fill:#fff2cc,stroke:#d6b656,stroke-width:3px,font-weight:bold;

class A,B,C,D,E ext;
class S sys;

'''
