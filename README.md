# KRX FIX Simulator - Giả lập Sàn Giao dịch Chứng khoán

![Python](https://img.shields.io/badge/python-3.9+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

Trình giả lập hệ thống khớp lệnh và cổng giao dịch FIX (Financial Information eXchange) cho thị trường chứng khoán Việt Nam, được thiết kế để mô phỏng lại các phiên giao dịch của sàn HSX và HNX theo mô hình của hệ thống KRX.

## 🇻🇳 Giới thiệu

Dự án này được xây dựng với mục tiêu cung cấp một môi trường Server-side hoàn chỉnh cho các nhà phát triển, công ty chứng khoán, hoặc các bên thứ ba muốn kiểm thử hệ thống giao dịch của mình trước khi kết nối vào hệ thống thật. Simulator sử dụng thư viện QuickFIX (bản port cho Python) để quản lý kết nối FIX và một kiến trúc đa tiến trình (multi-processing) để xử lý nghiệp vụ một cách hiệu quả.

## ✨ Tính năng chính

- **Hỗ trợ Giao thức FIX 4.4**: Tuân thủ các quy tắc cơ bản của phiên làm việc FIX.
- **Quản lý Phiên (Session Management)**:
  - Xử lý Logon (35=A), Logout (35=5), Heartbeat (35=0).
  - Hỗ trợ custom Data Dictionary để chấp nhận các trường tùy chỉnh (custom tags) của KRX.
- **Mô phỏng Phiên Giao Dịch (Trading Session)**:
  - Tự động gửi tin `TradingSessionStatus` (35=h) khi client kết nối, thông báo trạng thái phiên hiện tại (PREOPEN, LO1, ATC, CLOSED, v.v.).
  - Cấu hình được các mốc thời gian cho từng phiên trong ngày.
- **Mô phỏng Dữ liệu Thị trường (Market Data)**:
  - Tự động gửi tin `MarketDataSnapshotFullRefresh` (35=W) chứa thông tin cơ bản của mã chứng khoán (tham chiếu, trần, sàn) khi client kết nối.
- **Xử lý Lệnh Giao dịch (Order Processing)**:
  - Nhận và xác thực lệnh `NewOrderSingle` (35=D).
  - Phản hồi bằng `ExecutionReport` (35=8) với các trạng thái:
    - `New` (0): Lệnh mới được chấp nhận.
    - `Rejected` (8): Lệnh bị từ chối (do sai mã, thị trường đóng cửa, v.v.).
- **Kiến trúc Bất đồng bộ**: Sử dụng hàng đợi (Queue) và các tiến trình riêng biệt (Worker) để xử lý nghiệp vụ, không làm nghẽn luồng nhận tin nhắn FIX chính, đảm bảo hiệu năng cao.
- **Hỗ trợ Đa sàn (Multi-Market)**: Cấu hình và chạy giả lập cho cả hai sàn HSX và HNX trên cùng một trình giả lập.

## 🛠️ Môi trường và Công nghệ

- **Ngôn ngữ**: Python 3.9+
- **Thư viện FIX**: `quickfix` (phiên bản Python)
- **Kiến trúc**: Multi-processing (sử dụng module `multiprocessing`)
- **Cấu hình**: `PyYAML` (đọc file `config.yaml`)
- **Múi giờ**: `pytz`

## 🚀 Hướng dẫn Cài đặt và Chạy thử

### 1. Yêu cầu hệ thống

- Python 3.9 trở lên.
- `pip` và `venv` (thường đi kèm với Python).

### 2. Cài đặt

1.  **Clone repository về máy của bạn:**
    ```bash
    git clone <URL_CUA_DU_AN_NAY>
    cd <TEN_THU_MUC_DU_AN>
    ```

2.  **Tạo và kích hoạt môi trường ảo (virtual environment):**
    ```bash
    # Windows
    python -m venv .venv
    .venv\Scripts\activate

    # macOS / Linux
    python3 -m venv .venv
    source .venv/bin/activate
    ```

3.  **Cài đặt các thư viện cần thiết:**
    Tạo file `requirements.txt` với nội dung sau:
    ```txt
    quickfix
    pyyaml
    pytz
    ```
    Sau đó chạy lệnh:
    ```bash
    pip install -r requirements.txt
    ```

### 3. Cấu hình

Mọi cấu hình của simulator được quản lý trong file `config.yaml`.

1.  **File cấu hình FIX**: `fix_config_file: 'fix_config.cfg'`
    - File này chứa các thiết lập về cổng (port), đường dẫn log, và định danh (CompID) cho FIX Engine.

2.  **Từ điển FIX**: `fix_dictionary_file: 'FIX.4.4-KRXSIM.xml'`
    - File định nghĩa các trường và tin nhắn FIX, bao gồm cả các trường tùy chỉnh.

3.  **Cấu hình phiên (sessions)**: Định nghĩa các mốc thời gian trong ngày cho các sàn.

4.  **Cấu hình Client (market_clients & trading_clients)**: Khai báo các `SenderCompID` của client sẽ kết nối vào để giả lập nhận dữ liệu thị trường hoặc đặt lệnh.

### 4. Chạy chương trình

Sau khi đã hoàn tất cài đặt và cấu hình, chạy file `main.py`:

```bash
python main.py
```

Simulator sẽ khởi động, dọn dẹp log cũ, tải dữ liệu SFTP, và bắt đầu lắng nghe kết nối từ FIX client trên cổng đã được cấu hình.

## ❤️ Đóng góp & Ủng hộ

Dự án này là một sản phẩm mã nguồn mở và phi lợi nhuận. Mọi sự đóng góp về mã nguồn (qua Pull Request) hoặc ủng hộ về tài chính đều là nguồn động viên to lớn để dự án tiếp tục phát triển.

Nếu bạn thấy dự án này hữu ích, hãy cân nhắc ủng hộ tôi qua:

- **Buy Me a Coffee**: [https://www.buymeacoffee.com/your_username](https://www.buymeacoffee.com/your_username)
- **PayPal**: [https://paypal.me/your_username](https://paypal.me/your_username)
- **Crypto (BTC)**: `your_btc_address_here`

## 📝 Giấy phép

Dự án này được phát hành dưới giấy phép MIT. Xem file `LICENSE` để biết thêm chi tiết.
