# Deteksi Kelengkapan Berkendara

## Deskripsi Proyek
Proyek ini bertujuan untuk mendeteksi kelengkapan berkendara yaitu helm, menggunakan teknologi deteksi objek berbasis model YOLOv8 dan ONNX. Proyek ini terdiri dari dua bagian utama:
1. **ONNX Detection Script**: Skrip Python untuk inferensi real-time menggunakan model ONNX.
2. **YOLOv8 Training and Export Notebook**: Notebook untuk melatih model YOLOv8 dengan dataset kustom dan mengekspor model ke format ONNX.

## Tech Stack
![Python](https://img.shields.io/badge/Python-%233776AB.svg?style=for-the-badge&logo=python&logoColor=white) ![YOLO](https://img.shields.io/badge/YOLO-%23000000.svg?style=for-the-badge&logo=YOLO&logoColor=white) ![ONNX](https://img.shields.io/badge/ONNX-%23008000.svg?style=for-the-badge&logo=ONNX&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white) ![Roboflow](https://img.shields.io/badge/Roboflow-%2318A5FD.svg?style=for-the-badge&logo=Roboflow&logoColor=white) ![OpenCV](https://img.shields.io/badge/OpenCV-%235C3EE8.svg?style=for-the-badge&logo=OpenCV&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-%23013243.svg?style=for-the-badge&logo=NumPy&logoColor=white) ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) ![Jupyter Notebook](https://img.shields.io/badge/Jupyter-%23F37626.svg?style=for-the-badge&logo=Jupyter&logoColor=white)

## Fitur
### File 1: ONNX Detection Script
- **Input**: Video streaming dari webcam.
- **Model**: Format ONNX.
- **Fungsi Utama**:
  - Preprocessing input untuk kompatibilitas model.
  - Postprocessing untuk menerapkan NMS dan menggambar bounding box.
  - Penghitungan FPS untuk evaluasi performa real-time.

### File 2: YOLOv8 Training and Export Notebook
- **Dataset**: Diunduh dari Roboflow.
- **Model**: YOLOv8 (dilatih dan diekspor ke ONNX).
- **Fungsi Utama**:
  - Pelatihan model dengan dataset kustom.
  - Ekspor model ke format ONNX.
  - Inferensi pada gambar atau video dan perhitungan rata-rata skor kepercayaan serta waktu pemrosesan.

## Persyaratan
- **detect.py**:
  - Python 3.8+
  - OpenCV
  - ONNX Runtime
  - NumPy
- **YOLOv8.ipynb**:
  - Jupyter Notebook
  - Python 3.8+
  - [Ultralytics](https://github.com/ultralytics/ultralytics)
  - Roboflow SDK
  - PyTorch

## Cara Penggunaan
### File 1: ONNX Detection Script
1. Pastikan Anda memiliki model ONNX (misalnya, `best.onnx`).
2. Jalankan skrip menggunakan perintah:
   ```bash
   python detect.py --model <path_to_model> --conf-thres 0.5 --iou-thres 0.5
