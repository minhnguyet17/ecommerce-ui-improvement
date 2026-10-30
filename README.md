# E-commerce UI Improvement

Thiết kế lại thẻ sản phẩm và lưới danh sách sản phẩm cho website thời trang, tham khảo YODY (yody.vn).
Bài tập cá nhân Buổi 1 (khảo sát và cải tiến giao diện) và Buổi 2 (HTML5 & CSS3) – Phát triển ứng dụng WEB/TMĐT.

- **Xem trang demo:** https://minhnguyet17.github.io/ecommerce-ui-improvement/
- **Sinh viên:** Nguyễn Thị Minh Nguyệt – 87251020135

## 1. Giới thiệu

YODY là website bán quần áo và phụ kiện cho nam, nữ, trẻ em. Khi khảo sát ngày 18/10/2026, tôi thấy thẻ sản phẩm ở trang danh mục và trang tìm kiếm (bản điện thoại) chỉ hiện tên sản phẩm trên 1 dòng và không có nút thao tác. Bài tập này dựng lại giao diện thẻ sản phẩm và lưới danh sách sản phẩm bằng HTML5 và CSS3, hiển thị tốt trên cả máy tính và điện thoại.

## 2. Website tham khảo

- Tên website: YODY
- URL: https://yody.vn/
- Khu vực đã khảo sát: Trang chủ, Danh mục sản phẩm, Chi tiết sản phẩm, Tìm kiếm, Giỏ hàng. Bảng khảo sát chi tiết: [KHAO_SAT.md](KHAO_SAT.md)

## 3. Chức năng

- Hiển thị danh sách 8 sản phẩm mẫu dạng lưới.
- Hiển thị tên sản phẩm (tối đa 3 dòng trên điện thoại, 2 dòng trên tablet và máy tính), giá khuyến mãi, giá gốc, % giảm và số tiền tiết kiệm.
- Chọn nhanh size ngay trên thẻ; size hết hàng bị gạch ngang và không chọn được.
- Nút "Thêm vào giỏ" chuyển sang màu đậm khi đã chọn size.
- Nút "Yêu thích" (biểu tượng tim) cạnh nút "Thêm vào giỏ" *(Buổi 2, hiện chỉ là giao diện; chức năng sẽ thêm bằng JavaScript ở Buổi 3)*.
- Bố cục hỗ trợ nhiều kích thước màn hình: 2 cột (điện thoại), 3 cột (tablet), 4 cột (máy tính).

## 4. Công nghệ

- HTML5
- CSS3: Flexbox, CSS Grid, media query, biến CSS, bộ chọn `:has()`
- Không dùng JavaScript, thư viện ngoài hay backend.

## 5. Cách chạy

Mở file `index.html` bằng trình duyệt, hoặc chạy bằng Live Server / Live Preview trong VS Code. Có thể xem bản trực tuyến qua link GitHub Pages ở đầu trang.

```
ecommerce-ui-improvement/
├── index.html
├── css/
│   └── style.css
├── images/          8 ảnh minh họa SVG tự vẽ
├── screenshots/     ảnh giao diện trước/sau Buổi 2
├── KHAO_SAT.md      bảng khảo sát yody.vn (Buổi 1)
├── BAO_CAO_BUOI2.md báo cáo Buổi 2: các bước, kiểm thử, câu hỏi kiến thức
├── AI_USAGE.md      nhật ký sử dụng AI (Buổi 1 và Buổi 2)
└── README.md
```

## 6. Cải tiến đã thực hiện

**Vấn đề ban đầu** (yody.vn, bản điện thoại): tên sản phẩm trên thẻ bị cắt còn 1 dòng (VD "Quần Âu Nam Khóa Sườn An…") nên khó phân biệt các mẫu na ná nhau; thẻ không có nút thao tác, muốn mua phải mở trang chi tiết và kéo xuống mới thấy nút "Thêm vào giỏ"; nhãn % giảm nằm ở góc ảnh, tách khỏi giá.

**Thay đổi đã thực hiện:**

| Trước (yody.vn) | Sau (bản cải tiến) |
|---|---|
| Tên chỉ 1 dòng, bị cắt | Tên tối đa 3 dòng trên điện thoại, 2 dòng trên màn hình lớn; rê chuột vào tên để xem tên đầy đủ |
| Nhãn % giảm ở góc ảnh | Khối giá gồm giá khuyến mãi, % giảm, giá gốc gạch ngang và dòng "Tiết kiệm …đ" đặt cạnh nhau |
| Thẻ không có nút thao tác | Chọn size và nút "Thêm vào giỏ" ngay trên thẻ, kèm dòng nhắc "Chọn size trước khi thêm vào giỏ" |
| Không thể hiện size hết hàng trên thẻ | Size hết hàng gạch ngang, không chọn được; chọn size được bằng bàn phím |

