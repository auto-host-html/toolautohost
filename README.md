# 📝 KỊCH BẢN THUYẾT TRÌNH
## Portfolio Cá Nhân — Tin Học Ứng Dụng

> **Thời lượng ước tính:** 8–12 phút  
> **Đối tượng:** Giảng viên và các bạn sinh viên  
> **Ghi chú:** Các chỗ đánh dấu `[THAO TÁC]` là lúc bạn thực hiện demo trực tiếp trên màn hình.

---

## PHẦN 1 — MỞ ĐẦU (1–2 phút)

Kính chào thầy/cô và các bạn.

Hôm nay em xin trình bày về **Portfolio cá nhân** mà em đã xây dựng trong quá trình học môn Tin Học Ứng Dụng. Đây không chỉ đơn thuần là một trang web tĩnh mà là một **hệ thống quản trị nội dung hoàn chỉnh**, cho phép người dùng tùy biến mọi thứ trực tiếp trên trình duyệt mà không cần chạm vào source code.

Em sẽ trình bày theo hai phần chính:

1. **Quá trình xây dựng** — từ ý tưởng, công nghệ sử dụng đến thiết kế
2. **Hướng dẫn sử dụng** — demo trực tiếp các tính năng quản trị

---

## PHẦN 2 — QUÁ TRÌNH XÂY DỰNG (3–4 phút)

### 2.1. Ý tưởng và phong cách thiết kế

Ban đầu, em đã thiết kế trang web theo phong cách **glassmorphism** — với nền tối, gradient nhiều màu, các hiệu ứng mờ kính. Tuy nhiên, sau khi nghiên cứu thêm về xu hướng thiết kế hiện đại, em quyết định chuyển sang phong cách **Neobrutalism** — một trào lưu thiết kế web đang rất thịnh hành.

**Neobrutalism** được đặc trưng bởi:
- Tông màu **đen trắng** chủ đạo, triệt tiêu hoàn toàn gradient
- **Viền đen dày** (4px) bao quanh mọi thành phần
- **Đổ bóng cứng** (hard shadow) kiểu offset — ví dụ `12px 12px 0 0 #000` — tạo cảm giác các khối hộp "nổi" lên khỏi mặt phẳng
- **Không bo góc** — tất cả đều là góc vuông 90 độ
- Font chữ đậm, in hoa, mang đậm chất **in ấn truyền thống**

`[THAO TÁC: Mở trang web, cuộn chậm từ đầu đến cuối để giới thiệu tổng quan giao diện]`

### 2.2. Công nghệ sử dụng

Trang web được xây dựng hoàn toàn bằng **Front-end thuần túy**, không dùng framework:

| Công nghệ | Vai trò |
|---|---|
| **HTML5** | Cấu trúc trang, ngữ nghĩa (semantic) |
| **CSS3** | Thiết kế giao diện Neobrutalism |
| **JavaScript (Vanilla)** | Logic tương tác, quản trị nội dung |
| **localStorage** | Lưu trữ dữ liệu người dùng trực tiếp trên trình duyệt |
| **Google Fonts** | Noto Sans (body) + Space Grotesk (headings) |

Điểm đặc biệt: **toàn bộ dữ liệu** người dùng chỉnh sửa (tên, mô tả, ảnh, kỉ niệm, liên kết...) được lưu vào `localStorage` của trình duyệt, nghĩa là không cần server hay cơ sở dữ liệu. Khi cần triển khai lên internet, người dùng chỉ cần bấm nút **"Tải Source Code"** trong menu quản trị — hệ thống sẽ tự động nhúng toàn bộ dữ liệu đã chỉnh sửa vào source code và tải về.

### 2.3. Cấu trúc dự án

Dự án gồm **4 file chính**:

```
portfolio-project/
├── index.html        ← Cấu trúc HTML (596 dòng)
├── style.css         ← Style chính Neobrutalism (534 dòng)
├── additions.css     ← Style cho phần mở rộng: Kỉ niệm, Admin (473 dòng)
└── script.js         ← Toàn bộ logic JavaScript (560+ dòng)
```

### 2.4. Các phần chính của trang web

`[THAO TÁC: Cuộn đến từng phần khi giới thiệu]`

1. **Trang chủ (Hero)** — Lời chào, tên, mô tả ngắn, ảnh đại diện
2. **Giới thiệu (About)** — Thông tin cá nhân, ảnh giới thiệu, thống kê
3. **Liên kết (Quick Links)** — Kiểu Linktree/Beacon, dẫn nhanh đến từng bài tập
4. **Kỹ năng (Skills)** — 4 thẻ kỹ năng số chính
5. **Dự án (Projects)** — 6 bài tập với layout so le, có link đính kèm
6. **Kỉ niệm (Memories)** — Bộ sưu tập ảnh và câu chuyện, thêm/xóa tùy ý
7. **Tổng kết (Summary)** — Kinh nghiệm, kỹ năng phát triển, hướng đi tương lai, châm ngôn cá nhân

### 2.5. Các hiệu ứng nổi bật

- **Hình ảnh Grayscale**: Mọi hình ảnh mặc định ở chế độ đen trắng, chỉ hiện màu khi di chuột vào (hover)
- **Hiệu ứng nảy (Bounce)**: Các thẻ khi hover sẽ dịch chuyển lên 4px và bóng đổ dài ra, tạo cảm giác "vật lý"
- **Scroll Reveal**: Các phần nội dung sẽ từ từ hiện ra khi người dùng cuộn trang
- **Typing Effect**: Dòng mô tả ở trang chủ có hiệu ứng đánh máy
- **Pop-art Stripes**: Dự án chưa có ảnh sẽ hiển thị dải vằn vện đen trắng kiểu retro

