# AI Usage Log

## 1. Công cụ AI

Tên công cụ: **Claude** (Anthropic), dùng trong ứng dụng Claude (chế độ Cowork, có trình duyệt tích hợp để mở website).

## 2. Mục đích sử dụng

- **Nhiệm vụ 1–2:** phân tích các khu vực giao diện của yody.vn theo Prompt 1; hỗ trợ thao tác khảo sát trên website thật; đối chiếu kết quả AI với thực tế.
- **Nhiệm vụ 3:** đề xuất phương án thiết kế (Prompt 5.2); tạo mã HTML/CSS và 8 ảnh minh họa SVG (Prompt 5.3); giải thích cách chạy và những điểm cần kiểm tra.
- **Nhiệm vụ 4:** hướng dẫn từng bước cài Git, tạo repository, đưa mã nguồn lên GitHub và bật GitHub Pages.

## 3. Prompt đã sử dụng

### Prompt 1 – Phân tích website (18/10/2026)

```text
Bạn là chuyên gia phân tích nghiệp vụ và thiết kế trải nghiệm người dùng
cho website thương mại điện tử.

Tôi đang khảo sát website: YODY – https://yody.vn/

Hãy giúp tôi lập bảng phân tích các khu vực:
1. Trang chủ.
2. Danh mục sản phẩm.
3. Chi tiết sản phẩm.
4. Tìm kiếm.
5. Giỏ hàng.

Với mỗi khu vực, hãy nêu:
- Mục đích của chức năng.
- Thành phần giao diện cần có.
- Điểm thuận tiện đối với khách hàng.
- Một vấn đề có thể phát sinh.
- Một đề xuất cải tiến.

Không khẳng định những tính năng chưa được kiểm chứng.
Phân biệt rõ nhận xét dựa trên quan sát và đề xuất của AI.
```

Cách chạy: gửi trong **một phiên Claude riêng, không cho AI truy cập web**, để kết quả của AI tách bạch với khảo sát thực tế trên website.

### Prompt 5.2 – Nhờ AI đề xuất giao diện

```text
Tôi đang thực hiện bài tập phát triển giao diện website thương mại điện tử
bằng HTML5 và CSS3.

Tôi muốn cải tiến khu vực: thẻ sản phẩm và lưới danh sách sản phẩm (trang danh mục / kết quả tìm kiếm) của website thời trang YODY (yody.vn). Hiện trạng tôi đã khảo sát: tên sản phẩm trên thẻ bị cắt còn 1 dòng nên khó phân biệt các mẫu na ná nhau; thẻ không có nút thao tác, muốn mua phải mở trang chi tiết và kéo xuống mới thấy nút "Thêm vào giỏ"; nhãn % giảm nằm ở góc ảnh, tách khỏi giá. Tôi muốn thẻ mới có: tên hiển thị 2 dòng, khối giá gồm giá khuyến mãi – giá gốc – % giảm – số tiền tiết kiệm, chọn nhanh size và nút "Thêm vào giỏ" ngay trên thẻ.

Đối tượng sử dụng: khách hàng mua sắm trực tuyến tại Việt Nam.

Hãy đề xuất:
1. Bố cục giao diện.
2. Các thành phần HTML cần sử dụng.
3. Cách tổ chức CSS.
4. Cách hiển thị trên máy tính và điện thoại.
5. Những điểm cần kiểm tra về khả năng sử dụng.

Trước tiên, hãy giải thích phương án thiết kế.
Chưa tạo toàn bộ mã nguồn cho đến khi tôi yêu cầu.
```

### Prompt 5.3 – Tạo mã nguồn

```text
Dựa trên phương án đã thống nhất, hãy tạo một trang giao diện
thương mại điện tử bằng HTML5 và CSS3.

Yêu cầu:
- Giao diện có tiêu đề và khu vực sản phẩm.
- Có tối thiểu 4 sản phẩm mẫu.
- Mỗi sản phẩm có hình ảnh, tên, giá và nút thao tác.
- Bố cục phù hợp với màn hình máy tính và điện thoại.
- Mã HTML có cấu trúc rõ ràng.
- CSS được tách thành file riêng.
- Không sử dụng backend hoặc cơ sở dữ liệu.
- Không đưa thư viện hoặc thành phần không cần thiết vào dự án.

Giải thích cách chạy trang web và những phần tôi cần kiểm tra.
```

