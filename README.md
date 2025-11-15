# Hệ thống Quản lý Đảng viên (Local)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![CryptoJS](https://img.shields.io/badge/CryptoJS-AES_Encrypted-red?style=for-the-badge)

Đây là một công cụ mini-app được thiết kế cho công tác quản lý Đảng viên tại Chi bộ, với ưu tiên **bảo mật tuyệt đối**. Toàn bộ ứng dụng được gói gọn trong **một tệp HTML duy nhất**, không cần máy chủ, không cần cài đặt và không cần kết nối Internet.

Dữ liệu được **mã hoá AES** bằng mật khẩu của người dùng và lưu trữ an toàn ngay trên `localStorage` của trình duyệt.

## 🔐 Tại sao lại là Local-Only (Không Deploy)?

Đây là một lựa chọn thiết kế có chủ đích dựa trên yêu cầu nghiệp vụ:

* **Bảo mật tuyệt đối:** Dữ liệu quản lý (CCCD, Số thẻ Đảng, SĐT...) là thông tin nhạy cảm. Bằng cách chạy 100% local, dữ liệu **không bao giờ rời khỏi máy tính** của người dùng, loại bỏ mọi nguy cơ tấn công qua mạng.
* **Chi phí bằng 0:** Không tốn tiền hosting, tên miền, hay dịch vụ database.
* **Hoạt động độc lập:** Không cần Internet. Có thể mang laptop đi bất cứ đâu và sử dụng ngay lập tức.
* **Tốc độ:** Mọi thao tác (thêm, sửa, lọc, sắp xếp) đều được phản hồi tức thì.

## ✨ Tính năng Nổi bật

* **Mã hoá AES:** Toàn bộ dữ liệu được mã hoá bằng mật khẩu do người dùng tự đặt. Dữ liệu thô trong `localStorage` hoàn toàn không thể đọc được.
* **Quản lý Đảng viên (CRUD):** Quản lý đầy đủ các trường thông tin (SĐT, Học vấn, Chính trị, Chuyên môn...).
* **Quản lý Huy hiệu Đảng:**
    * Tự động tính **Tuổi Đảng** (tính từ ngày vào Đảng **Dự bị**).
    * Cho phép đánh dấu các mốc Huy hiệu đã nhận (30, 40, 45,... 90 năm).
    * Tự động phát hiện và cảnh báo "Huy hiệu sắp tới" cho mốc *tiếp theo* mà Đảng viên *chưa* nhận.
* **Công cụ Phân tích:**
    * Modal "Xem chi tiết" hiển thị cả "Tuổi đời" và "Tuổi Đảng" để tránh nhầm lẫn.
    * Tự động tính tuổi Đảng tại 4 mốc lễ (03/02, 19/5, 02/09, 07/11) cho một năm bất kỳ do người dùng chọn.
* **Lọc & Sắp xếp Nâng cao:**
    * Menu lọc gom gọn (Sắp xếp theo Tuổi Đảng, Tên; Lọc theo Giới tính, Huy hiệu).
    * Tìm kiếm "Full-text" trên nhiều trường (Tên, Quê quán, SĐT, CCCD...).
* **In ấn Chuyên nghiệp:** Nút "In Hồ sơ" tự động tạo một trang A4 Sơ yếu lý lịch chuẩn (có ô 4x6 để dán ảnh) và mở cửa sổ in.
* **Bảo toàn Dữ liệu:**
    * **Backup:** Xuất file `.json.txt` (đã mã hoá) để sao lưu an toàn.
    * **Restore:** Nhập file backup (hỗ trợ cả file JSON cũ không mã hoá và file `.txt` mới đã mã hoá).
* **Làm việc với Excel (CSV):** Hỗ trợ "Tải file mẫu", "Nhập từ CSV" và "Xuất ra CSV" (bao gồm tất cả các trường mới).
* **Xác thực Dữ liệu:** Tích hợp tính năng "Dữ liệu thông minh" (Validation) để cảnh báo khi người dùng nhập sai logic (ví dụ: Ngày chính thức trước ngày dự bị, SĐT sai định dạng...).
* **Tất cả trong Một:** Toàn bộ ứng dụng (HTML, CSS, JS, Thư viện, Hướng dẫn) nằm trong **1 file duy nhất**.

## 🚀 Cách sử dụng

1.  Tải toàn bộ mã nguồn về máy tính của bạn.
2.  Nhấn đúp chuột vào file 'qldangvien.html' để mở bằng trình duyệt (Khuyên dùng Chrome, Firefox, Edge).
3.  **Lần đầu tiên:**
    * Một cửa sổ "Đã khoá" sẽ hiện ra.
    * Nhập một mật khẩu mà bạn mong muốn và nhấn "Mở khoá".
    * Mật khẩu này sẽ trở thành chìa khoá vĩnh viễn của bạn.
    * **TUYỆT ĐỐI KHÔNG LÀM MẤT MẬT KHẨU NÀY!**
4.  **Từ lần sau:** Nhập đúng mật khẩu đã tạo để giải mã và vào ứng dụng.
5.  Sử dụng các nút bấm và xem Hướng dẫn (?) bên trong ứng dụng để biết thêm chi tiết.
6.  **Rất quan trọng:** Thường xuyên nhấn **"Xuất JSON"** để sao lưu file backup đã mã hoá (`.txt`) vào nơi an toàn (USB, Google Drive).

## 💻 Công nghệ sử dụng

* **HTML5**
* **TailwindCSS (via CDN):** Để tạo giao diện nhanh chóng và hiện đại.
* **JavaScript (ES6+):** Xử lý toàn bộ logic nghiệp vụ, DOM, và sự kiện.
* **CryptoJS (via CDN):** Thư viện chuẩn để thực hiện mã hoá và giải mã AES.
* **LocalStorage:** Sử dụng bộ nhớ của trình duyệt để lưu trữ dữ liệu (đã mã hoá).

## 🧑‍💻 Tác giả

Được phát triển bởi **Phan Hoàng Anh**, theo nhu cầu của Chi bộ Khóm Đông An, phường Long Xuyên, An Giang.
