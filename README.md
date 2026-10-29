# 🎬 Kho Tài Nguyên & Kịch Bản Dựng Video Đồng Diễn Tri Ân — Lớp 12A2 (THPT Thuận Hóa)

Repository này chứa toàn bộ **tài nguyên hình ảnh/âm thanh đã được kiểm duyệt, lọc trùng và phân hoạch theo dòng thời gian/chủ đề**, tích hợp sẵn bộ công cụ **[`video-shotcraft`](./video-shotcraft/)** cùng **hệ thống tài liệu `.md` đặc tả kỹ thuật** để bất kỳ **AI Coding Agent** nào (Claude Code, OpenAI Codex, Cursor, Windsurf, Antigravity...) cũng có thể tự động dựng hoàn chỉnh video trình chiếu trên màn hình máy chiếu / LED sân khấu phía sau buổi đồng diễn của **Tập thể Lớp 12A2 (Niên khóa 2023 – 2026) — Trường THPT Thuận Hóa, Trường Đại học Sư phạm, Đại học Huế**.

- **Phong cách & Âm nhạc tham chiếu**: [Đồng diễn Tri ân khối 12 25-26 | BLUE SHARKS TEAM | THPT Mạc Đĩnh Chi](https://www.youtube.com/watch?v=lQoerEv_2xE)
- **Thời lượng chuẩn của bài hát**: `02:27` (`147.0 giây` / `4410 frames @ 30fps`)
- **Độ phân giải mục tiêu**: `1920x1080` (Full HD `16:9`), `30fps` / `60fps`, `H.264 + AAC`

---

## 📂 Cấu Trúc Thư Mục Của Repository

```text
tai_nguyen_video_12a2/
├── README.md                                  # Tổng quan dự án & chỉ mục dành cho Coding Agent
├── .claude/skills/video-shotcraft/SKILL.md    # Skill tự động kích hoạt cho Claude Code / AI Agents
├── video-shotcraft/                           # Bộ công cụ dựng video bằng code (Remotion + 124 Shot Recipe Cards)
│   ├── SKILL.md                               # Tài liệu hướng dẫn gốc của video-shotcraft
│   ├── assets/lib/helpers.ts                  # Các hàm toán học chuyển động mượt (dampedSettle, handheld, lagged...)
│   ├── demos/                                 # 124 mẫu hiệu ứng chuyển động (Shot Cards)
│   ├── references/                            # Quy trình 6 bước dựng video tự chủ
│   └── template/                              # Dự án Remotion mẫu sẵn sàng để render ra MP4
├── docs/                                      # Hệ thống tài liệu hướng dẫn chi tiết cho Coding Agent
│   ├── 01_PHAN_TICH_VIDEO_MAU.md              # Phân tích từng giây & bố cục thị giác của video mẫu YouTube
│   ├── 02_DANH_MUC_TAI_NGUYEN_PHAN_HOACH.md   # Danh mục 41 ảnh độc nhất (đã lọc 3 ảnh trùng) + độ phân giải + caption
│   ├── 03_KICH_BAN_TIMELINE_147_GIAY.md       # Storyboard & Beat-Sheet 28 Shots khớp nhạc từ 00:00 đến 02:27
│   ├── 04_HUONG_DAN_AP_DUNG_VIDEO_SHOTCRAFT.md# Hướng dẫn kỹ thuật ghép video-shotcraft, chống cắt mặt, mẫu code
│   └── 05_PROMPT_MAU_CHO_CODING_AGENT.md      # Các câu lệnh Prompt mẫu để copy-paste cho bất kỳ Coding Agent nào
└── tai_nguyen_phan_hoach/                     # 41 bức ảnh độc nhất chia làm 6 ngăn chủ đề + 1 ngăn âm thanh
    ├── 01_Lop_10_Khoi_Dau_Bo_Ngo/             # (5 ảnh) Khai giảng Lớp 10, Tập thể 10/2, Áo Đoàn, Cổng trại
    ├── 02_Lop_11_Gan_Ket_Truong_Thanh/        # (8 ảnh) Kỷ niệm Lớp 11/2, Balo bánh kẹo, Hộp quà vẽ tay, Giao lưu QT
    ├── 03_Hoi_Trai_Van_Nghe_Ruc_Ro/           # (5 ảnh) Hội trại kỹ năng sống, Lều vàng súng nước, Múa cổ phục, Tết 2026
    ├── 04_Doi_Bong_12A2_Dam_Me_Va_Vo_Dich/    # (9 ảnh) Đội bóng 12A2 từ áo xanh đến Chức Vô Địch sân Bá Công
    ├── 05_Chuyen_Di_Thanh_Xuan_Quy_Nhon_Lang_Co/ # (11 ảnh) Bó hoa ảnh hồi nhỏ, Mẹ Thứ, ExploraScience, Biển, Gala Dinner
    ├── 06_Lop_12_Tri_An_Va_Truong_Thanh/      # (3 ảnh) Chào năm học cuối I ♥ HUEdu, Sân khấu Gala, Lễ Tổng Kết 25-26
    └── 07_Am_Thanh_Bai_Hat_Mau/               # (1 file) nhac_nen_dong_dien_tri_an_2m27s.m4a (147.0 giây)
```

---

## 📚 Thứ Tự Đọc Dành Cho Coding Agent

Nếu bạn là một **Coding Agent** được giao nhiệm vụ dựng video từ repository này, hãy đọc theo đúng thứ tự 5 bước sau:

1. **Bước 1**: Đọc [`docs/01_PHAN_TICH_VIDEO_MAU.md`](./docs/01_PHAN_TICH_VIDEO_MAU.md) để nắm rõ bố cục sân khấu đồng diễn, vùng an toàn thị giác (tránh bị học sinh đứng múa phía trước che khuất), bảng màu hoài niệm và cấu trúc 4 phần của bài hát.
2. **Bước 2**: Đọc [`docs/02_DANH_MUC_TAI_NGUYEN_PHAN_HOACH.md`](./docs/02_DANH_MUC_TAI_NGUYEN_PHAN_HOACH.md) để nắm thông tin từng bức ảnh trong `tai_nguyen_phan_hoach/` (kích thước ngang/dọc, các bức ảnh tâm điểm có tiền tố `HERO_`, và câu phụ đề tiếng Việt tương ứng).
3. **Bước 3**: Đọc [`docs/03_KICH_BAN_TIMELINE_147_GIAY.md`](./docs/03_KICH_BAN_TIMELINE_147_GIAY.md) để lấy bảng phân cảnh 28 Shots chính xác tới từng giây (`00:00` – `02:27`, `4410 frames @ 30fps`).
4. **Bước 4**: Đọc [`docs/04_HUONG_DAN_AP_DUNG_VIDEO_SHOTCRAFT.md`](./docs/04_HUONG_DAN_AP_DUNG_VIDEO_SHOTCRAFT.md) và [`video-shotcraft/SKILL.md`](./video-shotcraft/SKILL.md) để áp dụng các thẻ chuyển động (`spotlight-hero-card`, `panel-grid-moves`, `Classic Arch Frame`, `dampedSettle`, `handheld`) và xuất ra file `.mp4`.
5. **Bước 5 (Dành cho người dùng)**: Xem [`docs/05_PROMPT_MAU_CHO_CODING_AGENT.md`](./docs/05_PROMPT_MAU_CHO_CODING_AGENT.md) để lấy câu lệnh Prompt giao việc tự động cho Agent.
