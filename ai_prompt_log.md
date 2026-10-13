# Nhật ký Sử dụng AI
## Dự án: Tái cấu trúc Layout CreativeChronicle

### 🎯 Prompt 1: Tác hại của float
**Prompt:** "Tại sao float lại gây ra hiện tượng cha không ôm trọn con (collapse), và tại sao cần clearfix?"

**Trả lời:** 
- `float` đưa phần tử con **ra khỏi luồng tài liệu** → cha không tính được chiều cao.
- Phải dùng `overflow: hidden` hoặc `clearfix` (`::after { clear: both; }`).
- **Flexbox/Grid** tự động bao quanh con → không cần clearfix.

**Áp dụng:** Bỏ `overflow: hidden` trong `.author-section` → dùng `display: flex`.

---

### 🎯 Prompt 2: Flexbox căn giữa dọc
**Prompt:** "Cách căn giữa dọc các phần tử trên cùng một hàng bằng Flexbox?"

**Trả lời:**
```css
.parent {
    display: flex;
    align-items: center;
    justify-content: space-between;
}