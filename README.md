# Nho Nam ♡ Như Ý — Đếm Ngày Yêu

Một trang web kỷ niệm tình yêu: đếm số ngày bên nhau, trưng ảnh, xem video và vài hiệu ứng "huyền ảo" màu hồng.

---

## 1. Mở trang

Nhấp đúp vào **`index.html`** (hoặc chuột phải → Open with → Chrome / Edge / Cốc Cốc).

> Lần đầu mở sẽ có một màn hình trái tim — bấm vào đó để mở món quà.

---

## 2. Cấu trúc thư mục

```
nhuy/
├── index.html          ← toàn bộ website (giao diện + hiệu ứng)
├── README.md           ← file này
├── images/             ← bỏ ẢNH vào đây
├── videos/             ← bỏ VIDEO vào đây
└── music/              ← bỏ NHẠC NỀN vào đây
```

---

## 3. Thêm ảnh

1. Chép ảnh vào thư mục **`images/`**.
2. Đặt tên lần lượt: `anh-1.jpg`, `anh-2.jpg`, `anh-3.jpg`… (hỗ trợ `.jpg`, `.jpeg`, `.png`, `.webp`).
3. Muốn thêm/xoá/sửa chú thích → mở `index.html`, tìm dòng `photos: [` và sửa:

```js
photos: [
  { src: 'anh-1', caption: 'Ngày đầu tiên mình gặp nhau' },
  { src: 'anh-2', caption: 'Ngày mình nói yêu nhau' },
  // thêm bao nhiêu ảnh cũng được
],
```

Ảnh thiếu sẽ hiện khung "Thêm ảnh của hai đứa" kèm đúng tên file cần thêm.

---

## 4. Thêm video

1. Chép video vào thư mục **`videos/`**.
2. Đặt tên `video-1.mp4`, `video-2.mp4` (hoặc `.webm`, `.mov`…).
3. Muốn đổi tiêu đề → sửa `videos: [` trong `index.html`:

```js
videos: [
  { src: 'video-1.mp4', title: 'Thước phim đầu tiên của chúng mình', note: 'Bấm để xem' },
],
```

> **Video chỉ được tải khi bấm vào** — mở trang không tải video nào, nên trang vào rất nhanh và không giật.
> Muốn thẻ video có ảnh nền riêng, thêm `poster: 'anh-1.jpg'` (ảnh nằm trong `images/`) vào mục video.
>
> Nên nén video dưới ~50MB để phát cho mượt (dùng HandBrake hoặc CapCut để nén).

---

## 5. Thêm nhạc nền

Chép 1 file nhạc vào **`music/`** và đổi tên thành **`song.mp3`**.

Nhạc sẽ tự bật khi bấm mở món quà. Ở góc phải dưới có nút ♫ để bật/tắt.

---

## 6. Đổi ngày bắt đầu yêu

Mở `index.html`, tìm dòng:

```js
startDate: '2026-10-10T00:00:00',
```

Hiện tại đã đặt sẵn **10/10/2026**. Nếu muốn tính từ đúng giờ hai đứa bắt đầu yêu, thêm giờ vào sau chữ `T`,
ví dụ `2026-10-10T20:30:00`. Đồng hồ ngày / giờ / phút / giây sẽ tự tính lại.

> Dưới 1 năm bên nhau, trang sẽ đếm ngược tới **kỷ niệm tháng** (1 tháng, 2 tháng…);
> từ 1 năm trở lên sẽ đếm ngược tới **kỷ niệm năm**.

---

## 7. Những chỗ có thể sửa thêm

| Muốn đổi | Tìm trong `index.html` |
|---|---|
| Tên hiển thị | Gõ Ctrl + H, thay `Nho Nam` và `Như Ý` |
| Lá thư | Tìm `<!-- ✏️ Sửa lá thư ở đây -->` |
| Lời tỏ tình toàn màn hình | Tìm `id="loveOverlay"` |
| Màu sắc | Phần `:root{ --pink-400: ... }` đầu file CSS |

---

## 8. Các hiệu ứng có trong trang

- Màn hình mở đầu bằng trái tim đập, bung tim khi chạm.
- Tim hồng trôi lơ lửng khắp nền, quầng sáng chuyển động chậm.
- **Bấm bất kỳ đâu** → tim & ánh sáng bung ra, đôi khi hiện chữ "Nho Nam yêu Như Ý".
- Con trỏ chuột phát sáng có quầng bám theo.
- Đồng hồ đếm ngày bên nhau + đếm ngược tới kỷ niệm tiếp theo.
- Ảnh dạng polaroid nghiêng nhẹ, bấm vào mở khung lớn kèm dòng chữ **"Nho Nam yêu Như Ý"**.
- Video: thẻ phim chỉ tải khi bấm vào — mở trang nhanh, không lag; bấm để mở trình phát lớn.
- Nút trái tim cuối trang → màn hình tỏ tình "Nho Nam yêu Như Ý" với tim mưa.
- Thanh tiến trình cuộn, hiệu ứng hiện dần khi cuộn trang.

---

## 9. Đưa lên mạng (tuỳ chọn)

Cách dễ nhất:

1. Vào [netlify.com/drop](https://app.netlify.com/drop).
2. Kéo **cả thư mục `nhuy`** vào.
3. Nhận link dạng `https://ten-ngau-nhien.netlify.app` — gửi cho người yêu 💗

Hoặc dùng Vercel / GitHub Pages / Cloudflare Pages — chỉ cần tải cả thư mục lên.

---

## 10. Lưu ý

- Cần Internet **lần đầu** để tải font đẹp (Google Fonts). Không có mạng trang vẫn chạy, chỉ đổi font.
- Trang đã tối ưu tốc độ: **không tải video khi mở trang**, ảnh tải dần khi cuộn tới, nên mở rất nhanh và không giật.
- Nên dùng Chrome, Edge hoặc Cốc Cốc bản mới.
- Nếu đổi tên file ảnh/video thì nhớ sửa lại trong `CONFIG` (phần đầu thẻ `<script>`).
- Toàn bộ website nằm trong 1 file `index.html` — muốn sao lưu chỉ cần chép cả thư mục.

Chúc hai đứa thật nhiều ngày đáng đếm ♡
