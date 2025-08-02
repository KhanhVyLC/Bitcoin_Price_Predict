# Hướng dẫn chạy các dự án Dự đoán giá Bitcoin trên Google Colab
Link dataset: https://www.kaggle.com/datasets/sushilkumarinfo/bitcoin-data-from-9thapr2014-to-30thdec2022

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
- **Mô tả**: Huấn luyện mô hình Diffusion Variational Autoencoder (D-VAE) để phân tích dữ liệu.

### 3. `Training_SARIMAX.ipynb`
- **Mô tả**: Kết hợp LSTM và CNN để dự đoán giá Bitcoin.

### 4. `Training_SARIMAX-LSTM.ipynb`
- **Mô tả**: Sử dụng mô hình SARIMAX để dự đoán chuỗi thời gian giá Bitcoin.

### 5. `Training_Transformer.ipynb`
- **Mô tả**: Kết hợp SARIMAX và LSTM để cải thiện độ chính xác dự đoán.

### 6. `Training_SARIMAX-Transformer.ipynb`
- **Mô tả**: Áp dụng mô hình Pathformer vào phân tích chuỗi thời gian.


# Kết quả:
- Dự đoán giá và các chỉ số đánh giá mô hình, biểu đồ dự đoán chuỗi thời gian.
SARIMAX: MAE là 498,66, RMSE là 545,51 và MAPE là 2,26%. SARIMAX mô hình hóa hiệu quả các thành phần theo mùa và xu hướng, mang lại độ chính xác khá. Bản chất tuyến tính của nó hạn chế khả năng nắm bắt các biến động giá phức tạp.
- SARIMAX-LSTM: MAE là 0,64, RMSE là 0,6627 và MAPE là 0,0028%. Mô hình này kết hợp mô hình xu hướng của SARIMAX với khả năng phi tuyến tính của LSTM, đạt được độ chính xác gần như hoàn hảo. Sự thành công của nó xác nhận sức mạnh của các phương pháp tiếp cận kết hợp.
- Transformer: MAE là 9.712,76, RMSE là 10.550,84 và MAPE là 44,91%. Hiệu suất kém của Transformer là điều đáng ngạc nhiên, xét đến sức mạnh của nó trong các tác vụ tuần tự. Transformer hoạt động tốt trên các chuỗi dữ liệu dài và giàu quan hệ, chẳng hạn như văn bản hoặc chuỗi phân loại. Tuy nhiên, dữ liệu giá Bitcoin là chuỗi thời gian thường bị nhiễu cao, có tính không dừng và có xu hướng thay đổi đột ngột.
- Transformer-SARIMAX: MAE là 86,64, RMSE là 94,11 và MAPE là 0,3746%. Bằng cách kết hợp mô hình tuyến tính có cấu trúc của SARIMAX với khả năng học tập còn lại của Transformer, mô hình lai này đạt được kết quả đặc biệt so với mô hình Transformer đơn lẻ.
- Diffusion-VAE (Bộ mã hóa tự động biến đổi): MAE là 552,71, RMSE là 602,58 và MAPE là 2,33%. Diffusion-VAE, mặc dù mang tính sáng tạo, nhưng không vượt trội hơn các mô hình lai đơn giản hơn. Tiềm năng của nó nằm ở khả năng tinh chỉnh và tối ưu hóa tốt hơn.

<img width="686" height="237" alt="image" src="https://github.com/user-attachments/assets/baa81c64-3598-44ee-9a3e-f38a686bfdfe" />





