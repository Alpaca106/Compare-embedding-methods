# 🌌 Hybrid Quantum-Classical Neural Networks Benchmark

Dự án này tập trung vào nghiên cứu và đánh giá hiệu năng của các kiến trúc **Mạng nơ-ron Lượng tử lai (Hybrid QNN)**. Mục tiêu cốt lõi là phân tích sự đánh đổi (trade-off) giữa độ chính xác, thời gian huấn luyện và tài nguyên Qubit thông qua 3 chiến lược mã hóa dữ liệu (Quantum Embedding) khác nhau.

## 🛠 Cấu hình phần cứng (Hardware Setup)
Thực nghiệm được tối ưu hóa để chạy trên các dòng máy trạm hỗ trợ GPU:
- **GPU:** NVIDIA Quadro T2000 (Hỗ trợ kiến trúc Turing, CUDA 11.2).
- **CPU:** Intel® Xeon®.
- **Môi trường:** Python 3.11.0, hỗ trợ tăng tốc CUDA.

## 🗂 Cấu trúc mã nguồn (Project Structure)

Dự án bao gồm 3 file thực nghiệm chính, tương ứng với các nhóm dữ liệu và phương pháp nhúng khác nhau:

1. **`angle_tabular_data.ipynb`**: 
   - Tập trung vào phương pháp **Angle Embedding**.
   - Dữ liệu thử nghiệm: *Banknote Authentication*, *Breast Cancer*.
   - Mục tiêu: Đánh giá độ ổn định và tốc độ của phương pháp nhúng tuyến tính trên dữ liệu bảng.

2. **`amplitude_highdim.ipynb`**:
   - Tập trung vào phương pháp **Amplitude Embedding**.
   - Dữ liệu thử nghiệm: *Sonar* (60D), *Fashion-MNIST* (Hình ảnh).
   - Mục tiêu: Chứng minh khả năng nén dữ liệu hàm mũ và xử lý dữ liệu siêu cao chiều với số lượng Qubit cực thấp.

3. **`iqp_nonlinear.ipynb`**:
   - Tập trung vào phương pháp **IQP Embedding (ZZ-Feature Map)**.
   - Dữ liệu thử nghiệm: *Two Moons*, *Checkerboard*.
   - Mục tiêu: Khai thác sức mạnh của sự vướng víu lượng tử (Entanglement) để giải quyết các ranh giới phân loại phi tuyến phức tạp.

## 🚀 Hướng dẫn cài đặt và Chạy mã nguồn

### Cài đặt các thư viện cơ bản
Đảm bảo bạn đã tải file `requirements.txt`. Mở Terminal tại thư mục dự án và chạy:
```bash
pip install -r requirements.txt
```
Để code nhận diện Card đồ họa NVIDIA (CUDA) và hiển thị thông báo "Bắt đầu Training trên thiết bị: CUDA", cần chạy lệnh cài đặt phiên bản hỗ trợ:
```bash
pip install torch torchvision torchaudio --index-url [https://download.pytorch.org/whl/cu118](https://download.pytorch.org/whl/cu118)
```
