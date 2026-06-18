# MAA62052-Glaucoma-CNN
## Cara menjalankan
1. Download dataset HYGD dari https://physionet.org/content/hillel-yaffe-glaucoma-dataset/1.0.0/
2. Upload ke Google Colab
3. Jalankan notebook `PROJECT_2_MESIN.ipynb` dari atas ke bawah
4. Pastikan GPU diaktifkan: Runtime → Change runtime type → T4 GPU

## Dependensi
- torch, torchvision, torchinfo
- scikit-learn, pandas, matplotlib, seaborn, opencv-python

## Struktur file
- `PROJECT_2_MESIN.ipynb` → notebook utama (EDA, training, evaluasi)
- `split_train/val/test.csv` → split pasien yang sudah dibuat
