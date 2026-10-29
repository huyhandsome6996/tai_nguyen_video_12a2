# 01. Phân Tích Chi Tiết Video Mẫu Đồng Diễn & Màn Hình LED Phía Sau

- **Video tham khảo gốc**: [Đồng diễn Tri ân khối 12 25-26 | BLUE SHARKS TEAM | THPT Mạc Đĩnh Chi](https://www.youtube.com/watch?v=lQoerEv_2xE)
- **Thời lượng chuẩn**: `02:27` (`147.0 giây` — tương đương `4410 frames` ở mức `30fps`, hoặc `8820 frames` ở mức `60fps`)
- **File âm thanh gốc đã trích xuất sẵn**: [`tai_nguyen_phan_hoach/07_Am_Thanh_Bai_Hat_Mau/nhac_nen_dong_dien_tri_an_2m27s.m4a`](../tai_nguyen_phan_hoach/07_Am_Thanh_Bai_Hat_Mau/nhac_nen_dong_dien_tri_an_2m27s.m4a)
- **Mục tiêu áp dụng**: Xây dựng video trình chiếu trên màn hình máy chiếu / màn hình LED sân khấu ngay sau lưng học sinh **Lớp 12A2 (10/2 → 11/2 → 12/2) — Trường THPT Thuận Hóa (Trường Đại học Sư phạm, Đại học Huế), Niên khóa 2023 – 2026**.

---

## 1. Tổng Quan Bố Cục Sân Khấu & Vai Trò Của Video Màn Hình Chiếu

Trong tiết mục đồng diễn mẫu (`lQoerEv_2xE`), màn hình chiếu / LED đặt ở **chính giữa sân khấu, ngay phía sau đội hình múa của lớp**. Do các học sinh đứng múa ở tiền cảnh (chiếm khoảng 20%–25% chiều cao cạnh dưới của màn hình khi nhìn từ khán đài), video chiếu phía sau được thiết kế với các nguyên tắc thị giác đặc trưng:

1. **Vùng an toàn thị giác (Safe Zone)**:
   - **75% diện tích phía trên & trung tâm màn hình (`y: 60px -> 860px` trên khung `1920x1080`)**: Là nơi đặt khung ảnh kỷ niệm chính (Hero Photo / Polaroid / Arch Frame) để gương mặt của các thành viên trong ảnh luôn nằm cao hơn đầu của đội hình múa ngoài đời thực.
   - **Cạnh dưới (`y: 860px -> 1020px`)**: Dành cho dòng chữ phụ đề cảm xúc (Caption / Typography) hoặc khoảng nền sáng/mờ để không bị che khuất chi tiết quan trọng.
2. **Xử lý tỷ lệ ảnh (`4:3` và `3:4` trên màn hình `16:9`)**:
   - Không bao giờ kéo giãn (stretch) hoặc cắt cụt đầu/mặt học sinh (`crop` mất người).
   - Luôn dùng **lớp nền mờ đồng điệu (`Blurred & Warm-Tinted Backdrop`)** hoặc **nền giấy kem cổ điển (`#F6F2EA` / `#EFECE6`)** phủ kín khung `1920x1080`, sau đó đặt bức ảnh gốc bên trong khung bo góc (`Rounded Card`), khung vòm cong (`Arch Window Frame`), hoặc ghép đôi 2 ảnh dọc (`Dual Polaroid Scrapbook`).
3. **Nhịp điệu chuyển cảnh theo âm nhạc & đội hình múa**:
   - Không chuyển ảnh máy móc đều nhau từ đầu đến cuối, mà chia thành **4 chương cảm xúc (4 Acts)** khớp tuyệt đối với cao trào của bài hát và động tác trên sân khấu.

---

## 2. Phân Tích Cấu Trúc Âm Nhạc & Diễn Biến Từng Giây (`00:00` – `02:27`)

### Phần 1: Mở Đầu Lắng Đọng — Song Ca & Múa Đôi Đương Đại (`00:00` – `00:47` | `47 giây`)
- **Âm nhạc**: Tiếng hát ballad mộc mạc trên nền piano nhẹ nhàng (*"Cảm ơn đôi bàn tay... Cảm ơn vì đã đến bên nhau... Cảm ơn nơi bình yên... Để thanh xuân của ta ở lại..."*).
- **Hoạt động trên sân khấu**:
  - `00:00 – 00:28`: 2 học sinh nam – nữ múa đương đại mở màn ở trung tâm sân khấu.
  - `00:28 – 00:47`: 10 học sinh từ hai cánh gà chạy vào, kết đội hình tháp trung tâm (`00:31 – 00:45`) và cùng cúi xuống mở đội hình tại giây `00:46 – 00:47`.
- **Hình ảnh trên màn hình chiếu ở video mẫu**:
  - Giữ **Backdrop định danh buổi lễ** (*"ĐỒNG DIỄN TRI ÂN KHỐI 12 — NIÊN KHÓA 2023 - 2026"*) trên nền màu xanh bầu trời thanh xuân, có họa tiết máy bay giấy, khuông nhạc và mây trắng.
- **Phương án áp dụng cho Lớp 12A2 - THPT Thuận Hóa**:
  - **Chế độ A (Chuẩn đồng diễn sân khấu)**: Từ `00:00 – 00:47` hiển thị Backdrop động nhẹ nhàng mang tên **"TRƯỜNG ĐẠI HỌC SƯ PHẠM, ĐẠI HỌC HUẾ - TRƯỜNG THPT THUẬN HÓA | ĐỒNG DIỄN TRI ÂN KHỐI 12 - TẬP THỂ 12A2 (2023 - 2026)"** (hoặc đan xen 5 bức ảnh Lớp 10 mở đầu nhẹ nhàng).
  - **Chế độ B (Full Montage 147s)**: Trình chiếu chương **"Lớp 10 — Khởi Đầu Bỡ Ngỡ & Lớp 11 — Gắn Kết"** với chuyển động Ken Burns cực chậm theo tiếng piano.

---

### Phần 2: Bùng Nổ Cảm Xúc — Mở Đội Hình & Khởi Chạy Video Kỷ Niệm (`00:48` – `01:29` | `42 giây`)
- **Âm nhạc**: Tại đúng giây `00:47.5 -> 00:48.0`, nhạc dạo dàn dây (Strings) và trống dồn vang lên hào hùng cùng tiếng reoò cổ vũ của toàn trường.
- **Hoạt động trên sân khấu**:
  - Đội hình tách sang hai bên để lộ toàn bộ màn hình chiếu ở giữa.
  - Từ `00:52 – 00:55`, hai bức liễn dọc ở hai cột sân khấu được thả xuống:
    - Cánh trái: *"Cảm Ơn Vì Đã Xuất Hiện Trong Thanh Xuân Của Nhau"*
    - Cánh phải: *"Mang Theo Những Ký Ức Đẹp Nhất, Tiến Về Phía Ánh Sáng"*
- **Chi tiết từng khung hình trên màn hình LED (`00:48` – `01:29`)**:

| STT Cảnh | Thời gian | Thời lượng | Bố cục & Hiệu ứng thị giác trên màn hình mẫu | Nội dung & Caption tương ứng |
| :--- | :--- | :--- | :--- | :--- |
| **Slide 01** | `00:48 – 00:53` | `5.5s` | Toàn cảnh góc sân trường/hành lang rợp bóng cây xanh, nắng xuyên qua tán lá, chữ viết tay bay bổng ở trung tâm. | Mở ra không gian mái trường: *"Thanh xuân của chúng ta..."* |
| **Slide 02** | `00:54 – 00:58` | `5.0s` | Ảnh tập thể trong lớp học đặt trên nền giấy kem sáng, viền bo nhẹ, dòng chữ cảm xúc phía dưới ảnh. | Những ngày đầu tiên: *"Từ những ngày đầu bỡ ngỡ bước vào lớp 10/2..."* |
| **Slide 03** | `00:59 – 01:03` | `5.0s` | Ảnh kỷ niệm ngày lễ trong lớp học (bảng xanh phía sau, cả lớp giơ tay rạng rỡ), zoom-in rất nhẹ (`1.00 -> 1.05`). | Những buổi sinh hoạt & lễ kỷ niệm ấm áp trong lớp. |
| **Slide 04** | `01:04 – 01:10` | `6.5s` | Ảnh tập thể hoạt động ngoại khóa sân trường, tông màu ấm hoài niệm, chữ serif đậm ở cạnh dưới. | Hoạt động tập thể: *"Cùng nhau đi qua bao mùa nắng gió..."* |
| **Slide 05** | `01:11 – 01:16` | `5.5s` | Ảnh dã ngoại/cắm trại ngồi quây quần trên bãi cỏ xanh dưới tán cây. | Những buổi dã ngoại, hội trại kỹ năng sống đầy tiếng cười. |
| **Slide 06** | `01:17 – 01:22` | `5.5s` | Ảnh tập thể lớp đứng dưới hàng cây xanh trong trang phục đồng phục. | Kỷ niệm bên thầy cô chủ nhiệm và đoàn giáo sinh thực tập. |
| **Slide 07** | `01:23 – 01:29` | `6.5s` | **Điểm nhấn thiết kế đặc biệt**: Ảnh tập thể được lồng trong **Khung Vòm Cong (`Arch Frame`)** trên nền kem trang nhã, chữ lớn phía dưới. | *"Người dưng ngược lối, hóa anh em một nhà"* (Khi dàn học sinh trên sân khấu nắm tay nhau lúc `01:27`). |

---

### Phần 3: Cao Trào Pháo Giấy — Đội Hình Toàn Lớp & Những Chuyến Đi Thanh Xuân (`01:30` – `02:02` | `33 giây`)
- **Âm nhạc**: Điệp khúc cao trào nhất của bản phối với tiếng pháo giấy nổ vang và tiếng hò reo vang dội (`01:30 – 01:35`, `01:42 – 01:45`).
- **Hoạt động trên sân khấu**: Toàn bộ học sinh của lớp xếp thành 2 hàng ngang trải rộng khắp sân khấu, nhảy đồng đều mạnh mẽ, tạo hiệu ứng lượn sóng (`01:50 – 01:52`) và ghép hình trái tim (`01:55 – 01:58`).
- **Chi tiết từng khung hình trên màn hình LED (`01:30` – `02:02`)**:

| STT Cảnh | Thời gian | Thời lượng | Bố cục & Hiệu ứng thị giác trên màn hình mẫu | Nội dung & Caption tương ứng |
| :--- | :--- | :--- | :--- | :--- |
| **Slide 08** | `01:30 – 01:35` | `5.5s` | Khi pháo giấy bắn tung bay trên sân khấu (`01:30`), màn hình chiếu bức ảnh dã ngoại/chuyến đi rực rỡ nắng vàng. | Bùng nổ tuổi trẻ: Đội bóng 12A2 & những trận cầu rực lửa đam mê. |
| **Slide 09** | `01:36 – 01:41` | `5.5s` | Ảnh tập thể trong lớp / hoạt động chung với nụ cười rạng rỡ. | Những bữa tiệc liên hoan, những món quà bất ngờ dành cho nhau. |
| **Slide 10** | `01:42 – 01:46` | `4.5s` | Ảnh sự kiện sân khấu buổi tối với ánh đèn lung linh (học sinh trên sân khấu đồng loạt giơ cao tay lúc `01:42`). | Đêm hội văn nghệ / Múa cổ phục & Tết Yêu Thương rực rỡ. |
| **Slide 11** | `01:47 – 01:49` | `3.0s` | Nhịp cắt nhanh hơn (`3s`): Ảnh tập thể tại hội trường/điểm tham quan. | Hành trình khám phá Quy Nhơn – Quảng Nam – Lăng Cô. |
| **Slide 12** | `01:50 – 01:53` | `4.0s` | Ảnh chụp dưới giàn hoa hồng/hoa giấy rực rỡ bên bờ biển/đầm nước (khớp với động tác lượn sóng trên sân khấu). | Hoàng hôn Đầm Lập An & Biển xanh cát trắng bên nhau. |
| **Slide 13** | `01:54 – 01:59` | `5.5s` | Ảnh đại gia đình ấm cúng trong khán phòng/nhà hàng tối (khớp với động tác thả tim trên đầu lúc `01:55 – 01:57`). | Đêm Gala Dinner Quy Nhơn: *"Cảm ơn vì đã là một phần thanh xuân của nhau"*. |
| **Slide 14** | `02:00 – 02:02` | `3.0s` | **Điểm nhấn chuyển chương**: Nền trắng/kem tinh khôi, **Logo Trường** hiện lên trang trọng ở chính giữa. | Biểu trưng **Trường THPT Thuận Hóa — Trường ĐHSP, Đại học Huế (12A2)**. |

---

### Phần 4: Hồi Tưởng Nhanh (Fast Flashback) & Cái Kết Vẫy Tay Chào Tạm Biệt (`02:03` – `02:27` | `24 giây`)
- **Âm nhạc**: Chuyển sang giai điệu Piano & Strings lắng đọng, da diết (`02:03 – 02:27`), khép lại bằng hợp âm ngân dài.
- **Hoạt động trên sân khấu**:
  - `02:03 – 02:13`: Đội hình duy trì nhịp nhún nhẹ, nhìn về phía khán giả.
  - `02:14 – 02:23`: Cả lớp tiến sát về phía trước sân khấu, đứng sát bên nhau, cùng giơ cao tay vẫy chào tạm biệt toàn trường.
  - `02:24 – 02:27`: Cả lớp cúi chào và bước xuống sân khấu khi màn hình LED tối dần (Fade to Black).
- **Chi tiết từng khung hình trên màn hình LED (`02:03` – `02:27`)**:
  - Tốc độ chuyển cảnh tăng lên (`2.0s – 3.0s / cảnh`) như một thước phim tua ngược lại những khoảnh khắc đắt giá nhất trước khi khép lại:
  - **Slide 15 (`02:03 – 02:04`, `2.0s`)**: Khoảnh khắc cắm trại / tiệc tối dưới ánh đèn.
  - **Slide 16 (`02:05 – 02:06`, `2.0s`)**: Check-in cổng trường / cổng trại truyền thống.
  - **Slide 17 (`02:07 – 02:09`, `2.5s`)**: Chuyến đi thực tế Tượng đài Mẹ Thứ / ExploraScience Quy Nhơn.
  - **Slide 18 (`02:10 – 02:11`, `2.0s`)**: Khoảnh khắc nâng Cúp Vô Địch bóng đá truyền thống trường.
  - **Slide 19 (`02:12 – 02:13`, `2.0s`)**: Khoảnh khắc vui nhộn đời thường (bó hoa ảnh hồi nhỏ / quả cầu tĩnh điện của Cô chủ nhiệm).
  - **Slide 20 (`02:14 – 02:16`, `3.0s`)**: Đại gia đình 12A2 mừng chức Vô Địch sân bóng Bá Công.
  - **Slide 21 (`02:17 – 02:20`, `3.5s`)**: Đại gia đình 12A2 trên sân khấu Gala Dinner Quy Nhơn.
  - **Slide 22 (`02:21 – 02:24`, `3.5s`)**: Bức ảnh Lễ Tổng Kết Năm Học 2025 – 2026 trên sân khấu Trường THPT Thuận Hóa cùng Cô giáo chủ nhiệm + Đại cảnh khép lại: **"TẬP THỂ 12A2 — MÃI LÀ ANH EM (2023 – 2026)"**.
  - **Outro (`02:24 – 02:27`, `3.0s`)**: Màn hình mờ dần về đen (`Fade out to Black`) đồng bộ với nốt nhạc piano cuối cùng.

---

## 3. Đặc Tả Phong Cách Đồ Họa (Visual Style Guide) Cho Coding Agent

Để tái tạo đúng chất thơ và sự trang trọng của video mẫu, Coding Agent cần tuân thủ bảng thông số thiết kế sau:

1. **Bảng màu chủ đạo (Color Palette)**:
   - **Nền giấy hoài niệm (Warm Cream Paper)**: `#F5F0E6` đến `#EAE2D3` (dùng cho các cảnh có khung vòm cong `Arch Frame` hoặc khung `Polaroid`).
   - **Nền mờ chiều sâu (Dark/Warm Blurred Canvas)**: Lấy chính bức ảnh đang chiếu, phóng to `scale(1.25)`, làm mờ `blur(40px)` và phủ lớp màu `rgba(25, 20, 18, 0.45)` hoặc `rgba(245, 238, 225, 0.75)` tùy cảnh sáng/tối.
   - **Màu chữ chính (Primary Typography)**:
     - Trên nền sáng: `#2C3E50` (Xanh than đậm) hoặc `#4A3B32` (Nâu trầm cổ điển).
     - Trên nền tối: `#FFFDF9` (Trắng kem ấm) kèm đổ bóng `0 4px 16px rgba(0,0,0,0.65)`.
   - **Màu nhấn (Accent)**: Vàng nắng thanh xuân (`#E6A145`) và Xanh dương THPT Thuận Hóa (`#1A5DAB`).

2. **Kiểu chữ (Typography — Hỗ trợ đầy đủ Tiếng Việt Unicode)**:
   - **Tiêu đề nghệ thuật / Câu trích dẫn cảm xúc**: Font có chân hoặc chữ viết tay mềm mại hỗ trợ tiếng Việt như `Playfair Display`, `Cormorant Garamond`, `Dancing Script`, hoặc `Noto Serif Display` (in nghiêng nhẹ).
   - **Phụ đề định danh (Tên lớp, Năm học, Sự kiện)**: Font không chân hiện đại, rõ nét khi nhìn từ xa trên sân khấu như `Be Vietnam Pro`, `Montserrat`, `Plus Jakarta Sans`, hoặc `Segoe UI Semibold`.

3. **Các mẫu khung hình (Frame Templates) cần kết hợp**:
   - **Template 1 — `Rounded Hero Card` (Khung đơn bo góc chuẩn)**: Ảnh ngang `4:3` đặt giữa màn hình (chiếm ~78% chiều cao), bo góc `24px`, viền trắng `10px`, bóng đổ mềm `0 24px 60px rgba(0,0,0,0.35)`.
   - **Template 2 — `Classic Arch Frame` (Khung vòm cong nghệ thuật — giống giây `01:23–01:29` ở video mẫu)**: Khung ảnh có vòm cong tròn hoặc vòm cung ở cạnh trên (`borderRadius: '320px 320px 24px 24px'`), đặt trên nền kem `#F4EFE6`, bên dưới là dòng chữ cảm xúc cỡ lớn.
   - **Template 3 — `Dual Polaroid Scrapbook` (Ghép đôi 2 ảnh nghiêng nhẹ)**: Rất lý tưởng để ghép 2 bức ảnh dọc (`Portrait 3:4`) hoặc 2 bức ảnh cùng một sự kiện (ví dụ: 2 ảnh đội bóng, 2 ảnh múa cổ phục, hoặc ảnh chụp ngoài cổng ExploraScience + ảnh Cô chủ nhiệm chạm quả cầu tĩnh điện) xuất hiện lệch nhịp `0.3s` bằng hàm `dampedSettle` của `video-shotcraft`.
   - **Template 4 — `School Emblem Lockup` (Cảnh biểu trưng trường lúc `02:00–02:02`)**: Sử dụng công thức thẻ `logo-shrink-wordmark-lockup` của `video-shotcraft` để hiển thị cụm biểu trưng **TRƯỜNG ĐẠI HỌC SƯ PHẠM, ĐẠI HỌC HUẾ — TRƯỜNG THPT THUẬN HÓA — LỚP 12A2 (NIÊN KHÓA 2023 – 2026)**.

