# Deploy to GitHub Pages

Hướng dẫn triển khai website lên GitHub Pages.

## Yêu cầu

- Tài khoản GitHub
- Git đã được cài đặt trên máy tính

## Các bước triển khai

### Option 1: User/Organization Pages (username.github.io)

1. **Tạo repository mới** trên GitHub:
   - Tên repository: `yourusername.github.io` (thay `yourusername` bằng tên GitHub của bạn)
   - Đặt là **public**
   - Khởi tạo với README (tùy chọn)

2. **Clone và setup**:
   ```bash
   git clone https://github.com/yourusername/yourusername.github.io.git
   cd yourusername.github.io
   ```

3. **Copy các file**:
   ```bash
   # Copy tất cả các file vào repository
   cp -r /path/to/project/* .
   cp -r /path/to/project/.github .
   ```

4. **Commit và push**:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```

5. **Bật GitHub Pages**:
   - Vào repository Settings → Pages
   - Trong phần "Source", chọn **"GitHub Actions"**
   - Workflow sẽ tự động triển khai website

6. **Truy cập website**:
   - Website sẽ có sẵn tại: `https://yourusername.github.io`
   - Có thể mất vài phút cho lần triển khai đầu tiên

## Cấu trúc thư mục

Repository nên có cấu trúc như sau:

```
.
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions workflow
├── assets/                    # Tài nguyên (hình ảnh, sách, v.v.)
│   ├── books/
│   ├── covers/
│   └── img/
├── dflip/                     # Thư viện flipbook
├── index.html                 # Trang chủ
├── bookview.html              # Trang đọc sách
└── README.md
```

## Cập nhật website

Sau khi thay đổi:

```bash
git add .
git commit -m "Update website"
git push
```

GitHub Actions sẽ tự động build và triển khai website.

## Tên miền tùy chỉnh (Tùy chọn)

Để sử dụng tên miền tùy chỉnh:

1. Thêm file `CNAME` vào thư mục gốc của repository với tên miền của bạn:
   ```
   yourdomain.com
   ```

2. Cấu hình DNS với nhà cung cấp tên miền:
   - Thêm bản ghi CNAME trỏ đến `yourusername.github.io`

3. Cập nhật repository Settings → Pages → Custom domain
