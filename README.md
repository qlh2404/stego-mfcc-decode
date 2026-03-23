# HƯỚNG DẪN THỰC HÀNH: TÁCH THÔNG ĐIỆP ẨN TRONG ÂM THANH SỬ DỤNG ĐẶC TRƯNG MFCC

**Mã bài lab:** `stego-mfcc-decode`  
**Sinh viên thực hiện:** Lương Hà Anh Quân (B21DCAT153)  
**GVHD:** PGS.TS. Đỗ Xuân Chợ  
**Học kỳ:** 2 - Năm học 2024-2025

---

## CHƯƠNG 1. GIỚI THIỆU CHUNG VỀ BÀI THỰC HÀNH

### 1.1 Mục đích
- Hiểu nguyên lý cơ bản của Steganography (giấu tin) trong môi trường âm thanh.
- Thực hành trích xuất đặc trưng MFCC và các bước tách tin từ tệp âm thanh đã nhúng tin.
- Đánh giá chất lượng âm thanh sau khi giấu tin thông qua sai số bình phương trung bình (MSE) và biểu đồ dạng sóng.

### 1.2 Yêu cầu đối với sinh viên
- Có kiến thức cơ bản về xử lý tín hiệu số và ngôn ngữ lập trình Python.
- Sử dụng thành thạo môi trường dòng lệnh Linux.

### 1.3 Kịch bản bài lab
Sinh viên đóng vai trò là người nhận (receiver), thực hiện việc tách thông điệp bí mật từ tệp âm thanh đã được nhúng tin bằng phương pháp tác động vào các hệ số MFCC.

---

## CHƯƠNG 2. NỘI DUNG THỰC HÀNH

### 2.1 Chuẩn bị môi trường
1. **Cài đặt thư viện cần thiết:**
   ```bash
   pip3 install librosa numpy scipy matplotlib soundfile
   ```
2. **Tải và khởi tạo bài lab trên Labtainer:**
   ```bash
   imodule https://github.com/qlh2404/stego-mfcc-decode/raw/refs/heads/main/imodule.tar
   ```

### 2.2 Các nhiệm vụ cần thực hiện

#### 2.2.1 Task 1: Giấu thông điệp
- **Mô tả:** Nhúng thông điệp vào tệp âm thanh gốc bằng cách thay đổi các hệ số MFCC quan trọng.
- **Thực hiện:**
  1. Mở file `secret.txt` và nhập thông điệp cần giấu.
  2. Chạy tệp `encode.py`:
     ```bash
     python3 encode.py
     ```
  3. Kết quả sẽ tạo ra tệp `stego_audio.wav` và `mfcc_stego.npy`.

#### 2.2.2 Task 2: Tách thông điệp
- **Mô tả:** Trích xuất thông điệp bí mật từ tệp âm thanh đã nhúng tin.
- **Thực hiện:**
  1. Mở tệp `decode.py` để xem nội dung và hiểu luồng hoạt động: `nano decode.py`
  2. Chạy tệp `decode.py`:
     ```bash
     python3 decode.py
     ```
  3. Kiểm tra thông điệp đã tách được:
     ```bash
     cat extracted_message.txt
     ```

#### 2.2.3 Task 3: Đánh giá chất lượng
- **Mô tả:** Đánh giá chất lượng quá trình giấu/tách tin bằng cách so sánh dạng sóng và tính MSE.
- **Thực hiện:**
  1. Chạy tệp `compare.py`:
     ```bash
     python3 compare.py
     ```
  2. Xem biểu đồ so sánh dạng sóng (sử dụng dịch vụ `eog`):
     ```bash
     eog waveform_comparison.png
     ```
  3. Kiểm tra báo cáo sai số:
     ```bash
     cat comparison_report.txt
     ```

### 2.3 Checkwork và kết thúc bài lab
Sử dụng các câu lệnh sau để lưu kết quả và kết thúc bài thực hành:
```bash
checkwork stego-mfcc-decode
stoplab stego-mfcc-decode
```

---

## 2.4 Khởi động lại bài lab (Nếu cần)
Trong trường hợp cần thực hiện lại từ đầu, sử dụng câu lệnh:
```bash
labtainer -r stego-mfcc-decode
```