## 4. Kết quả AI đề xuất

**Prompt 1.** AI nói rõ không truy cập được yody.vn, nên gắn nhãn cho từng nhận định: *[Chung]* (kiến thức chung về TMĐT), *[Cần kiểm chứng]* (giả thuyết về YODY), *[Đề xuất AI]*. Tóm tắt:

| Khu vực | Vấn đề AI dự đoán | Đề xuất của AI |
|---|---|---|
| Trang chủ | Banner lớn chiếm gần hết màn hình đầu; ảnh nặng làm tải chậm trên 4G | Giới hạn số slide, đưa lối tắt danh mục lên trên, nén ảnh WebP/AVIF và lazy-load |
| Danh mục | Bấm Back bị mất bộ lọc và vị trí cuộn | Lưu bộ lọc/sắp xếp vào URL, khôi phục vị trí cuộn |
| Chi tiết SP | Bảng size chung chung, không theo phom → chọn sai size | Công cụ gợi ý size theo từng sản phẩm, thông số người mẫu |
| Tìm kiếm | Gõ không dấu, gõ sai, dùng từ địa phương → ít hoặc không có kết quả | Hỗ trợ không dấu, tìm gần đúng, từ điển đồng nghĩa |
| Giỏ hàng | Phí vận chuyển/điều kiện voucher chỉ hiện ở bước cuối → khách "sốc giá" | Ước tính phí ship ngay ở giỏ, thanh tiến độ freeship, gợi ý voucher |

<details>
<summary>Xem nguyên văn câu trả lời của AI cho Prompt 1</summary>

## Bảng phân tích 5 khu vực chức năng – Website YODY (yody.vn)

> **Lưu ý trước khi dùng:** Trong cuộc trò chuyện này mình **không truy cập được yody.vn**. Vì vậy **không có nhận xét nào dưới đây là do mình trực tiếp quan sát**. Nội dung dựa trên kiến thức chung về website thương mại điện tử thời trang và các nguyên tắc UX. Giao diện thật của YODY có thể khác hoặc đã thay đổi. Mỗi dòng đều có nhãn để bạn biết phần nào dùng được ngay và phần nào bạn phải tự kiểm tra.

**Quy ước nhãn**

| Nhãn | Ý nghĩa | Cách dùng trong báo cáo |
|---|---|---|
| **[Chung]** | Kiến thức chung về TMĐT/UX, đúng với hầu hết website thời trang | Trình bày như tiêu chí tham chiếu, **không** phải mô tả hiện trạng của YODY |
| **[Cần kiểm chứng]** | Giả thuyết của AI về YODY, chưa được xác nhận | Chỉ ghi thành "nhận xét dựa trên quan sát" sau khi bạn tự thao tác và chụp màn hình |
| **[Đề xuất AI]** | Ý tưởng cải tiến do AI đưa ra | Ghi rõ là đề xuất. Trước đó, kiểm tra xem YODY đã có tính năng này chưa |

Lưu ý: mục "điểm thuận tiện" mô tả lợi ích khách hàng nhận được **nếu** website có tính năng tương ứng.

### 1. Trang chủ

| Tiêu chí | Phân tích | Nhãn |
|---|---|---|
| **Mục đích** | Tạo ấn tượng về thương hiệu ngay lần đầu truy cập. Dẫn khách nhanh tới danh mục, chương trình khuyến mãi và sản phẩm nổi bật. Thể hiện các cam kết (giao hàng, đổi trả, thanh toán) để tạo niềm tin. | **[Chung]** |
| **Thành phần giao diện cần có** | (1) Header: logo, menu danh mục (ví dụ Nam/Nữ/Trẻ em), ô tìm kiếm, tài khoản, biểu tượng giỏ hàng có hiện số lượng; (2) Banner chính/khuyến mãi; (3) Lối tắt vào danh mục bằng hình ảnh; (4) Khối sản phẩm: mới về, bán chạy, đang giảm giá; (5) Dải chính sách: giao hàng, đổi trả, thanh toán; (6) Footer: liên hệ, hệ thống cửa hàng, chính sách, mạng xã hội; (7) Kênh hỗ trợ: chat/hotline. | **[Chung]** |
| **Điểm thuận tiện** | Khách thấy ngay ưu đãi và vào được danh mục cần tìm chỉ sau 1–2 lần nhấp. Khách mới đọc được chính sách đổi trả ngay từ đầu nên yên tâm hơn khi mua online. | **[Cần kiểm chứng]** |
| **Vấn đề có thể phát sinh** | Trang chủ dài, nhiều slider/banner có ảnh dung lượng lớn → tải chậm trên điện thoại dùng 4G. Banner chiếm gần hết màn hình đầu tiên nên lối vào danh mục và sản phẩm bị đẩy xuống dưới. | **[Cần kiểm chứng]** |
| **Đề xuất cải tiến** | Ưu tiên nội dung ở màn hình đầu tiên: giới hạn số slide, đặt lối tắt danh mục ngay dưới banner. Nén ảnh sang WebP/AVIF và chỉ tải ảnh phía dưới khi khách cuộn tới (lazy-load). *Đo hiệu quả:* chỉ số LCP, tức thời gian hiển thị phần nội dung lớn nhất (mục tiêu ≤ 2,5 giây), và tỷ lệ thoát ở trang chủ. | **[Đề xuất AI]** |

