# Dự án Nhận diện Biển số Xe


Dự án này tập trung vào việc phát hiện và nhận diện biển số xe từ hình ảnh bằng cách kết hợp WPOD (Weakly-supervised Positioning Object Detection) và PARSeq (Parallel Sequence). Hệ thống có khả năng phát hiện chính xác biển số xe và nhận diện các ký tự trên đó. Ngoài ra, dự án cũng cung cấp một giao diện thân thiện với người dùng để tương tác.

---

## Mục lục
- [Giới thiệu](#giới-thiệu)
- [Tính năng](#tính-năng)
- [Cài đặt](#cài-đặt)
  - [Yêu cầu hệ thống](#yêu-cầu-hệ-thống)
  - [Clone Repository](#clone-repository)
- [Cách sử dụng](#cách-sử-dụng)
- [Cấu trúc dự án](#cấu-trúc-dự-án)
- [Chi tiết mô hình](#chi-tiết-mô-hình)
- [Lời cảm ơn](#lời-cảm-ơn)

---

## Giới thiệu

Dự án Nhận diện Biển số Xe (LPR) kết hợp các mô hình học máy tiên tiến để phát hiện và nhận diện biển số xe. Dự án sử dụng WPOD để phát hiện biển số và PARSeq để nhận diện ký tự, cung cấp một giải pháp mạnh mẽ cho các ứng dụng thực tế như giám sát giao thông, hệ thống đỗ xe, và thu phí tự động.

### Công nghệ chính:
- **WPOD**: Một mạng nơ-ron được thiết kế để phát hiện chính xác biển số xe trong nhiều góc độ và điều kiện ánh sáng khác nhau.
- **PARSeq**: Mô hình nhận diện chuỗi đảm bảo khả năng nhận diện ký tự chính xác và hiệu quả từ hình ảnh biển số xe.

---

## Tính năng
- **Phát hiện biển số xe**: Sử dụng WPOD để phát hiện biển số xe đáng tin cậy.
- **Nhận diện ký tự**: Tận dụng PARSeq để nhận diện chính xác các ký tự trên biển số xe.
- **Hỗ trợ thời gian thực**: Hỗ trợ phát hiện và nhận diện thời gian thực từ nguồn webcam.
- **Giao diện Gradio**: Cung cấp giao diện trực quan cho người dùng tải lên hình ảnh hoặc sử dụng webcam để xử lý.
- 
![image](https://github.com/user-attachments/assets/bbdafa1f-0aff-48eb-80d5-67fb4e204b7e)
---
![image](https://github.com/user-attachments/assets/277d4d81-807d-4ce0-8051-a24bdf2e9ea1)


## Cài đặt

### Yêu cầu hệ thống
Để chạy dự án này, đảm bảo bạn đã cài đặt các công cụ sau:
- **Python 3.10**
- **Docker** (tùy chọn, để triển khai container hóa)

### Clone Repository
```bash
# Clone repository
git clone https://github.com/yukioreki1302/Internship-Aimesoft-ALPR.git

# Di chuyển vào thư mục dự án
cd Internship-Aimesoft-ALPR/License_Plate_Recognition
```

### Cài đặt các thư viện cần thiết
```bash
# Cài đặt các thư viện Python
pip install -r requirements.txt
```

---

## Cách sử dụng

### Chạy dự án
1. Chạy giao diện Gradio để xử lý hình ảnh hoặc nguồn webcam:
   ```bash
   python app.py
   ```

2. Truy cập giao diện Gradio thông qua URL localhost được cung cấp trên trình duyệt.

### Các tùy chọn đầu vào:
- **Tải lên hình ảnh**: Chọn một hình ảnh từ thiết bị của bạn để nhận diện biển số xe.
- **Nguồn webcam**: Sử dụng webcam để phát hiện và nhận diện thời gian thực.
![image](https://github.com/user-attachments/assets/9ceb9403-8011-4e2c-a560-e8abfa0e61d6)



---

## Cấu trúc dự án
```
.codegpt/
.head
.gitignore
.gradio/
.certificate.pem
.vscode/
.settings.json
flagged/
License_Plate_Recognition/
    .gitattributes
    .gitignore
    app.py
    parseq/
        __pycache__/
        augmentation.py
        config.yaml
        module.py
        system.py
        utils.py
    README.md
    requirements.txt
    test.ipynb
    weights/
        best.ckpt
        checkpoint.ckpt
        parseq.ckpt
        test
        wpod-net.h5
    wpodnet/
        __init__.py
        __pycache__/
        backend.py
        lib_detection.py
        model.py
        stream.py
```

---

## Chi tiết mô hình

### WPOD (Wraped Planer Object Detection Network):
- Chịu trách nhiệm phát hiện biển số xe trong hình ảnh.
- Xử lý các góc độ, hướng, và điều kiện ánh sáng khác nhau.

### PARSeq (Permuted Autoregressive Sequence Models):
- Thực hiện nhận diện ký tự trên các biển số đã được phát hiện.
- Đảm bảo độ chính xác cao và hiệu quả trong việc đọc chuỗi ký tự.

---

## Lời cảm ơn
- **WPOD**: Được tùy chỉnh từ [WPOD-Net GitHub Repository](https://github.com/xiezhq-herbert/WPOD-Net).
- **PARSeq**: Dựa trên [PARSeq Research Paper and Codebase](https://github.com/mlfoundations/parseq).


---

## Cải tiến trong tương lai
- Bổ sung hỗ trợ nhận diện đa ngôn ngữ.
- Tích hợp với dịch vụ đám mây để triển khai trên quy mô lớn.
- Cải thiện tốc độ và độ chính xác phát hiện với các mô hình được tối ưu hóa.

---