`[THAO TÁC: Di chuột vào một thẻ dự án để demo hiệu ứng nảy, di chuột vào ảnh kỉ niệm để demo grayscale → color]`

---

## PHẦN 3 — HƯỚNG DẪN SỬ DỤNG & DEMO (4–5 phút)

### 3.1. Mở bảng quản trị

`[THAO TÁC: Click nút ⚙ ở góc phải dưới màn hình]`

Ở góc phải dưới màn hình có nút bánh răng ⚙. Khi bấm vào, bảng quản trị sẽ trượt ra từ bên phải. Bảng này có **6 tab** chức năng:

| Tab | Chức năng |
|---|---|
| **Avatar** | Tải ảnh đại diện lên |
| **Trang Chủ** | Chỉnh tên, lời chào, mô tả |
| **Giới Thiệu** | Tải ảnh giới thiệu, sửa châm ngôn, nội dung giới thiệu |
| **Bài Tập** | Gắn link cho từng bài tập (1–6) |
| **Liên Kết** | Thêm/xóa các nút Quick Link |
| **Kỉ Niệm** | Thêm/xóa/sửa thẻ kỉ niệm (tiêu đề, ngày, mô tả, ảnh URL) |

### 3.2. Demo: Đổi ảnh đại diện

`[THAO TÁC: Ở tab Avatar → Bấm "Nhấn để chọn ảnh đại diện" → Chọn ảnh từ máy]`

Ảnh sẽ được nén tự động và lưu vào localStorage. Ảnh đại diện sẽ cập nhật ngay lập tức ở cả trang chủ.

### 3.3. Demo: Chỉnh sửa Trang Chủ

`[THAO TÁC: Chuyển sang tab "Trang Chủ" → Đổi tên thành tên thật → Sửa mô tả → Bấm "Lưu Trang Chủ"]`

Sau khi bấm Lưu, nội dung trên trang web sẽ cập nhật ngay. Dữ liệu này được lưu lại, khi tải lại trang vẫn giữ nguyên.

### 3.4. Demo: Gắn link bài tập

`[THAO TÁC: Chuyển sang tab "Bài Tập" → Dán URL của bài tập vào ô tương ứng → Bấm "Lưu tất cả link bài tập"]`

Khi đã gắn link, nút "Xem chi tiết" ở mỗi dự án sẽ mở bài tập đó trong tab mới. Nếu chưa có link, nút sẽ hiển thị "Chưa có link · Nhấn ⚙ để thêm".

### 3.5. Demo: Quản lý Kỉ niệm

`[THAO TÁC: Chuyển sang tab "Kỉ Niệm"]`

- **Thêm kỉ niệm**: Bấm nút **"+ Thêm ảnh"** → Một thẻ mới xuất hiện trên trang web và trong danh sách quản trị
- **Sửa kỉ niệm**: Nhập tiêu đề, ngày tháng, mô tả, dán link ảnh → Bấm **"Lưu tất cả"**
- **Xóa kỉ niệm**: Bấm nút đỏ **"🗑 Xóa kỉ niệm này"** → Thẻ bị xóa ngay lập tức
- **Ảnh**: Dán URL ảnh từ Unsplash, Google Drive, hoặc bất kỳ nguồn nào

`[THAO TÁC: Demo thêm 1 kỉ niệm mới, dán link ảnh Unsplash, bấm Lưu, sau đó xóa nó]`

### 3.6. Demo: Xuất Source Code để triển khai

`[THAO TÁC: Cuộn xuống cuối bảng quản trị → Phần "📦 XUẤT & TRIỂN KHAI"]`

Khi bấm **"📥 Tải Source Code"**, hệ thống sẽ tải về 4 file:
- `index.html` (đã nhúng sẵn dữ liệu chỉnh sửa)
- `style.css`
- `additions.css`
- `script.js`

Bạn chỉ cần đẩy 4 file này lên **GitHub Pages**, **Cloudflare Pages**, hoặc **GitLab Pages** là có ngay một trang web portfolio cá nhân hoạt động trên internet thực tế.

---

## PHẦN 4 — KẾT LUẬN (1 phút)

Tóm lại, dự án Portfolio này không chỉ đáp ứng yêu cầu bài tập mà còn là một **sản phẩm thực tế** có thể sử dụng lâu dài. Em đã áp dụng các kỹ năng đã học trong môn Tin Học Ứng Dụng:

- **Kỹ năng thiết kế web** — HTML, CSS, JavaScript
- **Tìm kiếm và đánh giá thông tin** — Nghiên cứu xu hướng thiết kế Neobrutalism
- **Sáng tạo nội dung số** — Xây dựng giao diện đẹp mắt, hiện đại
- **Sử dụng AI có trách nhiệm** — Tận dụng công cụ AI hỗ trợ coding nhưng vẫn hiểu và kiểm soát toàn bộ source code

Em xin cảm ơn thầy/cô và các bạn đã lắng nghe!

---

## PHỤ LỤC — CÂU HỎI THƯỜNG GẶP

> **Q: Dữ liệu lưu ở đâu?**  
> A: Trong `localStorage` của trình duyệt. Nếu xóa cache trình duyệt, dữ liệu sẽ mất. Vì vậy nên dùng chức năng "Tải Source Code" để backup.

> **Q: Có cần server không?**  
> A: Không. Đây là trang web tĩnh (static), có thể chạy offline hoặc host miễn phí trên GitHub Pages.

> **Q: Tại sao chọn Neobrutalism?**  
> A: Vì phong cách này phá cách, cá tính, dễ nhận diện, và quan trọng nhất — nó đang là xu hướng thiết kế web 2025–2026.

> **Q: Ảnh kỉ niệm có bị giới hạn không?**  
> A: Không giới hạn số lượng. Ảnh dùng URL link (không upload file) nên không lo vấn đề dung lượng.
