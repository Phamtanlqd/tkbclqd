# Smart Timetable V2.1 — bản sửa TKB tuần 7

Khuyến nghị chạy GitHub Pages hoặc localhost. Chạy cục bộ: `python -m http.server 8000`, mở `http://localhost:8000`. Không mở trực tiếp bằng `file://` vì trình duyệt chặn ES Modules.

GitHub Pages: đưa toàn bộ NỘI DUNG thư mục này lên root nhánh `main`; bật Settings → Pages → Deploy from a branch → `main` → `/(root)`.

Bản sửa: dữ liệu tuần 7 thực từ file Excel đã cung cấp (814 bản ghi); thêm fallback dữ liệu nhúng nếu JSON lỗi; bảng TKB hiển thị 8 tiết; cập nhật phiên bản cache service worker.

Cập nhật: nhấn “Cập nhật TKB”, chọn Excel, chọn thay thế hoặc gộp dữ liệu.
