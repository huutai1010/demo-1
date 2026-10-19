# Chúc Mừng 20/10 💖 — Animation Web

Thiệp chúc mừng Ngày Phụ Nữ Việt Nam 20/10 dạng web animation, phong cách dễ thương, tông hồng – gradient.

Đây là **web tĩnh** (static) 100%: chỉ có HTML/CSS/JS thuần, **không cần build**, không cần `npm install`.

## Cấu trúc

```
demo-1/
├── index.html      # toàn bộ trang (HTML + CSS + JS trong 1 file)
├── image/          # ảnh kỷ niệm
│   ├── my_1.jpg
│   ├── my_2.jpg
│   └── my_3.jpg
├── vercel.json     # cấu hình cache cho Vercel (không bắt buộc)
└── .gitignore
```

Trang gồm 3 phần:
1. **Thiệp chúc mừng** — thỏ vẽ bằng CSS (vẫy tay, chớp mắt), chữ rơi từng ký tự, lời chúc chạy chữ, tim bung khi bấm.
2. **Album ảnh** — polaroid nghiêng, băng dính, cuộn tới thì ảnh trượt lên; bấm vào ảnh để xem lớn (lightbox, có ‹ › và phím ←/→/Esc).
3. **Cây lá trái tim** — tán cây là hình trái tim làm từ ~70 chiếc lá tim; gió định kỳ thổi cho lá tim bay đi rồi cây mọc lá mới.

## Xem thử ở máy

Mở trực tiếp `index.html` bằng trình duyệt (double click) là xong.
Hoặc chạy 1 static server nhỏ:

```bash
npx serve .
```

## Deploy lên Vercel (miễn phí)

### Cách 1 — Nhanh nhất, không cần GitHub (khuyến nghị)

```bash
cd "C:\Users\huuta\OneDrive\Desktop\demo-1"
npx vercel        # lần đầu sẽ hỏi đăng nhập (mở trình duyệt, xác nhận email)
npx vercel --prod # đẩy lên bản chính thức
```

Lần chạy đầu tiên nó sẽ hỏi vài câu, cứ chọn theo gợi ý:

| Câu hỏi | Trả lời |
| --- | --- |
| Set up and deploy? | `Y` |
| Which scope? | chọn tài khoản của bạn |
| Link to existing project? | `N` |
| What's your project's name? | `demo-1` (hoặc tên bạn thích) |
| In which directory is your code located? | `./` (Enter) |
| Want to modify these settings? | `N` |

Sau khi xong, Vercel in ra URL dạng `https://demo-1-xxxx.vercel.app`.
Lần sau muốn cập nhật chỉ cần chạy lại `npx vercel --prod`.

### Cách 2 — Nối với GitHub (tự động deploy mỗi khi push)

1. Tạo repository trống trên github.com (không thêm README/gitignore).
2. Trong thư mục này, chạy:

```bash
cd "C:\Users\huuta\OneDrive\Desktop\demo-1"
git init
git add .
git commit -m "Chuc mung 20/10"
git branch -M main
git remote add origin https://github.com/<tên-bạn>/<tên-repo>.git
git push -u origin main
```

3. Vào [vercel.com/new](https://vercel.com/new) → chọn repo vừa push →
   **Framework Preset: Other**, **Build Command: để trống**, **Output Directory: để trống** → Deploy.

Từ đó mỗi lần `git push` là web tự cập nhật.

### Cách 3 — Không cài gì, kéo thả

Vào **https://app.netlify.com/drop** → kéo cả thư mục `demo-1` vào → nhận link ngay.
(Netlify và Cloudflare Pages cũng miễn phí tương tự Vercel, cách làm giống hệt.)

## Lưu ý

- **Ảnh là ảnh cá nhân**: sau khi deploy, ai có link đều xem được.
  Muốn riêng tư hơn thì: đặt tên project khó đoán, hoặc dùng **Cloudflare Pages + Cloudflare Access** (miễn phí, chặn bằng email), hoặc Vercel password-protection (gói trả phí).
- Đổi ảnh: bỏ file mới vào `image/` rồi sửa `src="image/my_1.jpg"` trong `index.html` (nằm trong thẻ `<button class="polaroid">`).
- Muốn đổi lời chúc: tìm mảng `wishes` và các thẻ `<figcaption>` trong `index.html`.
