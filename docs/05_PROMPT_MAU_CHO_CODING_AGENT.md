# 05. Prompt Mẫu Chuẩn Cho Coding Agent Bất Kỳ (Copy & Paste)

Tài liệu này cung cấp các **Prompt (Câu lệnh giao việc)** đã được tối ưu hóa để bạn chỉ cần copy và dán vào bất kỳ Coding Agent nào (**Claude Code**, **OpenAI Codex**, **Cursor**, **Windsurf**, **Antigravity**, **GitHub Copilot Workspace**...) là Agent đó sẽ tự động đọc hiểu toàn bộ kho tài nguyên và render ra video hoàn chỉnh.

---

## Prompt 1: Dựng Video Bằng `video-shotcraft` (Remotion + TypeScript)

> **Copy đoạn dưới đây và gửi cho Coding Agent:**

```text
Hãy đóng vai một Motion Designer & Video Engineer chuyên nghiệp. Trong repository này đã có sẵn:
1. Bộ công cụ `video-shotcraft/` (kèm `.claude/skills/video-shotcraft/SKILL.md` và `video-shotcraft/assets/lib/helpers.ts`).
2. Kho tài nguyên 41 bức ảnh kỷ niệm độc nhất và 1 file nhạc nền (147.0 giây / 02:27) của Lớp 12A2 — Trường THPT Thuận Hóa (ĐHSP Huế) đã được chia ngăn sẵn trong thư mục `tai_nguyen_phan_hoach/`.
3. Bộ tài liệu đặc tả chi tiết trong thư mục `docs/`:
   - `docs/01_PHAN_TICH_VIDEO_MAU.md`: Phân tích phong cách video mẫu màn hình chiếu phía sau buổi đồng diễn.
   - `docs/02_DANH_MUC_TAI_NGUYEN_PHAN_HOACH.md`: Danh mục chi tiết 41 ảnh + độ phân giải + gợi ý caption.
   - `docs/03_KICH_BAN_TIMELINE_147_GIAY.md`: Bảng phân cảnh 28 Shots từ 00:00 đến 02:27 (4410 frames @ 30fps).
   - `docs/04_HUONG_DAN_AP_DUNG_VIDEO_SHOTCRAFT.md`: Hướng dẫn áp dụng `video-shotcraft` và quy tắc chống cắt mặt học sinh.

Nhiệm vụ của bạn:
1. Đọc kỹ toàn bộ 4 file `.md` trong `docs/` và `video-shotcraft/SKILL.md`.
2. Sử dụng `video-shotcraft/template` (Remotion) để lập trình Composition `DongDien12A2` (1920x1080, 30fps, 4410 frames = 147.0 giây) bám sát 100% kịch bản 28 Shots trong `docs/03_KICH_BAN_TIMELINE_147_GIAY.md`.
3. Đảm bảo sử dụng đầy đủ 41/41 bức ảnh trong `tai_nguyen_phan_hoach/`, ghép với file âm thanh `tai_nguyen_phan_hoach/07_Am_Thanh_Bai_Hat_Mau/nhac_nen_dong_dien_tri_an_2m27s.m4a`.
4. Áp dụng các công thức chuyển động mượt từ `video-shotcraft/assets/lib/helpers.ts` (`dampedSettle`, `handheld`, `lagged`, `mulberry32`), kết hợp các bố cục: Ceremony Backdrop Title, Rounded Hero Card, Classic Arch Frame (khung vòm cong cổ điển), Dual Polaroid Scrapbook, School Emblem Lockup và Grand Finale Lockup.
5. Tuyệt đối không làm méo ảnh hoặc cắt mất mặt học sinh; đặt khung ảnh ở vùng an toàn phía trên và đặt phụ đề tiếng Việt (Unicode chuẩn) ở cạnh dưới màn hình.
6. Render ra file video hoàn chỉnh `Video_Dong_Dien_12A2_THPT_Thuan_Hoa.mp4` ở thư mục gốc của repo và kiểm tra lại các frame xuất ra.
```

---

## Prompt 2: Dựng Video Bằng Chế Độ Sân Khấu Nghiêm Ngặt (`00:00 – 00:47` Giữ Backdrop Tĩnh/Động Nhẹ, `00:48 – 02:27` Chạy Montage Kỷ Niệm)

