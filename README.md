# 🏫 VKU Field Survey PWA

Ứng dụng Progressive Web App (PWA) hỗ trợ kiểm tra, đánh giá và ghi nhận hiện trạng cơ sở vật chất, trang thiết bị và vệ sinh môi trường tại **Đại học CNTT & TT Việt - Hàn (VKU)**. 

Ứng dụng được tối ưu hóa cho thiết bị di động, thiết kế theo chiến lược **Offline-First**, hoạt động trơn tru ngay cả khi không có kết nối Internet và tự động đồng bộ dữ liệu về Google Sheets khi quay lại Online.

---

## 🌟 Tính Năng Nổi Bật

- 📱 **Trải nghiệm như App bản địa (PWA):** Cài đặt trực tiếp vào màn hình chính (Home Screen) trên cả iOS và Android mà không cần qua App Store hay Google Play.
- 📶 **Hoạt động Ngoại tuyến 100% (Offline-First):** Sử dụng Service Worker (Cache-First) và lưu trữ dữ liệu khảo sát trực tiếp trên thiết bị với `IndexedDB` (`Dexie.js`).
- ⚡ **Tự Động Đồng Bộ (Auto-Sync):** Tự động phát hiện khi có mạng trở lại và đẩy dữ liệu chờ xử lý lên Google Sheets ngầm định.
- 📋 **Biểu mẫu khảo sát toàn diện:**
  - Trang thiết bị phòng học (Đèn, quạt, máy chiếu, điều hòa, bàn ghế).
  - Kết nối Internet & Wi-Fi VKU.
  - Tình trạng Nhà vệ sinh (Nước, bồn rửa, vệ sinh).
  - Vệ sinh môi trường & Cảnh quan chung.
- 📷 **Nén ảnh tự động (Canvas Compressor):** Chụp ảnh minh chứng trực tiếp từ camera, tự động nén kích thước trước khi lưu trữ để tiết kiệm dung lượng bộ nhớ.
- 📍 **Ghi nhận GPS:** Tự động lấy tọa độ địa lý tại vị trí kiểm tra thực địa.

---

## 🛠️ Công Nghệ Sử Dụng

- **Frontend:** HTML5, CSS3, JavaScript (ES6+), Tailwind CSS (CDN), FontAwesome Icons.
- **Database Cục bộ:** IndexedDB via [Dexie.js](https://dexie.org/).
- **PWA Capabilities:** Web App Manifest, Service Workers.
- **Backend / Storage:** Google Sheets API via Google Apps Script (GAS).
- **Hosting / Deployment:** Cloudflare Pages / GitHub Pages.

---

## 📂 Cấu Trúc Dự Án

```text
vku-field-survey-pwa/
├── icons/                  # Thuộc tính Icon PWA (192x192, 512x512)
│   ├── icon-192.png
│   └── icon-512.png
├── js/
│   ├── app.js              # Logic giao diện, sự kiện form & Auto-Sync
│   ├── db.js               # Cấu hình Dexie.js (IndexedDB) & Nén ảnh
│   └── sw-register.js      # Đăng ký Service Worker
├── index.html              # Giao diện chính người dùng (Mobile-First)
├── manifest.json           # Cấu hình PWA Manifest
├── sw.js                   # Service Worker xử lý caching offline
├── .gitignore              # Cấu hình loại bỏ file không cần thiết trên Git
└── README.md               # Tài liệu hướng dẫn dự án
