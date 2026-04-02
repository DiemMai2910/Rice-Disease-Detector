# ĐỒ ÁN TỐT NGHIỆP ĐẠI HỌC
# ỨNG DỤNG TRÍ TUỆ NHÂN TẠO TRONG CHẨN ĐOÁN VÀ PHÁT HIỆN BỆNH TRÊN LÚA DỰA VÀO HÌNH ẢNH

---

## 📋 Giới thiệu

Đề tài được thực hiện nhằm hỗ trợ người nông dân phát hiện sớm các loại bệnh phổ biến trên cây lúa thông qua việc phân tích hình ảnh lá lúa. Hệ thống tự động phân tích và đưa ra kết quả chẩn đoán về bệnh lá lúa.

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

- Python, TensorFlow/Keras
- ResNet-50 (pretrained ImageNet)
- Google Colab (GPU T4)

**Thư viện hỗ trợ:** NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn, OpenCV

---

## 📁 Cấu trúc dự án

```
├── data/
│   ├── Bacterialblight/
│   ├── Blast/
│   └── Brownspot/
├── train.ipynb             # Notebook huấn luyện mô hình
└── README.md
```

---

## 📊 Dữ liệu

- **Nguồn:** [Rice Leaf Diseases Dataset – Mendeley Data](https://data.mendeley.com/datasets/dwtn3c6w6p/1)
- **Số lượng:** ~4.600 ảnh, 3 nhóm bệnh cân bằng
- **Chia tập:** Train 60% / Validation 20% / Test 20%

---

## 🚀 Hướng dẫn chạy

```bash
# Mở train.ipynb trên Google Colab
# Kết nối Google Drive và chạy các cell theo thứ tự
```

---

## 👩‍💻 Tác giả

**Mai Thị Diễm**