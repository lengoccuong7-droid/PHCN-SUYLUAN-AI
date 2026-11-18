# PHCN AI 4.3.0 – Trợ lý suy luận lâm sàng PHCN offline-first

## Chức năng
- Quản lý hồ sơ bệnh nhân và lịch sử lần khám bằng SQLite.
- Nhập bệnh sử tự do và thông tin khám có cấu trúc.
- NLP tiếng Việt dựa trên quy tắc để nhận diện một số triệu chứng, vị trí, bên, thời gian và yếu tố liên quan.
- Suy luận giả thuyết, bằng chứng ủng hộ/chống lại, dữ liệu còn thiếu, cảnh báo và tổng hợp chẩn đoán sơ bộ.
- Bổ sung thông tin tự do sau phân tích và chạy phân tích lại nhiều vòng mà không nhập lại hồ sơ.
- Tra cứu tri thức, nghiệm pháp, kho bài tập, theo dõi, kế hoạch PHCN và sao lưu.
- Không gọi API AI bên ngoài.

## Cài đặt trên Windows
1. Cài Python 3.10 hoặc mới hơn.
2. Giải nén ZIP.
3. Mở Command Prompt tại thư mục dự án.
4. Tạo môi trường: `python -m venv .venv`
5. Kích hoạt: `.venv\Scripts\activate`
6. Cài thư viện: `pip install -r requirements.txt`
7. Chạy: `streamlit run app.py`
8. Mở địa chỉ Streamlit hiển thị trong terminal.

## macOS / Linux
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
streamlit run app.py
```

## Dùng trên điện thoại
Có thể mở giao diện qua URL của máy chủ Streamlit nếu điện thoại truy cập được máy chủ qua mạng/Internet. PWA hỗ trợ một phần lưu nội dung ngoại tuyến; engine Streamlit và SQLite vẫn chạy trên máy chủ. Vì vậy, không được hiểu là ứng dụng có thể suy luận hoàn toàn khi iPhone mất kết nối tới máy chủ.

## Bảo mật
- Dữ liệu SQLite nằm trong `data/phcn_ai.db`. Sao lưu định kỳ bằng chức năng trong ứng dụng hoặc sao chép an toàn tệp DB khi ứng dụng đã dừng.
- Không triển khai máy chủ công khai nếu chưa cấu hình mật khẩu, HTTPS và kiểm soát truy cập.
- Chỉ dùng dữ liệu đã được phép xử lý; hạn chế thông tin định danh không cần thiết.

## Vai trò lâm sàng và giới hạn
Đây là công cụ hỗ trợ quyết định, không thay thế bác sĩ. Bộ suy luận hiện tại là hệ thống luật/NLP offline, không phải mô hình hiểu ngôn ngữ tổng quát hoặc AI chuyên khoa đã được thẩm định. Điểm thuật toán không phải xác suất mắc bệnh. Bác sĩ trực tiếp khám là người quyết định cuối cùng.

## Phiên bản
Xem `VERSION` và `RELEASE_NOTES_4_3.md`.
