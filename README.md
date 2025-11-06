# Eksperimen_SML_Satriana
Eksperimen Sistem Machine Learning-Preprocessing Dataset

Deskripsi Proyek:
Repository ini berisikan proyek Eksperimen Machine Learning.
proyek ini berfokus pada otomatisasi proses preprocessing data menggunakan Python dan integrasi workflow otomatis dengan Github Actions

Dataset yang digunakan adalah Students Performances in Exams, yang berisikan informasi mengenai nilai ujian untuk tiga mata pelajaran serta faktor-faktor demografis dan sosial yang dapat memengaruhi performa mereka dalam melaksanakan ujian

Adapun Tujuan Proyek ini:
1. Melakukan eksperimen preprocessing data untuk menyiapkan dataset agar siap digunakan pada model Machine Learning
2. mengonversi hasl eksperimen preprocessing ke dalam script Python otomatis (automate_Satriana.py)
3. Membuat workflow otomatis dengan Github Actions agar preprocessing dapat berjalan otomatis setiap kali ada perubahan di branch main

Struktur Folder:

Eksperimen_SML_Satriana                                                                                                                                                                      
├── .github/

│   └── workflows/

│       └── preprocess.yml          # Workflow GitHub Actions

│

├── studentsperformance_raw/        # Dataset mentah (raw dataset)

│   └── StudentsPerformance.csv

│

├── preprocessing/

│   ├── Eksperimen_Satriana.ipynb   # Eksperimen preprocessing awal (Jupyter Notebook)

│   ├── automate_Satriana.py        # Script otomatis untuk preprocessing

│   └── studentsperformance_preprocessing/

│       └── StudentsPerformance_preprocessing.csv   # Hasil preprocessing (otomatis dihasilkan)

│

├── requirements.txt                # Daftar dependencies yang digunakan

└── README.md                       # Dokumentasi proyek


Tahapan Preprocessing:
Scrips pada fioe automate_Satriana.py akan secara otomatis menjalankan tahapan-tahapan:
Tahapan preprocessing yang dilakukan:
  1. Membaca data dari file CSV.
  2. Menangani missing value.
  3. Menghapus data duplikat
  4. Deteksi dan penanganan outlier
  5. Melakukan normalisasi data menggunakan StandardScaler.
  6. Membuat kolom rata-rata (average score)
  7. Melakukan encoding pada kolom kategorical.
  8. Binning (pengelompokkan data)
  9. Split dataset menjadi data train dan test.
  10. Simpan hasil preprocessing ke dalam file CSV.
preprocessing/studentsperformance_preprocessing/StudentsPerformance_preprocessing.csv

Automatisasi Workflow (Github Actions)
untuk file workflow terletak di
.github/workflows/preprocessing.yml

Alur workflow:
1. Checkout repository : mengambil seluruh isi repository
2. Set up Python : menggunakan python versi 3.12.7
3. Install dependencies : menginstal semua library pada requerements.txt
4. Menjalankan Script : automate_Satriana.py
5. Upload hasil preprocessing ke github sebagai artifact
6. Commit and Push otomatis hasil dataset baru ke repository

Hasil Akhir:
1. File .ipynb: proses eksplorasi dan eksperimen awal
2. File .py: hasil dari konversi otomatis preprocessing
3. File .yml: menunjukkan workflow otomatis Github Actions
