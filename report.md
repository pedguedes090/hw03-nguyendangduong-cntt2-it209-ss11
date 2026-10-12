# Báo cáo kiểm thử Gradle Dependency Cache

Workflow bật `cache: 'gradle'` trong `actions/setup-java@v5`. Gradle Wrapper và các dependency đã tải được lưu trong cache Actions để lần chạy sau có thể khôi phục.

| Lần chạy | Cache | Tổng thời gian job | Kết quả |
|---|---|---:|---|
| Lần đầu | Chưa có cache phù hợp | Ghi nhận trong GitHub Actions | Chờ chạy trên GitHub |
| Lần sau | Khôi phục cache Gradle | Ghi nhận trong GitHub Actions | Chờ chạy trên GitHub |

Thời gian phụ thuộc runner và trạng thái cache tại thời điểm chạy nên không ghi số liệu giả. Sau khi push, đối chiếu thời gian hai lần chạy ở tab **Actions** và kiểm tra log setup-java có thông báo khôi phục Gradle cache.

