# ĐỒ ÁN TỐT NGHIỆP ĐẠI HỌC
# ỨNG DỤNG TRÍ TUỆ NHÂN TẠO TRONG CHẨN ĐOÁN VÀ PHÁT HIỆN BỆNH TRÊN LÚA DỰA VÀO HÌNH ẢNH

---

## 📋 Giới thiệu

Đề tài được thực hiện nhằm hỗ trợ người nông dân phát hiện sớm các loại bệnh phổ biến trên cây lúa thông qua việc chụp ảnh lá lúa bằng điện thoại. Hệ thống tự động phân tích và đưa ra kết quả chẩn đoán cùng lời khuyên xử lý ngay trên thiết bị, không cần kết nối internet.

### Các loại bệnh được nhận diện
| Tên bệnh | Tên khoa học |
|---|---|
| Bệnh đạo ôn | Blast |
| Bệnh bạc lá | Bacterial Blight |
| Bệnh đốm nâu | Brown Spot |

---

## 🏆 Kết quả mô hình

| Lần huấn luyện | Phương pháp | Độ chính xác (Test) |
|---|---|---|
| Lần 1 | ResNet-50 cơ bản | 64.99% |
| Lần 2 | + Tăng cường dữ liệu (xoay, lật) | 73.40% |
| Lần 3 | + Fine-tuning 2 giai đoạn, Dropout, Label Smoothing | **97.12%** |

**Kết quả lần 3 (tốt nhất):**
- Bệnh bạc lá: 100%
- Bệnh đốm nâu: 98%
- Bệnh đạo ôn: 93%

---

## 🛠️ Công nghệ sử dụng

**Huấn luyện mô hình:**
- Python, TensorFlow/Keras
- ResNet-50 (pretrained ImageNet)
- Google Colab (GPU T4)

**Ứng dụng di động:**
- Flutter (Android)
- TensorFlow Lite

**Thư viện hỗ trợ:** NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn, OpenCV

---

## 📁 Cấu trúc dự án

```
├── model/                  # Notebook huấn luyện và dữ liệu
│   ├── data/
│   │   ├── Bacterialblight
│   │   ├── Brownspot
│   │   └── Leafsmut
│   └── train.ipynb
├── app/                    # Ứng dụng Flutter
│   ├── lib/
│   │   ├── main.dart
│   │   ├── home_screen.dart
│   │   ├── result_screen.dart
│   │   ├── disease_info.dart
│   │   ├── disease_model.dart
│   │   └── scan_controller.dart
│   └── assets/
│       ├── images/
│       └── model/          # Mô hình hoàn thiện
│           └── rice_disease_model.tflite      
└── README.md
```

---

## 📱 Chức năng ứng dụng

- **Chụp ảnh mới** — chẩn đoán trực tiếp qua camera
- **Chọn ảnh từ thư viện** — chẩn đoán từ ảnh có sẵn
- **Xem kết quả** — tên bệnh, độ tin cậy, lời khuyên xử lý
- **Tra cứu thông tin** — đặc điểm nhận dạng, thuốc đặc trị từng loại bệnh

---

## 📊 Dữ liệu

- **Nguồn:** [Rice Leaf Diseases Dataset – Mendeley Data](https://data.mendeley.com/datasets/dwtn3c6w6p/1)
- **Số lượng:** ~4.600 ảnh, 3 nhóm bệnh cân bằng
- **Chia tập:** Train 60% / Validation 20% / Test 20%

---

## 🚀 Hướng dẫn chạy

### Huấn luyện mô hình
```bash
# Mở notebook trên Google Colab
# Kết nối Google Drive và chạy các cell theo thứ tự
```

### Chạy ứng dụng Flutter
```bash
cd app
flutter pub get
flutter run
```

---

## 👩‍💻 Tác giả

**Mai Thị Diễm**