**Cách kiểm chứng:** Mở trang chủ trên điện thoại và ghi lại những gì hiện ở màn hình đầu tiên. Kiểm tra yody.vn bằng PageSpeed Insights (pagespeed.web.dev), chụp lại kết quả bản di động.

### 2. Danh mục sản phẩm

| Tiêu chí | Phân tích | Nhãn |
|---|---|---|
| **Mục đích** | Giúp khách duyệt và thu hẹp lựa chọn trong một nhóm sản phẩm (ví dụ: áo polo nam). So sánh nhanh giá, màu, ưu đãi để chọn ra sản phẩm muốn xem chi tiết. | **[Chung]** |
| **Thành phần giao diện cần có** | (1) Breadcrumb (đường dẫn phân cấp), tên danh mục, số lượng sản phẩm; (2) Bộ lọc: size, màu, khoảng giá, chất liệu, kiểu dáng; (3) Sắp xếp: mới nhất, bán chạy, giá tăng/giảm; (4) Thẻ sản phẩm: ảnh, tên, giá bán, giá gốc/% giảm, ô màu (swatch), nhãn "Mới"/"Bán chạy"; (5) Danh sách bộ lọc đang áp dụng và nút "Xóa lọc"; (6) Phân trang hoặc nút "Xem thêm"; (7) Trên mobile: bộ lọc dạng bảng trượt có nút "Áp dụng". | **[Chung]** |
| **Điểm thuận tiện** | Lọc theo size và khoảng giá giúp khách chỉ xem những món hợp với mình. Giá và màu hiện ngay trên thẻ sản phẩm nên khách không phải mở từng trang chi tiết. | **[Cần kiểm chứng]** |
| **Vấn đề có thể phát sinh** | Khách lọc, cuộn xuống, mở một sản phẩm rồi bấm "Quay lại" thì bộ lọc bị xóa hoặc trang nhảy về đầu danh sách. Khách phải lọc và cuộn lại từ đầu nên dễ bỏ cuộc. Lỗi này hay gặp ở trang dùng nút "Xem thêm" hoặc cuộn vô hạn. | **[Cần kiểm chứng]** |
| **Đề xuất cải tiến** | Lưu trạng thái lọc/sắp xếp vào URL (ví dụ minh họa: `?size=L&mau=den&sap-xep=ban-chay`) và khôi phục vị trí cuộn khi khách quay lại. Khách cũng có thể gửi link danh sách đã lọc cho người khác. *Đo hiệu quả:* số sản phẩm được xem mỗi phiên, tỷ lệ thoát ở trang danh mục. | **[Đề xuất AI]** |

**Cách kiểm chứng:** Vào một danh mục → lọc size và màu → cuộn xuống → mở 1 sản phẩm → bấm Back. Xem bộ lọc và vị trí cuộn có được giữ không, và URL có thay đổi khi lọc không.

### 3. Chi tiết sản phẩm

