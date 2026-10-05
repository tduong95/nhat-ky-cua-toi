# Nhật ký của tôi

Blog ảnh và bài viết cá nhân bằng tiếng Việt, xây dựng với [Astro](https://astro.build) và xuất bản bằng GitHub Pages. Không cần backend.

URL dự kiến sau khi bật Pages: https://tduong95.github.io/nhat-ky-cua-toi/

## Chạy local

```bash
npm install
npm run dev      # http://localhost:4321/nhat-ky-cua-toi/
npm run build    # build ra thư mục dist/
npm run preview
```

## Cấu trúc nội dung

- `src/content/posts/*.md`: mỗi file là một bài viết (tên file = đường dẫn bài).
- `public/images/`: ảnh dùng cho bài viết.
- `src/pages/index.astro`: trang chủ và phần giới thiệu.

## Thêm bài viết và ảnh

1. Chép ảnh vào `public/images/` (ví dụ `chuyen-di.jpg`).
2. Tạo `src/content/posts/chuyen-di.md`:

```md
---
title: Tiêu đề bài viết
date: 2026-10-10
description: Mô tả ngắn hiển thị trên thẻ bài viết.
cover: /images/chuyen-di.jpg
coverAlt: Mô tả ảnh bìa
featured: true        # tuỳ chọn: hiện ở trang chủ
draft: false          # true để ẩn bài
gallery:              # tuỳ chọn
  - src: /images/chuyen-di-2.jpg
    alt: Mô tả ảnh
    caption: Chú thích
---
Nội dung bài viết bằng Markdown.
```

3. Commit và push lên `main`; website sẽ tự được build lại.

## Xuất bản bằng GitHub Pages

Workflow `.github/workflows/deploy.yml` build và deploy mỗi khi push lên `main` (hoặc chạy tay ở tab Actions → *Run workflow*).

Website chưa được xác nhận là đã deploy. Nếu workflow báo lỗi chưa bật Pages, vào **Settings → Pages → Build and deployment → Source** và chọn **GitHub Actions**, rồi chạy lại workflow. Sau khi chạy thành công, trang có tại https://tduong95.github.io/nhat-ky-cua-toi/.

Nếu đổi tên repository, cập nhật `base` trong `astro.config.mjs`.
