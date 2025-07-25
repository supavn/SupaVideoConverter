# SupaVideoConverter

🌐 **Ngôn ngữ khác / Other Languages:**
- [English](README.md)
- [Bahasa Indonesia](README-id.md)
- [한국어](README-kr.md)

---

Ứng dụng desktop đa nền tảng để chuyển đổi định dạng video được xây dựng với Electron, React và Ant Design, phát triển bởi Supa

## Tính năng

- **Hỗ trợ đa định dạng**: Chuyển đổi MP4, AVI, MOV, MKV, WMV, FLV, WEBM, M4V, 3GP, OGV sang MP4
- **Tùy chọn chất lượng**: Nhiều cài đặt chất lượng sẵn có (Thấp, Trung bình, Cao, Lossless) và tùy chỉnh bitrate
- **Thay đổi độ phân giải**: Hỗ trợ 720p, 1080p và độ phân giải tùy chỉnh
- **Xử lý hàng loạt**: Chuyển đổi nhiều file cùng lúc
- **Theo dõi tiến trình**: Hiển thị tiến trình chuyển đổi thời gian thực với thời gian còn lại dự kiến
- **Kéo & Thả**: Dễ dàng chọn file với tính năng kéo thả
- **Đa nền tảng**: Hoạt động trên Windows và macOS

## Ảnh chụp màn hình

### Màn hình chào mừng
![Welcome Screen](screenshots/screenshot-01-welcome.png)
*Màn hình chào mừng hiển thị khi khởi động ứng dụng*

### Giao diện chính
![Main Screen](screenshots/screenshot-02-main-screen.png)
*Giao diện chuyển đổi chính hiển thị chọn file, theo dõi tiến trình và điều khiển chuyển đổi*

### Chọn ngôn ngữ
![Language Select](screenshots/screenshot-03-language-select.png)
*Tùy chọn chọn ngôn ngữ cho hỗ trợ đa ngôn ngữ*

### Cài đặt video
![Video Settings](screenshots/screenshot-04-video-settings.png)
*Cài đặt chi tiết chuyển đổi video bao gồm chất lượng, độ phân giải và tùy chọn đầu ra*

## Công nghệ sử dụng

- **Electron** ^28.0.0 - Framework ứng dụng desktop
- **React** ^18.2.0 - Framework UI frontend
- **Ant Design** ^5.12.0 - Thư viện component UI
- **Vite** ^5.0.0 - Công cụ build
- **FFmpeg** - Engine xử lý video
- **fluent-ffmpeg** ^2.1.2 - Wrapper Node.js cho FFmpeg

## Cài đặt

1. Clone repository:
```bash
git clone <repository-url>
cd video-converter-app
```

2. Cài đặt dependencies:
```bash
npm install
```

## Phát triển

Để chạy ứng dụng ở chế độ phát triển:

```bash
npm run electron:dev
```

Điều này sẽ:
1. Khởi động Vite dev server trên http://localhost:5173
2. Tự động khởi chạy ứng dụng Electron
3. Kích hoạt hot module replacement cho React components

## Build

Để build ứng dụng React:
```bash
npm run build
```

Để đóng gói ứng dụng Electron để phân phối:
```bash
npm run electron:dist
```

Điều này sẽ tạo ra các file phân phối trong thư mục `dist`:
- **Windows**: File cài đặt `.exe`
- **macOS**: Gói `.dmg`

## Scripts

- `npm run dev` - Chỉ khởi động Vite dev server
- `npm run build` - Build ứng dụng React cho production
- `npm run preview` - Xem trước production build
- `npm run electron` - Chạy Electron với các file đã build
- `npm run electron:dev` - Chạy ở chế độ phát triển
- `npm run electron:pack` - Đóng gói mà không build
- `npm run electron:dist` - Build và đóng gói để phân phối

## Cấu trúc dự án

