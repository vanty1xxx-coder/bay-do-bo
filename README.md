# Bẫy Dò Bò

Webapp PWA chọn ngẫu nhiên 1–10 tên, hoạt hình đàn bò, âm nhạc tổng hợp bằng Web Audio API, Google Sign-In, Firestore lưu dữ liệu. Không dùng nhạc có bản quyền.

## Firebase Console
1. Tạo Firebase project trên https://console.firebase.google.com/.
2. Build → Authentication → Get started → Sign-in method → Google → Enable → Save.
3. Build → Firestore Database → Create database. Trong tab Rules dán nội dung `firestore.rules` rồi Publish.
4. Project settings → General → Your apps → Web (</>) → Register app → copy `firebaseConfig` JSON.
5. Authentication → Settings → Authorized domains: thêm tên miền nơi triển khai (vd `your-project.web.app`, `your-user.github.io`), nếu chưa có.
6. Trên trang web, vào ☰ → Cấu hình Firebase → dán JSON → Lưu → Đăng nhập Google.

## Hosting
Có thể dùng Firebase Hosting (Firebase CLI: `firebase login`, `firebase use --add`, `firebase deploy --only hosting`) hoặc GitHub Pages. Firebase config của ứng dụng web là cấu hình public; không dán service account hay private key.

## Ghi chú
- Nhạc khởi chạy sau lần tương tác đầu tiên theo quy định autoplay trình duyệt.
- Dữ liệu được lưu cục bộ nếu chưa đăng nhập; khi đăng nhập, dữ liệu Firestore đã có được ưu tiên tải về.
- Không nhúng API key admin hoặc tài khoản dịch vụ vào mã nguồn.


Firebase web config đã được cấu hình sẵn cho project baybo-a5b38. Không cần nhập cấu hình trong menu.
