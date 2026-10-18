# Smart Timetable V2

## Chạy ứng dụng
- Giải nén thư mục.
- Khuyến nghị chạy qua localhost/HTTPS để bật ES Modules và PWA:
  - Python: `python -m http.server 8000`
  - Mở `http://localhost:8000`
- Cần kết nối Internet lần đầu để tải Bootstrap, SheetJS, Chart.js, QRCode.js và html2pdf.js từ CDN.
- Dữ liệu mẫu được trích từ hai tệp TKB đính kèm, tuần 7 năm học 2026–2027.

## Cập nhật thời khóa biểu
Chọn **Cập nhật TKB**, chọn tệp `.xls`, `.xlsx` hoặc `.csv`. Parser quét nhiều sheet, thử nhận dạng định dạng TKB giáo viên/lớp, điền giá trị ô gộp khi có thể, rồi cho chọn thay thế hoặc gộp dữ liệu.
- **Thay thế:** dùng dữ liệu đọc được làm bộ dữ liệu hiện hành.
- **Gộp/cập nhật:** cập nhật các bản ghi theo khóa lớp/giáo viên/môn/thứ/tiết; nên rà soát sau nhập.
- Dữ liệu nhập chỉ giữ trong bộ nhớ phiên hiện tại; để lưu lâu dài, xuất Excel trước khi đóng trang.

## Giới hạn dữ liệu nguồn
- Tệp TKB lớp thường chỉ chứa môn học; không thể suy ra chính xác giáo viên/phòng nếu nguồn không có.
- Tệp giáo viên có thể không có phòng học. Những ô thiếu được để trống, không tự bịa dữ liệu.
- Kiểm tra xung đột hiển thị thiếu giáo viên như cảnh báo; dữ liệu từ nhiều sheet có thể có các bản ghi tương ứng khác nhau.
- Các CDN bên ngoài không được cache bởi service worker hiện tại; khi ngoại tuyến, giao diện lõi vẫn cache nhưng một số thư viện có thể không khả dụng nếu chưa được tải trước.

## Cấu trúc
`index.html`, `css/style.css`, `js/*.js`, `data/sample-timetable.json`, `assets/logo.svg`, `manifest.json`, `sw.js`.


## Bản vá V2.1 – TKB giáo viên/lớp
- Thêm dữ liệu mẫu fallback bằng `data/sample-timetable.js`.
- Bảng TKB hiển thị đủ 8 tiết theo cấu hình.
- Upload các file/thư mục bên trong `smart-timetable-v2` lên root branch `main`, không để lồng thêm một thư mục.
- Mở bằng GitHub Pages hoặc localhost; `file://` có thể chặn ES Modules.