| Tiêu chí | Phân tích | Nhãn |
|---|---|---|
| **Mục đích** | Cung cấp đủ thông tin để khách quyết định mua (hình ảnh, giá, chất liệu, size, đánh giá, chính sách) và thực hiện hành động chính: thêm vào giỏ hoặc mua ngay. | **[Chung]** |
| **Thành phần giao diện cần có** | (1) Bộ ảnh nhiều góc, phóng to được, có ảnh người mẫu mặc thực tế; (2) Tên, mã sản phẩm, giá bán/giá gốc; (3) Chọn màu và size, báo rõ biến thể đã hết hàng; (4) Bảng size/hướng dẫn chọn size; (5) Nút "Thêm vào giỏ" và "Mua ngay" (trên mobile nên cố định ở cạnh dưới màn hình); (6) Mô tả chất liệu, form dáng, cách bảo quản; (7) Chính sách giao hàng, đổi trả; (8) Đánh giá, hỏi đáp; (9) Sản phẩm liên quan/gợi ý phối đồ. | **[Chung]** |
| **Điểm thuận tiện** | Khách có đủ thông tin trên một trang, chọn màu/size và thêm vào giỏ mà không phải rời trang. Bảng size giúp khách bớt lo chọn sai cỡ. | **[Cần kiểm chứng]** |
| **Vấn đề có thể phát sinh** | Bảng size chung chung, chỉ dựa trên chiều cao/cân nặng, trong khi mỗi sản phẩm có form khác nhau (ôm, suông, oversize). Khách chọn sai size → phải đổi trả, tốn chi phí cho cả hai bên và giảm mức hài lòng. | **[Cần kiểm chứng]** |
| **Đề xuất cải tiến** | Công cụ "Gợi ý size" riêng cho từng sản phẩm: khách nhập chiều cao, cân nặng, kiểu mặc ưa thích (vừa/rộng) → hệ thống gợi ý size. Kèm thông số người mẫu (cao, nặng, mặc size gì) và thống kê từ đánh giá ("đa số thấy vừa"/"hơi rộng"). *Đo hiệu quả:* tỷ lệ đổi trả do sai size, tỷ lệ thêm vào giỏ từ trang chi tiết. | **[Đề xuất AI]** |

**Cách kiểm chứng:** Mở 2–3 sản phẩm khác loại (áo, quần, áo khoác). Xem mỗi loại có bảng size riêng không, có công cụ tư vấn size không, size hết hàng hiển thị thế nào, và ảnh có đổi theo màu đã chọn không.

### 4. Tìm kiếm

| Tiêu chí | Phân tích | Nhãn |
|---|---|---|
| **Mục đích** | Giúp khách đã biết mình cần gì tìm tới sản phẩm nhanh nhất, không phải duyệt qua nhiều tầng danh mục. | **[Chung]** |
| **Thành phần giao diện cần có** | (1) Ô tìm kiếm dễ thấy trên header (trên mobile nên luôn hiển thị ở đầu trang); (2) Gợi ý tự động khi gõ: từ khóa, danh mục, sản phẩm kèm ảnh và giá; (3) Từ khóa phổ biến, lịch sử tìm kiếm; (4) Trang kết quả: số kết quả, bộ lọc và sắp xếp như trang danh mục; (5) Trang "không có kết quả": gợi ý từ khóa gần đúng, sản phẩm bán chạy. | **[Chung]** |
| **Điểm thuận tiện** | Gợi ý tức thì giúp khách không phải gõ hết từ khóa mà vào thẳng sản phẩm. Khách muốn mua lại mẫu quen có thể tìm ngay theo tên hoặc mã sản phẩm. | **[Cần kiểm chứng]** |
| **Vấn đề có thể phát sinh** | Nhiều người gõ không dấu, gõ sai hoặc dùng từ theo vùng miền ("ao polo", "áo phông"/"áo thun", "quần bò"/"quần jean"). Nếu công cụ chỉ khớp đúng từng chữ, kết quả sẽ ít hoặc không có. Khách tưởng cửa hàng không có hàng và rời đi. | **[Cần kiểm chứng]** |
| **Đề xuất cải tiến** | Chuẩn hóa tìm kiếm tiếng Việt: hỗ trợ gõ không dấu, tìm gần đúng khi gõ sai (fuzzy search), thêm từ điển đồng nghĩa theo vùng miền. Định kỳ lấy danh sách từ khóa "0 kết quả" để bổ sung vào từ điển. *Đo hiệu quả:* tỷ lệ tìm kiếm không có kết quả, tỷ lệ nhấp vào sản phẩm sau khi tìm. | **[Đề xuất AI]** |

