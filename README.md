# Wello - Ứng Dụng Theo Dõi Sức Khỏe

## Giới Thiệu

Wello là ứng dụng di động được phát triển bằng Flutter, giúp người dùng theo dõi và quản lý sức khỏe cá nhân một cách toàn diện. Ứng dụng cung cấp các công cụ để theo dõi dinh dưỡng, tập luyện, và các chỉ số sức khỏe quan trọng.

## Tính Năng Chính

### Xác Thực & Đăng Ký
- Đăng ký và đăng nhập bằng email/mật khẩu
- Đăng nhập bằng tài khoản Google
- Xác thực OTP qua email
- Khôi phục mật khẩu
- Khảo sát sức khỏe ban đầu để cá nhân hóa mục tiêu

### Quản Lý Dinh Dưỡng
- Ghi nhận bữa ăn với thông tin dinh dưỡng chi tiết
- Theo dõi lượng calo tiêu thụ hàng ngày
- Phân tích macro (protein, carbs, chất béo)
- Lịch sử bữa ăn theo từng bữa trong ngày
- Lưu món ăn yêu thích
- Tạo món ăn tùy chỉnh

### Theo Dõi Tập Luyện
- Ghi nhận các bài tập với thời lượng và cường độ
- Thư viện bài tập với giá trị MET
- Lịch sử tập luyện và calories đốt cháy
- Theo dõi tiến độ tập luyện

### Theo Dõi Nước Uống
- Ghi nhận lượng nước uống hàng ngày
- Nhắc nhở thông minh với lịch trình tùy chỉnh
- Trực quan hóa mục tiêu hydration

### Giám Sát Sức Khỏe
- Tính toán BMI theo thời gian thực với cảnh báo sức khỏe
- Theo dõi cân nặng theo thời gian
- Tiến độ mục tiêu với biểu đồ trực quan
- Tổng kết hoạt động hàng ngày

### Quản Lý Hồ Sơ
- Cập nhật thông tin cá nhân (tên, tuổi, giới tính, chiều cao, cân nặng)
- Tải ảnh đại diện
- Điều chỉnh mục tiêu (giảm/tăng/duy trì cân nặng)
- Thiết lập mức độ hoạt động

## Công Nghệ Sử Dụng

### Framework & Ngôn Ngữ
- Flutter 3.9.2
- Dart 3.0+

### Kiến Trúc
- Clean Architecture với 3 lớp: Data, Domain, UI
- Repository Pattern
- Provider cho quản lý state

### Thư Viện Chính
- `provider` - Quản lý state
- `http` - HTTP client
- `google_fonts` - Font chữ
- `firebase_core` - Firebase
- `firebase_messaging` - Push notifications
- `google_sign_in` - Đăng nhập Google
- `shared_preferences` - Lưu trữ local
- `image_picker` - Chọn ảnh

## API Backend

**Base URL:** `https://api.memap.id.vn:8280/wello-backend/api`

### Endpoints Chính

**Authentication:**
- `POST /auth/login` - Đăng nhập
- `POST /auth/register` - Đăng ký
- `POST /auth/google-login` - Đăng nhập Google
- `POST /auth/verify-otp` - Xác thực OTP
- `POST /auth/forgot-password` - Quên mật khẩu

**Nutrition:**
- `GET /nutrition/daily-summary` - Tổng kết dinh dưỡng
- `POST /nutrition/log-food` - Ghi nhận bữa ăn
- `GET /nutrition/history` - Lịch sử ăn uống
- `GET /food/all` - Danh sách thực phẩm

**Exercise:**
- `GET /workout/exercises` - Danh sách bài tập
- `POST /workout/log` - Ghi nhận tập luyện
- `GET /workout/daily` - Tổng kết tập luyện

**Profile:**
- `GET /user/profile` - Thông tin người dùng
- `PUT /profile/{userId}/weight` - Cập nhật cân nặng
- `POST /profile/{userId}/avatar/base64` - Tải ảnh đại diện

**Survey:**
- `GET /survey/questions` - Câu hỏi khảo sát
- `POST /survey/submit` - Gửi khảo sát
- `POST /survey/calculate-bmi` - Tính BMI

## Cài Đặt

### Yêu Cầu
- Flutter SDK 3.9.2 trở lên
- Android Studio hoặc VS Code
- Android SDK (cho Android) / Xcode (cho iOS)

### Các Bước

1. Clone repository:
```bash
git clone <repository-url>
cd wello_frontend
```

2. Cài đặt dependencies:
```bash
flutter pub get
```

3. Cấu hình Firebase:
- Thêm `google-services.json` vào `android/app/`
- Thêm `GoogleService-Info.plist` vào `ios/Runner/`

4. Chạy ứng dụng:
```bash
flutter run
```

5. Build APK release:
```bash
flutter build apk --release
```

## Cấu Trúc Thư Mục

```
lib/
├── core/                   # Utilities và constants
│   ├── navigation/        # Quản lý routes
│   ├── services/          # Services (notifications, etc.)
│   └── utils/             # Helper functions
├── data/                  # Data layer
│   ├── data_source/       # Remote API data sources
│   ├── models/            # Request/Response models
│   └── repositories/      # Repository implementations
├── domain/                # Domain layer
│   ├── entities/          # Business entities
│   ├── providers/         # State management
│   └── repositories/      # Repository interfaces
└── ui/                    # Presentation layer
    ├── auth/              # Màn hình xác thực
    ├── home/              # Trang chủ
    ├── profile/           # Hồ sơ người dùng
    ├── meal_selection/    # Chọn và ghi nhận thực phẩm
    ├── favorites/         # Món ăn yêu thích
    ├── question/          # Khảo sát ban đầu
    └── widgets/           # UI components tái sử dụng
```

## Thông Tin Dự Án

**Loại:** Tiểu Luận Chuyên Ngành  
**Năm:** 2024  
**Framework:** Flutter  
**License:** MIT

---

**Phát triển bởi Trung Doan**
