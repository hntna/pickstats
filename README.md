# 🏓 CLB Pickleball VTNet — Hệ thống Thống Kê

Ứng dụng quản lý thống kê trận đấu và tiền phạt cho CLB Pickleball VTNet, Quý 3/2026.

[![GitHub Pages](https://img.shields.io/badge/Demo-GitHub%20Pages-blue?style=flat-square&logo=github)](https://YOUR_USERNAME.github.io/YOUR_REPO_NAME)

---

## ✨ Tính năng

- 🏆 **Bảng xếp hạng** thành viên theo số trận thắng
- 💰 **Tính tiền phạt** tự động theo công thức CLB
- 📋 **Lịch sử trận đấu** đầy đủ
- 🔐 **Quản trị viên** có thể thêm / sửa / xoá kết quả
- 🔥 **Firebase Realtime Database** — đồng bộ dữ liệu thực thời trên mọi thiết bị
- 📵 **Offline fallback** — dùng được khi mất kết nối

---

## 🚀 Hướng dẫn Setup

### Bước 1: Tạo Firebase Project

1. Truy cập [console.firebase.google.com](https://console.firebase.google.com)
2. Nhấn **"Add project"** → đặt tên → nhấn **Continue**
3. Vào **Build → Realtime Database → Create Database**
4. Chọn vùng: `asia-southeast1 (Singapore)`
5. Chọn **"Start in test mode"** (cho phép đọc/ghi trong 30 ngày)

### Bước 2: Lấy Firebase Config

1. Vào **Project Settings** (bánh răng ⚙️ góc trái)
2. Chọn tab **"General"** → kéo xuống **"Your apps"**
3. Nhấn **"Add app"** → chọn **Web** (`</>`)
4. Copy đoạn `firebaseConfig`

### Bước 3: Cập nhật Config trong file HTML

Mở `VTNet Pickleball_stats.html`, tìm đoạn:

```javascript
const firebaseConfig = {
  apiKey: "...",
  authDomain: "...",
  databaseURL: "...",
  // ...
};
```

Thay bằng config của bạn.

### Bước 4: Cài đặt Firebase Rules

Vào **Realtime Database → Rules**, dán nội dung sau:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

> ⚠️ Rules này cho phép mọi người ghi dữ liệu. Phù hợp cho nhóm nội bộ. Bảo mật thực tế phụ thuộc vào mật khẩu admin trong file JS.

---

## 🌐 Deploy lên GitHub Pages

### Lần đầu (tạo repo mới)

```bash
git init
git add .
git commit -m "feat: init pickleball stats app"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

### Bật GitHub Pages

1. Vào **Settings → Pages**
2. Source: **"Deploy from a branch"**
3. Branch: `main` / `root`
4. Nhấn **Save** → đợi ~1 phút
5. URL: `https://YOUR_USERNAME.github.io/YOUR_REPO/`

### Cập nhật sau này

```bash
git add .
git commit -m "update: thêm kết quả trận mới"
git push
```

---

## 🔐 Tài khoản Admin mặc định

> ⚠️ **Bảo mật**: File này là **public** trên GitHub. Hãy đổi mật khẩu trong file HTML trước khi deploy!

Tìm dòng này trong file HTML và thay mật khẩu:
```javascript
const ADMINS = { admin: 'your_password', vtnet: 'your_password2' };
```

---

## 🛠️ Stack kỹ thuật

| Công nghệ | Mục đích |
|-----------|----------|
| HTML / CSS / JavaScript | Giao diện & logic |
| Firebase Realtime Database | Lưu trữ & đồng bộ dữ liệu |
| GitHub Pages | Hosting miễn phí |
| Google Fonts (Fredoka One + Nunito) | Typography |

---

*CLB Pickleball VTNet · Hệ thống quản lý nội bộ · Quý 3/2026*