**Cách kiểm chứng:** Lần lượt gõ "áo polo nam", "ao polo nam", "polo nm" (cố tình gõ sai), "áo phông", "quần bò" và một mã sản phẩm lấy từ trang chi tiết. So sánh số lượng và độ liên quan của kết quả, chụp màn hình từng lần.

### 5. Giỏ hàng

| Tiêu chí | Phân tích | Nhãn |
|---|---|---|
| **Mục đích** | Cho khách xem lại, điều chỉnh sản phẩm đã chọn và biết tổng chi phí trước khi thanh toán. Đây là bước chốt giữa "xem hàng" và "đặt hàng". | **[Chung]** |
| **Thành phần giao diện cần có** | (1) Thông báo hoặc giỏ hàng thu gọn (mini-cart) ngay khi thêm sản phẩm; (2) Danh sách sản phẩm: ảnh, tên, màu/size (cho phép đổi), đơn giá, nút tăng/giảm số lượng, thành tiền, nút xóa; (3) Ô nhập mã giảm giá/chọn voucher; (4) Tóm tắt đơn: tạm tính, giảm giá, phí vận chuyển dự kiến, tổng cộng; (5) Nút "Thanh toán" nổi bật và nút "Tiếp tục mua sắm"; (6) Cảnh báo khi sản phẩm hết hàng hoặc đổi giá; (7) Gợi ý sản phẩm mua kèm. | **[Chung]** |
| **Điểm thuận tiện** | Khách đổi size/màu, sửa số lượng hoặc xóa sản phẩm ngay trong giỏ mà không phải quay lại trang chi tiết. Khách thấy tổng tiền trước khi nhập thông tin giao hàng. | **[Cần kiểm chứng]** |
| **Vấn đề có thể phát sinh** | Phí vận chuyển hoặc điều kiện áp dụng voucher chỉ hiện ra ở bước cuối → khách bị "sốc giá" và bỏ giỏ. Các khảo sát về bỏ giỏ hàng, ví dụ của Baymard Institute, thường xếp chi phí phát sinh vào nhóm lý do hàng đầu. Nếu trích dẫn, hãy kiểm tra số liệu của năm mới nhất. | **[Cần kiểm chứng]** |
| **Đề xuất cải tiến** | Cho khách thấy rõ chi phí ngay tại giỏ: ước tính phí vận chuyển theo khu vực; thanh tiến độ "Còn thiếu X đ để được miễn phí vận chuyển" (chỉ áp dụng nếu YODY có chính sách miễn phí theo ngưỡng đơn); tự gợi ý voucher dùng được và nêu rõ lý do khi mã không áp dụng được. *Đo hiệu quả:* tỷ lệ bỏ giỏ, tỷ lệ chuyển từ giỏ hàng sang thanh toán. | **[Đề xuất AI]** |

**Cách kiểm chứng (không cần đặt hàng thật):** Thêm 2 sản phẩm vào giỏ khi chưa đăng nhập. Thử đổi size, đổi số lượng và nhập một mã giảm giá sai. Ghi lại phí vận chuyển xuất hiện ở bước nào và thông báo lỗi trông ra sao. Nếu có tài khoản, đăng nhập rồi xem giỏ hàng còn giữ sản phẩm không.

### Gợi ý khi đưa vào báo cáo

- **Tách bạch nguồn nhận xét:** thêm vào bảng của bạn cột "Nguồn", ghi *Quan sát (ảnh số…)* hoặc *Đề xuất – tham khảo AI*. Làm theo quy định của giảng viên về việc sử dụng AI.
- **Bằng chứng cho quan sát:** mỗi nhận xét nên kèm ảnh chụp màn hình, ngày giờ khảo sát, thiết bị/trình duyệt và thao tác đã thực hiện.
- **Nếu kiểm tra mà vấn đề không xảy ra:** có thể giữ nó dưới dạng "rủi ro tiềm ẩn", nhưng không ghi là lỗi hiện có của YODY.
- **Nếu YODY đã có tính năng nằm trong mục [Đề xuất AI]:** ghi nhận đó là điểm mạnh (nhận xét quan sát) và chọn một đề xuất khác.

Nếu bạn gửi ảnh chụp màn hình của 5 khu vực, mình có thể giúp chuyển các mục **[Cần kiểm chứng]** thành nhận xét dựa trên quan sát. Mình cũng có thể gộp 5 bảng thành một bảng tổng hợp để bạn dán vào báo cáo.

</details>

