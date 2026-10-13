# Báo cáo Tái cấu trúc Layout - CreativeChronicle

## 🚨 Tác hại của `position: absolute` với Responsive Design

### 1. Mất chiều cao thực tế của phần tử cha
Khi con dùng `position: absolute`, nó **thoát khỏi luồng tài liệu** → cha không còn biết con cao bao nhiêu → **chiều cao cha = 0** → nội dung bên dưới bị **đè lấn**.

### 2. Gây "vỡ" layout khi màn hình thay đổi
- Lập trình viên cũ **fix cứng** `height: 400px` cho gallery.
- Trên mobile 375px, ảnh bị **co bóp méo** hoặc **đè lên text**.
- Không thể tự động điều chỉnh theo nội dung.

### 3. Khó bảo trì, dễ gây bug
- Mỗi ảnh phải **tính toán pixel thủ công** (`top`, `left`, `right`, `bottom`).
- Thêm ảnh mới → phải sửa toàn bộ CSS.
- Không hỗ trợ tốt cho **nội dung động**.

## ✅ CSS Grid - Giải pháp cứu cánh

CSS Grid cho phép:
- **Định vị 2 chiều** đồng thời (hàng + cột) mà không cần tính pixel.
- **`grid-template-columns: 2fr 1fr`** → tự động chia tỷ lệ.
- **`grid-row: span 2`** → ảnh lớn chiếm 2 hàng.
- **Tự động tính chiều cao** theo nội dung → không đè lấn.
- **Responsive dễ dàng**: chỉ cần đổi `grid-template-columns: 1fr` trên mobile.

## 🎯 Kết luận

**Grid sinh ra để làm layout 2D**, thay thế hoàn toàn `position: absolute` + `height` cứng. Code ngắn hơn, dễ đọc hơn, responsive hoàn hảo.