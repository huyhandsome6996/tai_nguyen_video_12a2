# 04. Hướng Dẫn Kỹ Thuật Áp Dụng `video-shotcraft` Để Edit Video Kỷ Yếu 12A2

Tài liệu này hướng dẫn bất kỳ **Coding Agent** nào (Claude Code, Codex, Cursor, Windsurf, Antigravity...) cách khai thác trực tiếp thư viện [`video-shotcraft/`](../video-shotcraft/) đã được cài đặt sẵn trong repository để dựng và xuất file video `.mp4` (`1920x1080`, `30fps`, `147.0 giây`) theo đúng kịch bản tại [`03_KICH_BAN_TIMELINE_147_GIAY.md`](./03_KICH_BAN_TIMELINE_147_GIAY.md).

---

## 1. Cấu Trúc Thư Viện `video-shotcraft` Đã Cài Đặt Trong Repo

Thư viện [Vincentwei1021/video-shotcraft](https://github.com/Vincentwei1021/video-shotcraft) đã được tích hợp tại:
- Thư mục chính: [`video-shotcraft/`](../video-shotcraft/)
- Skill tự động nhận diện cho Agent: [`.claude/skills/video-shotcraft/SKILL.md`](../.claude/skills/video-shotcraft/SKILL.md) và [`video-shotcraft/SKILL.md`](../video-shotcraft/SKILL.md)
- Các tài nguyên cốt lõi cần đọc trước khi code:
  1. [`video-shotcraft/references/pipeline.md`](../video-shotcraft/references/pipeline.md): Quy trình 6 bước dựng video tự chủ (Autonomous Free Creation Mode).
  2. [`video-shotcraft/assets/lib/helpers.ts`](../video-shotcraft/assets/lib/helpers.ts): Bộ hàm toán học chuyển động mượt (`dampedSettle`, `handheld`, `lagged`, `velocityAt`, `mulberry32`, `clamp01`).
  3. [`video-shotcraft/template/`](../video-shotcraft/template/): Dự án Remotion mẫu hoàn chỉnh có sẵn `package.json`, `tsconfig.json`, `src/index.ts`.
  4. [`video-shotcraft/demos/`](../video-shotcraft/demos/): 124 thẻ công thức chuyển động (Shot Recipe Cards).

---

## 2. Ánh Xạ Các Thẻ Công Thức (`Shot Recipe Cards`) Của `video-shotcraft` Vào Video Đồng Diễn

Để video chiếu sau lưng học sinh đạt chuẩn điện ảnh (mượt mà, có chiều sâu 2.5D, không bị giật cục), Coding Agent hãy áp dụng các thẻ công thức sau từ `video-shotcraft/demos/`:

| Mẫu bố cục trong Timeline | Thẻ `video-shotcraft` tương ứng | Hàm Helper trong `assets/lib/helpers.ts` | Mục đích thị giác trên màn hình LED |
| :--- | :--- | :--- | :--- |
| **`Ceremony Backdrop Title`** (`Shot 01`) | `ambient-HeroBackdropParticles` + `kinetic-TitleSplitReveal` | `mulberry32(seed)` + `dampedSettle()` | Tạo nền bầu trời xanh thanh xuân với các hạt bụi sáng/mây trôi nhẹ và tiêu đề **ĐỒNG DIỄN TRI ÂN KHỐI 12 — 12A2** hiện lên trang trọng. |
| **`Rounded Hero Card`** (`Shot 02, 03, 05, 10, 26`) | `spotlight-hero-card` + `camera-HandheldFloat` | `dampedSettle(t, 0, 1, 9, 0.78)` + `handheld(frame, fps, 0.35)` | Khung ảnh đơn bo góc `24px`, viền trắng `10px`, nổi trên nền mờ ấm (`blur(36px)`), có độ trôi máy ảnh tự nhiên như đang thở. |
| **`Classic Arch Frame`** (`Shot 06, 16, 21`) | `showcase-ArchWindowReveal` / `graze-face-tour` | `dampedSettle()` + `interpolate()` | Khung vòm cong cổ điển (`borderRadius: '340px 340px 24px 24px'`) trên nền giấy kem `#F5F0E6` — tái hiện chính xác khung hình tại giây `01:23–01:29` của video mẫu. |
| **`Dual Polaroid Scrapbook`** (`Shot 04, 07, 08, 09, 11, 12, 14, 19, 20, 24, 25`) | `panel-grid-moves` / `product-card-progressive-assemble` | `lagged(frame, index, 10)` + `dampedSettle()` | Ghép 2 bức ảnh xuất hiện lệch nhịp `10 frames` (`0.33s`), nghiêng nhẹ `-2.5deg` và `+2.5deg` như cuốn sổ lưu bút thanh xuân. |
| **`Spotlight Hero Card` [HERO]** (`Shot 13, 18, 22, 27`) | `spotlight-hero-card` + `camera-SlowPushIn` | `interpolate(frame, [0, duration], [1.0, 1.06])` | Dành cho các bức ảnh `[HERO]` (Tết Yêu Thương, Cúp Vô Địch, Gala Dinner): phóng nhẹ vào trung tâm kèm lớp phủ bokeh vàng ấm. |
| **`School Emblem Lockup`** (`Shot 23` @ `02:00–02:03`) | `logo-shrink-wordmark-lockup` | `dampedSettle()` | Tái hiện cảnh giây `02:00–02:02` của video mẫu: Logo & Tên Trường **THPT Thuận Hóa — ĐHSP Huế** khóa bố cục ở chính giữa. |

---

## 3. Quy Tắc Bắt Buộc Khi Xử Lý Ảnh Tập Thể Lớp (Chống Mất Mặt Học Sinh)

Khi lập trình component hiển thị ảnh, Coding Agent **BẮT BUỘC** tuân thủ 4 quy tắc sau:

1. **Không cắt cúp mất người (`No Cropped Faces`)**:
   - Đa số ảnh của Lớp 12A2 có tỷ lệ `4:3` (`2048x1536` hoặc `2568x1926`) và `5 ảnh dọc 3:4` (`1920x2560`).
   - Khi đặt vào màn hình `16:9` (`1920x1080`), **KHÔNG ĐƯỢC** ép ảnh `4:3` hoặc `3:4` tràn full `width: 1920px` với `objectFit: 'cover'` vì sẽ cắt mất hàng đầu hoặc hàng cuối của lớp.
   - **Giải pháp chuẩn**:
     - Lớp dưới cùng (`Layer 0`): Dùng chính bức ảnh đó với `width: '100%', height: '100%', objectFit: 'cover', filter: 'blur(42px) brightness(0.65) saturate(1.2)', transform: 'scale(1.15)'` (hoặc nền kem `#F5F0E6`).
     - Lớp khung ảnh chính (`Layer 1`): Đặt ảnh trong khung chứa có chiều cao `740px -> 800px` (nằm ở toạ độ `top: 50px`), sử dụng `objectFit: 'contain'` hoặc khung có đúng tỷ lệ `4:3` / `3:4` của ảnh gốc, bo góc `20px`, viền trắng `10px`, bóng đổ `0 24px 60px rgba(0,0,0,0.4)`.
2. **Xử lý 5 bức ảnh dọc (`Portrait 3:4`)**:
   - Gồm các file:
     - `04_Doi_Bong_12A2_Dam_Me_Va_Vo_Dich/04_doi_bong_ao_do_cong_kenh_cung_co_chu_nhiem.jpg`
     - `04_Doi_Bong_12A2_Dam_Me_Va_Vo_Dich/07_lien_hoan_kfc_sau_tran_bong.jpg`
     - `05_Chuyen_Di_Thanh_Xuan_Quy_Nhon_Lang_Co/01_bo_hoa_anh_hoi_nho_tren_xe_du_lich.jpg`
     - `05_Chuyen_Di_Thanh_Xuan_Quy_Nhon_Lang_Co/02_check_in_tuong_dai_me_thu_quang_nam.jpg`
     - `06_Lop_12_Tri_An_Va_Truong_Thanh/03_HERO_le_tong_ket_nam_hoc_2025_2026_cung_co_chu_nhiem.jpg`
   - Luôn hiển thị các ảnh dọc này theo cặp (`Dual Portrait Card` — 2 khung dọc đặt song song bên trái & bên phải) hoặc đặt khung dọc bên trái + khối đại tự cảm xúc bên phải (như ở `Shot 28 Finale`).
3. **Vùng an toàn cho Phụ đề (Caption Safe Zone)**:
   - Đặt thanh phụ đề ở khoảng `bottom: 48px -> 95px`, chữ cỡ `36px – 44px`, có nền bán trong suốt nhẹ (`backdropFilter: 'blur(12px)', background: 'rgba(20, 18, 15, 0.55)'` hoặc trên nền giấy kem sáng ở dưới đáy khung `Arch Frame`) để khán giả ngồi xa vẫn đọc rõ từng câu chữ.
4. **Hiệu ứng chuyển cảnh êm ái (`Cross-Fade 15–20 frames`)**:
   - Giữa các cảnh liên tiếp, luôn có `15 frames` (`0.5s`) hòa mờ (`opacity` crossfade) để mắt người xem cảm nhận sự liền mạch theo giai điệu bài hát.

---

## 4. Mẫu Code Component Remotion Chuẩn (Copy & Dùng Ngay)

Coding Agent có thể khởi tạo hoặc mở rộng trực tiếp trong `video-shotcraft/template/src/` với cấu trúc component như sau:

```tsx
import React from 'react';
import {
  AbsoluteFill,
  Audio,
  Img,
  Sequence,
  interpolate,
  staticFile,
  useCurrentFrame,
  useVideoConfig,
} from 'remotion';
import { dampedSettle, handheld } from '../../assets/lib/helpers';

export interface ShotSpec {
  id: string;
  startSec: number;
  endSec: number;
  layout: 'backdrop' | 'hero' | 'arch' | 'dual' | 'triple' | 'emblem' | 'finale';
  images: string[];
  title?: string;
  caption: string;
}

export const ArchFrameShot: React.FC<{ shot: ShotSpec }> = ({ shot }) => {
  const frame = useCurrentFrame();
  const { fps, durationInFrames } = useVideoConfig();
  const t = frame / fps;

  // Hiệu ứng xuất hiện mượt từ video-shotcraft
  const reveal = dampedSettle(t, 0, 1, 8, 0.82);
  const scale = interpolate(frame, [0, durationInFrames], [1.0, 1.05]);
  const fadeOut = interpolate(
    frame,
    [durationInFrames - 15, durationInFrames],
    [1, 0],
    { extrapolateLeft: 'clamp', extrapolateRight: 'clamp' }
  );

  return (
    <AbsoluteFill
      style={{
        backgroundColor: '#F4EFE6',
        justifyContent: 'center',
        alignItems: 'center',
        opacity: fadeOut,
      }}
    >
      {/* Khung vòm cong cổ điển giống giây 01:23 - 01:29 của video mẫu */}
      <div
        style={{
          width: 1280,
          height: 780,
          marginTop: -70,
          borderRadius: '360px 360px 28px 28px',
          overflow: 'hidden',
          border: '12px solid #FFFFFF',
          boxShadow: '0 24px 60px rgba(45, 35, 25, 0.18)',
          transform: `translateY(${(1 - reveal) * 40}px)`,
        }}
      >
        <Img
          src={staticFile(shot.images[0])}
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'center center',
            transform: `scale(${scale})`,
          }}
        />
      </div>

      {/* Dòng chữ cảm xúc ở cạnh dưới */}
      <div
        style={{
          position: 'absolute',
          bottom: 56,
          textAlign: 'center',
          color: '#3B2F2F',
          fontFamily: '"Playfair Display", "Noto Serif", Georgia, serif',
          fontSize: 44,
          fontStyle: 'italic',
          fontWeight: 600,
          letterSpacing: 0.5,
        }}
      >
        {shot.caption}
      </div>
    </AbsoluteFill>
  );
};
```

---

## 5. Quy Trình Build & Render Ra File `.mp4`

### Cách 1: Render bằng Remotion (`video-shotcraft/template`)
1. Copy thư mục `tai_nguyen_phan_hoach/` vào `video-shotcraft/template/public/tai_nguyen_phan_hoach/`.
2. Cài đặt dependencies và xuất video:
   ```bash
   cd video-shotcraft/template
   npm install
   npx remotion render src/index.ts DongDien12A2 ../../Video_Dong_Dien_12A2_THPT_Thuan_Hoa.mp4 --codec=h264 --crf=18
   ```

### Cách 2: Render bằng Python (`OpenCV` + `Pillow` + `FFmpeg`) nếu môi trường không có Node.js
Nếu Coding Agent chạy trên máy chưa cài Node.js nhưng có Python + FFmpeg:
- Viết script Python đọc trực tiếp bảng cấu hình 28 Shots từ [`03_KICH_BAN_TIMELINE_147_GIAY.md`](./03_KICH_BAN_TIMELINE_147_GIAY.md).
- Dùng `PIL.Image`, `PIL.ImageDraw`, `PIL.ImageFilter.GaussianBlur` và font tiếng Việt hệ thống (`C:\Windows\Fonts\timesbi.ttf`, `segoeui.ttf`, `arialbd.ttf`) để vẽ từng frame `1920x1080` với công thức toán học `dampedSettle` tương đương.
- Pipe trực tiếp luồng frame raw RGB vào `ffmpeg` kèm file âm thanh `tai_nguyen_phan_hoach/07_Am_Thanh_Bai_Hat_Mau/nhac_nen_dong_dien_tri_an_2m27s.m4a` để xuất ra `Video_Dong_Dien_12A2_THPT_Thuan_Hoa.mp4` (`H.264`, `yuv420p`, `30fps`, `1920x1080`).