**Prompt 5.2 – phương án thiết kế.** AI đề xuất:
- Thiết kế mobile-first. Mỗi thẻ thành một "khối mua nhanh": ảnh 3:4 → tên tối đa 2 dòng → khối giá (giá khuyến mãi, % giảm, giá gốc dùng `<del>`, dòng "Tiết kiệm") → chọn size → nút "Thêm vào giỏ" luôn nằm ở đáy thẻ.
- HTML: `header`, `main`, `section` cho lưới, `article` cho từng sản phẩm, `h2` cho tên, `fieldset` + `legend` + `input type="radio"` + `label` để chọn size (không cần JavaScript), `button type="button"`.
- CSS: một file chia 7 mục; biến trong `:root`; tên class kiểu BEM; Flexbox trong thẻ, CSS Grid cho lưới; bộ chọn `:has()` đổi màu nút khi đã chọn size.
- Responsive: 2 cột (dưới 600px), 3 cột (600–1023px), 4 cột (từ 1024px).
- 8 điểm cần kiểm tra khả năng sử dụng: tên, giá, chọn size bằng bàn phím, vùng bấm ≥ 44px, viền focus, độ tương phản, 3 kích thước màn hình, alt của ảnh.
- Dùng tên cửa hàng giả định "Demo Fashion" và ảnh tự vẽ để không bị nhầm với website thật của YODY.

**Prompt 5.3 – mã nguồn.** AI tạo `index.html` (8 sản phẩm mẫu: 5 có giảm giá, 3 giá thường, 3 sản phẩm có size hết hàng), `css/style.css` (7 mục có chú thích) và 8 ảnh minh họa SVG trong `images/`; hướng dẫn chạy bằng Live Server và liệt kê những điểm cần kiểm tra.

## 5. Kiểm tra và điều chỉnh

### 5.1 Đối chiếu kết quả AI với website thật (kiểm tra ngày 18/10/2026)

Quy ước: **Giữ** = đúng với website · **Sửa** = đúng một phần, đã ghi lại cho chính xác · **Loại bỏ** = sai, YODY đã có sẵn, hoặc chưa có bằng chứng.