> **Dùng Prompt này nếu kịch bản múa trên sân khấu của lớp 12A2 giống hệt 100% đội hình của video mẫu (47 giây đầu múa đôi trên nền phông tên chương trình, đúng giây `00:48` mới bật video ảnh kỷ niệm):**

```text
Hãy đọc toàn bộ các file hướng dẫn trong `docs/` và `video-shotcraft/SKILL.md`.
Tôi muốn bạn render video `Video_Dong_Dien_12A2_Stage_Mode.mp4` (1920x1080, 30fps, 147.0 giây) ghép với nhạc nền `tai_nguyen_phan_hoach/07_Am_Thanh_Bai_Hat_Mau/nhac_nen_dong_dien_tri_an_2m27s.m4a` theo Chế độ 2 (Strict Stage Sync):
- Từ `00:00` đến `00:47.5`: Hiển thị màn hình Backdrop sân khấu "TRƯỜNG ĐẠI HỌC SƯ PHẠM, ĐẠI HỌC HUẾ - TRƯỜNG THPT THUẬN HÓA | ĐỒNG DIỄN TRI ÂN KHỐI 12 - TẬP THỂ 12A2 (NIÊN KHÓA 2023 - 2026)" trên nền bầu trời xanh thanh xuân với mây trắng, máy bay giấy và hạt sáng chuyển động nhẹ nhàng.
- Đúng tại giây `00:47.5 -> 00:48.0` (khi nhạc dồn và đội hình múa mở ra hai bên): Bắt đầu trình chiếu toàn bộ 41 bức ảnh trong `tai_nguyen_phan_hoach/` (từ Ngăn 01 đến Ngăn 06) kéo dài từ `00:48` đến `02:27` bằng cách sử dụng kết hợp khung đơn (`Rounded Hero Card`, `Classic Arch Frame`) cho các ảnh `HERO_` và khung ghép đôi/ghép ba (`Dual Polaroid Scrapbook`) cho các ảnh cùng chủ đề.
- Tại giây `02:00 – 02:02`: Hiển thị biểu trưng Trường THPT Thuận Hóa ở chính giữa nền kem sáng.
- Tại giây `02:20 – 02:27`: Kết thúc bằng đại cảnh Lễ Tổng Kết Năm Học 2025-2026 và lời chào tạm biệt của Tập thể 12A2 rồi mờ dần về đen.
```

---

## Prompt 3: Dựng Nhanh Bằng Python + FFmpeg (Không Cần Cài Node.js / Chromium)

> **Dùng Prompt này nếu máy chạy Coding Agent không có Node.js hoặc muốn xuất video tốc độ cao chỉ bằng Python + Pillow + OpenCV + FFmpeg:**

```text
Hãy đọc toàn bộ kịch bản 28 Shots tại `docs/03_KICH_BAN_TIMELINE_147_GIAY.md` và hướng dẫn thị giác tại `docs/01_PHAN_TICH_VIDEO_MAU.md`, `docs/04_HUONG_DAN_AP_DUNG_VIDEO_SHOTCRAFT.md`.
Hãy viết một script Python hoàn chỉnh sử dụng Pillow (PIL), NumPy, OpenCV và FFmpeg để tự động dựng và render toàn bộ 41 bức ảnh trong `tai_nguyen_phan_hoach/` cùng file nhạc `tai_nguyen_phan_hoach/07_Am_Thanh_Bai_Hat_Mau/nhac_nen_dong_dien_tri_an_2m27s.m4a` thành file `Video_Dong_Dien_12A2_THPT_Thuan_Hoa.mp4` (1920x1080, 30fps, H.264 yuv420p, AAC audio, thời lượng đúng 147.0 giây).
Đảm bảo cài đặt hàm toán học `dampedSettle` từ `video-shotcraft/assets/lib/helpers.ts` sang Python để tạo chuyển động mượt mà cho các khung ảnh Rounded Card, Classic Arch Frame và Dual Polaroid, hỗ trợ đầy đủ font chữ Tiếng Việt Unicode sắc nét.
```