```
video-converter-app/
├── src/                           # Mã nguồn ứng dụng React
│   ├── components/                # React components
│   │   ├── FileInput/            # Component chọn file
│   │   ├── ConversionSettings/   # Cấu hình cài đặt
│   │   ├── ProgressTracking/     # Hiển thị tiến trình
│   │   └── OutputManagement/     # Kết quả và đầu ra
│   ├── hooks/                    # Custom React hooks
│   ├── utils/                    # Utility functions
│   ├── styles/                   # Global styles
│   └── App.jsx                   # Ứng dụng chính
├── electron/                     # Electron main process
│   ├── main.js                   # Main process entry
│   ├── preload.js               # Preload script
│   └── services/                # Backend services
│       ├── VideoProcessor.js    # FFmpeg wrapper
│       ├── FileManager.js       # File operations
│       └── SettingsManager.js   # Settings persistence
├── build/                       # Cấu hình build
├── resources/                   # Static resources
└── package.json                 # Cấu hình dự án
```

## Cách sử dụng

1. **Chọn file**: Kéo thả file video hoặc sử dụng trình duyệt file
2. **Cấu hình cài đặt**: Chọn độ phân giải đầu ra, chất lượng và thư mục đích
3. **Bắt đầu chuyển đổi**: Khởi động quá trình chuyển đổi
4. **Theo dõi tiến trình**: Giám sát tiến trình thời gian thực cho từng file
5. **Truy cập kết quả**: Mở thư mục đầu ra hoặc phát file đã chuyển đổi

## Định dạng được hỗ trợ

**Định dạng đầu vào:**
- MP4, AVI, MOV, MKV, WMV, FLV, WEBM, M4V, 3GP, OGV

**Định dạng đầu ra:**
- MP4 (H.264/AAC)

## Cài đặt chất lượng

- **Thấp**: 1 Mbps - File nhỏ hơn, chất lượng thấp hơn
- **Trung bình**: 3 Mbps - Cân bằng chất lượng và kích thước
- **Cao**: 8 Mbps - Chất lượng cao hơn, file lớn hơn
- **Lossless**: 50 Mbps - Chất lượng tối đa
- **Tùy chỉnh**: Bitrate do người dùng định nghĩa (1-50 Mbps)

## Tùy chọn độ phân giải

- **Giữ nguyên**: Duy trì độ phân giải gốc
- **720p**: 1280x720 (HD)
- **1080p**: 1920x1080 (Full HD)
- **Tùy chỉnh**: Kích thước do người dùng định nghĩa

## Yêu cầu hệ thống

- **Node.js** 16+ (cho phát triển)
- **macOS** 10.15+ hoặc **Windows** 10+
- Ít nhất 4GB RAM để xử lý file video lớn
- Dung lượng đĩa khả dụng cho file đầu ra

## Khắc phục sự cố

### Vấn đề thường gặp

1. **Không tìm thấy FFmpeg**: Ứng dụng bao gồm FFmpeg binaries, nhưng nếu gặp vấn đề, hãy đảm bảo ứng dụng có quyền thích hợp.

2. **Xử lý file lớn**: Đối với file trên 4GB, đảm bảo bạn có đủ dung lượng đĩa và RAM.

3. **Chuyển đổi thất bại**: Kiểm tra file đầu vào không bị hỏng và thư mục đầu ra có quyền ghi.

### Vấn đề phát triển

1. **Electron không khởi động**: Đảm bảo tất cả dependencies được cài đặt với `npm install`

2. **Hot reload không hoạt động**: Kiểm tra Vite dev server đang chạy trên port 5173

3. **Build thất bại**: Xóa node_modules và cài đặt lại dependencies

## Giấy phép

MIT License - xem file LICENSE để biết chi tiết

## Đóng góp

1. Fork repository
2. Tạo feature branch
3. Thực hiện thay đổi
4. Test kỹ lưỡng
5. Gửi pull request

## Hỗ trợ

Đối với các vấn đề và yêu cầu tính năng, vui lòng tạo issue trong repository.