| Khu vực | Nhận định / đề xuất của AI | Kết quả kiểm tra trên yody.vn | Xử lý |
|---|---|---|---|
| Trang chủ | Header có menu, tìm kiếm, tài khoản, giỏ hàng hiện số lượng | Đúng; menu "Danh mục" nhiều cấp Nam/Nữ/Trẻ em | Giữ |
| Trang chủ | Có khối lối tắt danh mục bằng hình ảnh | Trang chủ không có khối này; danh mục nằm trong menu "Danh mục" | Loại bỏ |
| Trang chủ | Có dải chính sách giao hàng – đổi trả – thanh toán | Trang chủ chỉ có dải "đổi trả trong 30 ngày"; giao hàng/freeship ghi ở trang sản phẩm và giỏ hàng | Sửa |
| Trang chủ | Banner chiếm gần hết màn hình đầu | Đúng một phần: khoảng 500/812 px (≈60%) trên điện thoại | Sửa (ghi số liệu) |
| Trang chủ | Ảnh nặng làm tải chậm trên 4G | Chưa đo tốc độ, không có bằng chứng | Loại bỏ |
| Trang chủ | Đề xuất nén ảnh WebP và lazy-load | Ảnh sản phẩm đã dùng `.webp` và `loading="lazy"` | Loại bỏ (đã có) |
| Danh mục | Có lọc theo size, màu, khoảng giá, kiểu dáng | Đúng; có thêm Giới tính, Loại SP, Dòng SP | Giữ |
| Danh mục | Có lọc theo chất liệu | Không có | Loại bỏ |
| Danh mục | Sắp xếp: mới nhất, bán chạy, giá tăng/giảm | Có Ưu đãi, Mới nhất, Giá (tăng/giảm); không có "Bán chạy" | Sửa |
| Danh mục | Thẻ sản phẩm có nhãn "Mới"/"Bán chạy" | Không thấy; thẻ chỉ có nhãn % giảm | Loại bỏ |
| Danh mục | Bấm Back bị mất bộ lọc | Sai: bộ lọc nằm trên URL, Back quay lại đúng `?sizes=6&sort=price_asc` | Loại bỏ |
| Danh mục | Đề xuất lưu bộ lọc vào URL | YODY đã làm | Loại bỏ (đã có) |
| Chi tiết SP | Có bảng size, chọn màu/size, mô tả chất liệu, chính sách giao/đổi | Đúng | Giữ |
| Chi tiết SP | Có nút "Mua ngay", cố định ở đáy màn hình điện thoại | Chỉ có "Thêm vào giỏ", không cố định khi cuộn | Sửa → ghi thành vấn đề thật |
| Chi tiết SP | Có đánh giá và hỏi đáp | Có "Câu hỏi thường gặp"; không thấy đánh giá (đã xem 2 sản phẩm) | Sửa |
| Chi tiết SP | Bảng size chung chung, không theo phom | Đúng một phần: bảng chung theo Nam/Nữ/Trẻ em, có chiều cao, cân nặng, vai, ngực | Giữ (ghi rõ phạm vi) |
| Chi tiết SP | Đề xuất gợi ý size theo từng sản phẩm | Trang chưa có | Giữ làm đề xuất |
| Tìm kiếm | Gợi ý khi gõ có sản phẩm kèm ảnh, giá | Đúng, kèm số kết quả và "Xem tất cả" | Giữ |
| Tìm kiếm | Gợi ý từ khóa, danh mục, từ khóa phổ biến | Không có; chỉ có "Lịch sử tìm kiếm" | Loại bỏ |
| Tìm kiếm | Gõ không dấu cho ít kết quả | Sai: "ao polo" và "áo polo" đều 145 kết quả | Loại bỏ |
| Tìm kiếm | Từ địa phương không ra kết quả | Sai: "quần bò" ra 82 sản phẩm jeans | Loại bỏ |
| Tìm kiếm | Gõ sai thì không có kết quả | Đúng: "polo nm" ra 0 kết quả, không gợi ý | Giữ |
| Tìm kiếm | Trang 0 kết quả có gợi ý từ gần đúng, sản phẩm bán chạy | Không có, chỉ có câu thông báo | Sửa → ghi thành vấn đề thật |
| Giỏ hàng | Có thông báo/mini-cart khi thêm sản phẩm | Đúng: popup "Đã thêm vào giỏ hàng" | Giữ |
| Giỏ hàng | Đổi màu/size, số lượng, xóa ngay trong giỏ | Đúng: hộp "Cập nhật sản phẩm" | Giữ |
| Giỏ hàng | Có ô nhập mã giảm giá trong giỏ | Không thấy trong trang giỏ hàng | Loại bỏ |
| Giỏ hàng | Tóm tắt có dòng phí vận chuyển dự kiến | Không có dòng phí ship; Tạm tính lệch 20.000đ không giải thích | Sửa → ghi thành vấn đề thật |
| Giỏ hàng | Thanh tiến độ freeship (nếu có ngưỡng) | YODY có ngưỡng 498k nhưng chưa có thanh tiến độ | Giữ làm đề xuất |
| Giỏ hàng | Số liệu của Baymard về bỏ giỏ | Không tự kiểm chứng được | Loại bỏ |

### 5.2 Nhận xét bổ sung (AI không nêu, phát hiện khi khảo sát thật)

- Bộ lọc Size trộn size áo, quần, giày và các mã khác trong một danh sách, thứ tự lộn xộn.
- Tên sản phẩm trên chỉ hiển thị 1 dòng và … nên bị cắt; thẻ không có nút thao tác như mua hay hiện thêm thông tin size số, cần bấm vào.
- Ba nút nổi (quà tặng nhảy liên tục, nút quét, "Danh mục") che nội dung trên điện thoại.
- Mô tả sản phẩm nhắc nút "Mua ngay" nhưng trang không có nút này, chỉ có “Thêm vào giỏ”
- Điểm tốt: size đã lọc được chọn sẵn khi mở trang chi tiết.
- Đăng ký chỉ được dùng Email/ Google, không có số điện thoại => Bất tiện
- Phần Ưu đãi trong danh mục nhưng bấm vào các sản phẩm không hiện giá ưu đãi, chỉ có giá gốc


### 5.3 Sinh viên tự kiểm tra lại

- [x] Mở trang chủ trên điện thoại: banner chiếm phần lớn màn hình đầu, có các nút nổi
- [x] Danh mục Nam → Lọc → Size: danh sách size bị trộn lẫn
- [x] Tìm "polo nm" ra 0 kết quả; tìm "ao polo" ra kết quả như "áo polo"
- [x] Trang chi tiết: nút "Thêm vào giỏ" có cố định khi cuộn không; có phần đánh giá không

