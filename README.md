# Dự đoán giá laptop theo cấu hình và thương hiệu

Đồ án môn Machine Learning (Nhóm 45), ĐH Nông Lâm TP.HCM.
So sánh 4 mô hình hồi quy để dự đoán giá laptop từ cấu hình phần cứng và thương hiệu.

📄 **Báo cáo đầy đủ:** [Nhom45_DuDoanGiaLaptopTheoCauHinhVaThuongHieu.pdf](https://github.com/user-attachments/files/33288558/Nhom45_DuDoanGiaLaptopTheoCauHinhVaThuongHieu.pdf)

## Dữ liệu
- [Laptop Price Dataset (Kaggle)](https://www.kaggle.com/datasets/abdulrahmanelbanna/laptop-price-dataset): hơn 1.300 laptop
- Giá gốc bằng INR, quy đổi sang VND

## Phương pháp
1. Phân tích khám phá dữ liệu (EDA) và tiền xử lý
2. Trích xuất đặc trưng từ 6 cột dạng chuỗi (CPU, GPU, RAM, Memory, ScreenResolution, Weight)
3. Tự xây dựng đặc trưng `Cpu_Tier`, `Gpu_Tier` để xếp hạng hiệu năng phần cứng
4. One-Hot Encoding, StandardScaler, đóng gói bằng Pipeline
5. Huấn luyện 4 mô hình, tinh chỉnh bằng GridSearchCV 5-fold

## Kết quả

| Mô hình | R² | MAE (VND) | MAPE |
|---|---|---|---|
| **XGBoost** | **0,8653** | **2.299.121** | 14,70% |
| Random Forest | 0,8521 | 2.625.104 | 16,14% |
| SVR | 0,8300 | 2.565.512 | 14,46% |
| Linear Regression | 0,7815 | 3.642.296 | 25,95% |

Các đặc trưng ảnh hưởng nhiều nhất đến giá: RAM, hạng CPU, hạng GPU, dung lượng SSD.

## Công nghệ
Python, pandas, numpy, scikit-learn, XGBoost, matplotlib, seaborn (Google Colab)

## Thành viên
| Thành viên | Phụ trách |
|---|---|
| Nguyễn Khánh Dinh | EDA, tiền xử lý, trích xuất đặc trưng, huấn luyện XGBoost và Random Forest |
| Vũ Châu Hoài Phong | Mã hóa và chuẩn hóa, chọn lọc đặc trưng, huấn luyện Linear Regression và SVR, đánh giá |

## Mã nguồn
[Google Drive](https://drive.google.com/drive/folders/1CDdFp5iqLJZP9ajkhfwi3VU7myUh_Btu)