**Điểm tự phát hiện và sửa:** khi kiểm tra ở chế độ điện thoại (375px), tên dài vẫn bị cắt ở dòng thứ 2 vì thẻ chỉ rộng khoảng 150px. Tôi đổi giới hạn thành 3 dòng cho điện thoại (`-webkit-line-clamp: 3`, `min-height: 4.2em`) và giữ 2 dòng từ 600px trở lên bằng media query.

## 7. Hỗ trợ từ AI

Tôi dùng Claude (Anthropic) để phân tích website theo Prompt 1, đề xuất phương án thiết kế (Prompt 5.2), tạo mã HTML/CSS và ảnh minh họa (Prompt 5.3), và hướng dẫn các bước Git/GitHub. Tôi đã đối chiếu kết quả phân tích của AI với website thật (loại bỏ 12/29 nhận định sai hoặc chưa có bằng chứng), tự chạy thử trang bằng Chrome DevTools ở nhiều kích thước màn hình và tự sửa lỗi cắt tên sản phẩm trên điện thoại. Chi tiết: [AI_USAGE.md](AI_USAGE.md)

## 8. Buổi 2 – HTML5 & CSS3

**Khu vực cải tiến:** danh sách sản phẩm (lưới + thẻ sản phẩm), tiếp tục từ Buổi 1. Báo cáo đầy đủ (Bước 1–8, bảng kiểm thử, 7 câu hỏi kiến thức): [BAO_CAO_BUOI2.md](BAO_CAO_BUOI2.md)

**Kỹ thuật đã thực hành:**

- HTML5 ngữ nghĩa: `section` + `aria-labelledby`, `header` của khu vực, danh sách `ul` > `li` > `article`, nút chỉ có biểu tượng dùng `aria-label`.
- CSS selector: element, class, con cháu (`.btn-fav svg`), con trực tiếp (`.product-grid > li`), kề cạnh (`input:checked + label`), pseudo-class.
- Box Model: đặt lại `margin`/`padding` mặc định của `ul`, padding và gap trong thẻ theo kích thước màn hình.
- Flexbox: hàng nút `.product-buy` (`display: flex`, `justify-content`, `align-items`, `gap`, `flex: 1` / `flex: 0 0 44px`).
- CSS Grid: lưới 2/3/4 cột với `repeat(N, minmax(0, 1fr))`, ảnh `aspect-ratio` + `object-fit: cover`.
- Hover/focus: `transition`, `:hover`, `:focus-visible`, `prefers-reduced-motion`.

**Những thay đổi đã thực hiện:**

| Vấn đề | Thay đổi |
|---|---|
| 8 sản phẩm không được đánh dấu là danh sách; tiêu đề nằm ngoài `section` | Đổi sang `ul` > `li` > `article`; tiêu đề vào `header` trong `section` |
| Chỉ có 1 nút thao tác | Thêm hàng nút Flexbox: "Thêm vào giỏ" + "Yêu thích" |
| Nút đổi màu tức thì; quy tắc giảm chuyển động nhắc tới `transition` không tồn tại | Thêm `transition` cho nút |
| Nhấn Tab thì nút bị đổi góc bo 8px → 4px | Chỉ bo góc viền focus cho liên kết |
| *(tự phát hiện)* Chữ "Thêm vào giỏ" xuống 2 dòng ở 390 px | Thu nhỏ padding/cỡ chữ trên điện thoại; `line-height: 1.2` cho máy 360–375 px |

**Trước và sau (390 px):**

| Trước | Sau |
|---|---|
| ![Trước](screenshots/the-sp-truoc-390.png) | ![Sau](screenshots/the-sp-sau-390.png) |

Ảnh toàn trang: [`screenshots/`](screenshots/) (`truoc-*.png` và `sau-*.png` ở 1366, 768, 390 px).

**Kiểm thử:** đạt 6/7 mục, mục "Liên kết hoạt động" đạt một phần vì liên kết sản phẩm và giỏ hàng vẫn là `#` (chưa có trang chi tiết). Chi tiết ở mục 8 của [BAO_CAO_BUOI2.md](BAO_CAO_BUOI2.md).

**Công cụ AI:** Claude Code trong VS Code. Các kết quả của AI được đo lại ở 5 chiều rộng màn hình; hai lần kiểm tra ban đầu của AI cho kết quả sai (ảnh chụp tràn ngang giả, phép đo chiều cao nút) và đã được sửa. Prompt và chi tiết: phần "Buổi 2" trong [AI_USAGE.md](AI_USAGE.md).

**Repository:** https://github.com/minhnguyet17/ecommerce-ui-improvement · **Trang demo:** https://minhnguyet17.github.io/ecommerce-ui-improvement/