### 5.4 Nhiệm vụ 3 – kiểm tra và điều chỉnh

- Chạy trang bằng Live Preview trong VS Code; kiểm tra bằng Chrome DevTools (chế độ giả lập màn hình) ở 375px, 768px và 1280px: số cột 2/3/4, không tràn ngang, ảnh không méo; chọn size thì nút đổi màu, size hết hàng không chọn được.
- **Tự phát hiện:** ở 375px, tên sản phẩm dài vẫn bị cắt ở dòng thứ 2 (VD "Áo Polo Nam Cổ Bo Kẻ Thoáng Khí Dáng…"). Nguyên nhân: phương án của AI giới hạn tên 2 dòng cho mọi kích thước, trong khi thẻ trên điện thoại chỉ rộng khoảng 150px.
- **Đã sửa** trong `css/style.css`:

  ```css
  /* Điện thoại: tối đa 3 dòng */
  .product-card__name {
    -webkit-line-clamp: 3;
    line-clamp: 3;
    min-height: 4.2em;   /* 3 dòng × line-height 1.4 */
  }

  /* Từ 600px trở lên: 2 dòng là đủ */
  @media (min-width: 600px) {
    .product-card__name {
      -webkit-line-clamp: 2;
      line-clamp: 2;
      min-height: 2.8em;
    }
  }
  ```

- Thêm thuộc tính chuẩn `line-clamp` bên cạnh `-webkit-line-clamp`, nhờ vậy hết cảnh báo của VS Code trong bảng Problems.
- Điền họ tên, MSSV vào footer của `index.html`.

## 6. Phần tôi hiểu và có thể giải thích

| Thành phần | Vai trò |
|---|---|
| `header`, `main`, `section`, `article`, `footer` | Thẻ HTML ngữ nghĩa chia trang thành đầu trang, nội dung chính, khu vực danh sách, từng sản phẩm, chân trang |
| `h1` (tiêu đề trang), `h2` (tên sản phẩm) | Thứ bậc tiêu đề rõ ràng cho người đọc và công cụ tìm kiếm |
| `<del>` và lớp `.sr-only` | `del` thể hiện giá gốc đã bị thay; chữ ẩn "Giá gốc:", "Giá khuyến mãi:" giúp trình đọc màn hình đọc đúng nghĩa |
| `fieldset` + `legend` + `input type="radio"` + `label for` | Nhóm chọn size: các radio cùng `name` nên chỉ chọn được 1 size; bấm vào chữ size là chọn; `disabled` cho size hết hàng |
| `button type="button"` | Nút thao tác; hiện chỉ là giao diện vì bài tập không có backend |
| Biến CSS trong `:root` | Khai báo màu, bo góc, khoảng cách một lần; sửa một chỗ là cả trang thay đổi |
| CSS Grid `repeat(2, minmax(0, 1fr))` | Lưới 2 cột chia đều; `minmax(0, 1fr)` ngăn chữ dài làm tràn cột |
| Media query `min-width: 600px` và `1024px` | Mobile-first: mặc định 2 cột, từ 600px lên 3 cột, từ 1024px lên 4 cột |
| Flexbox `flex-direction: column` + `margin-top: auto` | Xếp nội dung thẻ theo chiều dọc và đẩy phần chọn size cùng nút xuống đáy, nên nút các thẻ thẳng hàng |
| `aspect-ratio: 3 / 4` + `object-fit: cover` | Giữ ảnh đúng tỉ lệ, không méo ở mọi kích thước |
| `-webkit-line-clamp` + `min-height` | Giới hạn số dòng của tên, dư thì hiện "…"; giữ chỗ cố định để các thẻ đều nhau |
| `input:checked + label`, `input:disabled + label` | Bộ chọn kề cạnh (`+`): tô ô size theo trạng thái của nút radio đứng ngay trước nó |
| `.product-card:has(input:checked) .btn-add` | Khi trong thẻ có size được chọn thì đổi nút sang màu đậm và ẩn dòng nhắc, không cần JavaScript |
| `:focus-visible` | Hiện viền xanh khi dùng bàn phím, giúp người không dùng chuột biết mình đang ở đâu |
