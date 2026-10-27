# Portfolio CV - Phan Huy Hoàng

Trang portfolio cá nhân giới thiệu Phan Huy Hoàng, định hướng Frontend Developer. Dự án được xây dựng dưới dạng website tĩnh bằng HTML và CSS, phù hợp để xem trực tiếp trên trình duyệt hoặc triển khai trên một web server tĩnh.

## Chức năng

- Giới thiệu bản thân và định hướng nghề nghiệp.
- Hiển thị các kỹ năng, dự án tiêu biểu và thông tin liên hệ.
- Điều hướng tới từng phần trên cùng một trang.
- Bố cục responsive cho điện thoại, máy tính bảng và máy tính.
- Không cần backend, cơ sở dữ liệu hoặc bước biên dịch.

## Công nghệ

- HTML5: cấu trúc nội dung và các vùng điều hướng.
- CSS3: giao diện, Flexbox, CSS Grid, responsive và hiệu ứng cuộn.
- Nginx (tùy chọn): phục vụ website trong Docker.

JavaScript hiện không được dùng để vận hành các chức năng của trang. Các công nghệ khác được liệt kê trong phần kỹ năng là nội dung giới thiệu của portfolio.

## Yêu cầu môi trường

Để mở trang trực tiếp, chỉ cần một trình duyệt web hiện đại. Không bắt buộc cài Node.js, npm hay công cụ build.

Để chạy web server cục bộ, cần Python 3. Để chạy bằng Docker, cần Docker Engine hoặc Docker Desktop đang hoạt động và có thể tải image `nginx:alpine`.

## Cài đặt

Tải hoặc giải nén mã nguồn vào máy, sau đó mở terminal tại thư mục dự án. Cấu trúc chính:

```text
.
├── index.html
├── README.md
└── assets/
	├── css/
	│   └── styles.css
	└── img/
		└── avatar.jpg
```

Không cần cài đặt các gói phụ thuộc. Có thể mở `index.html` trực tiếp bằng trình duyệt; để kiểm tra qua HTTP, hãy dùng một trong các cách chạy bên dưới.

## Cấu hình và cá nhân hóa

Website không có file cấu hình riêng, biến môi trường hay thông tin bí mật. Nội dung được chỉnh trực tiếp trong `index.html`; giao diện được chỉnh trong `assets/css/styles.css`.

Trước khi xuất bản, nên kiểm tra và cập nhật:

- Tên, phần giới thiệu, kỹ năng và nội dung các dự án trong `index.html`.
- Ảnh đại diện tại `assets/img/avatar.jpg` (giữ tên file hoặc cập nhật đường dẫn `src`).
- Email và các liên kết GitHub, LinkedIn trong phần liên hệ. Một số liên kết hiện là liên kết mẫu; hãy thay bằng địa chỉ thật. Đồng thời bảo đảm giá trị `mailto:` khớp với email hiển thị.
- Mô tả trang và thông tin tác giả trong phần `<head>` nếu dùng cho hồ sơ khác.

## Chạy thử

### Windows

Mở PowerShell tại thư mục dự án và chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có nhưng đã cài Python, dùng `python -m http.server 8000`. Mở [http://localhost:8000](http://localhost:8000) trong trình duyệt. Dừng server bằng `Ctrl+C`.

### macOS

Mở Terminal, chuyển tới thư mục dự án rồi chạy:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Dừng server bằng `Ctrl+C`.

### Linux

Mở terminal tại thư mục dự án và chạy:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Dừng server bằng `Ctrl+C`.

### Docker

Cài và khởi động Docker trước, sau đó chạy lệnh tại thư mục gốc của dự án. Docker sẽ gắn mã nguồn chỉ đọc vào Nginx; không cần build image riêng.

macOS / Linux:

```bash
docker run --rm -d --name phh-portfolio -p 8080:80 -v "$PWD:/usr/share/nginx/html:ro" nginx:alpine
```

Windows PowerShell:

```powershell
docker run --rm -d --name phh-portfolio -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

Windows Command Prompt:

```bat
docker run --rm -d --name phh-portfolio -p 8080:80 -v "%cd%:/usr/share/nginx/html:ro" nginx:alpine
```

Mở [http://localhost:8080](http://localhost:8080) để kiểm tra. Dừng và xóa container bằng:

```bash
docker stop phh-portfolio
```

Nếu cổng `8080` đang được sử dụng, thay `8080` ở phía trái của `-p` bằng một cổng khác, ví dụ `8081:80`.

## Kiểm tra nhanh

- Trang tải được tại địa chỉ localhost và các mục điều hướng cuộn tới đúng phần.
- Ảnh đại diện cùng ảnh minh họa dự án hiển thị bình thường.
- Thu nhỏ cửa sổ hoặc mở trên thiết bị di động để kiểm tra bố cục responsive.
- Khi chạy Docker, kiểm tra trang tại cổng đã ánh xạ và dừng container sau khi thử.

## Thông tin liên hệ

- Tác giả: Phan Huy Hoàng
- Email: [hoangphanhuy31206@gmail.com](mailto:hoangphanhuy31206@gmail.com)
- GitHub: `github.com/phanhuyhoang` (cập nhật liên kết thật trong trang trước khi sử dụng)
- LinkedIn: `linkedin.com/in/phanhuyhoang` (cập nhật liên kết thật trong trang trước khi sử dụng)
