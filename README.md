# Hướng dẫn chạy các dự án trên Google Colab

Dưới đây là các bước chi tiết để chạy các dự án trên Google Colab, bao gồm các tệp:

- `Data Visualization.ipynb`
- `Training_D_VAE.ipynb`
- `Training_LSTM_CNN.ipynb`
- `Training_SARIMAX.ipynb`
- `Training_SARIMAX-LSTM.ipynb`
- `Training_SARIMAX-Pathformer.ipynb`

---

## 1. Chuẩn bị môi trường

### Yêu cầu:
- **Tài khoản Google**: Để truy cập Google Colab.
- **Google Drive**: Lưu trữ dữ liệu và tệp `.ipynb`.

---

## 2. Hướng dẫn sử dụng

### Bước 1: Upload tệp lên Google Drive
1. Tạo một thư mục trên Google Drive (ví dụ: `Bitcoin Projects`).
2. Upload tất cả các tệp sau vào thư mục:
   - `Data Visualization.ipynb`
   - `Training_D_VAE.ipynb`
   - `Training_LSTM_CNN.ipynb`
   - `Training_SARIMAX.ipynb`
   - `Training_SARIMAX-LSTM.ipynb`
   - `Training_SARIMAX-Pathformer.ipynb`

### Bước 2: Mở tệp trên Google Colab
1. Truy cập [Google Colab](https://colab.research.google.com/).
2. Chọn `File` > `Open notebook`.
3. Chuyển sang tab `Google Drive` và cấp quyền truy cập Google Drive.
4. Tìm tệp trong thư mục `Bitcoin Projects` và mở tệp mong muốn.

### Bước 3: Kết nối với Runtime
1. Nhấn vào nút `Connect` ở góc trên bên phải để kết nối với máy chủ Colab.
2. Đảm bảo bạn chọn **GPU runtime** (nếu cần):
   - Vào `Runtime` > `Change runtime type`.
   - Chọn:
     - **Hardware accelerator**: GPU (nếu sử dụng mô hình học sâu).
     - **Runtime type**: Python 3.

### Bước 4: Chạy từng cell trong tệp
1. Nhấn `Shift + Enter` hoặc nhấp vào nút **Run** để chạy từng cell.
2. Theo dõi các kết quả hiển thị.

---

## 3. Ghi chú quan trọng

1. **Dữ liệu cần thiết**:
   - Đảm bảo các tập dữ liệu cần thiết được lưu trong Google Drive.
   - Nếu một tệp yêu cầu truy cập dữ liệu, bạn có thể cần chỉnh sửa đường dẫn để trỏ tới Google Drive. Ví dụ:
     ```python
     from google.colab import drive
     drive.mount('/content/drive')
     data_path = '/content/drive/MyDrive/Bitcoin Projects/data.csv'
     ```

2. **Thư viện yêu cầu**:
   - Mỗi tệp có thể yêu cầu các thư viện Python cụ thể. Nếu gặp lỗi thiếu thư viện, hãy cài đặt bằng lệnh:
     ```python
     !pip install <library-name>
     ```

3. **Kết quả**:
   - Các mô hình sẽ tạo ra các biểu đồ, số liệu hoặc kết quả dự đoán.
   - Lưu ý kiểm tra phần cuối của tệp để biết các bước lưu kết quả.

---

## 4. Danh sách dự án và mục đích

### 1. `Data Visualization.ipynb`
- **Mô tả**: Phân tích và trực quan hóa dữ liệu giao dịch Bitcoin.
- **Kết quả**: Các biểu đồ thể hiện xu hướng giá, khối lượng giao dịch, v.v.

### 2. `Training_D_VAE.ipynb`
- **Mô tả**: Huấn luyện mô hình Deep Variational Autoencoder (D-VAE) để phân tích dữ liệu.
- **Kết quả**: Mã nguồn cho mô hình và các tham số huấn luyện.

### 3. `Training_LSTM_CNN.ipynb`
- **Mô tả**: Kết hợp LSTM và CNN để dự đoán giá Bitcoin.
- **Kết quả**: Dự đoán giá và độ chính xác.

### 4. `Training_SARIMAX.ipynb`
- **Mô tả**: Sử dụng mô hình SARIMAX để dự đoán chuỗi thời gian giá Bitcoin.
- **Kết quả**: Biểu đồ dự đoán chuỗi thời gian.

### 5. `Training_SARIMAX-LSTM.ipynb`
- **Mô tả**: Kết hợp SARIMAX và LSTM để cải thiện độ chính xác dự đoán.
- **Kết quả**: So sánh kết quả giữa mô hình kết hợp và mô hình đơn lẻ.

### 6. `Training_SARIMAX-Pathformer.ipynb`
- **Mô tả**: Áp dụng mô hình Pathformer vào phân tích chuỗi thời gian.
- **Kết quả**: Biểu đồ và số liệu dự đoán nâng cao.
