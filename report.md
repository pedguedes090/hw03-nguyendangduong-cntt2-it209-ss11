# Báo cáo kiểm thử Gradle Dependency Cache

Workflow bật `cache: 'gradle'` trong `actions/setup-java@v5`. Gradle Wrapper và các dependency đã tải được lưu trong cache Actions để lần chạy sau có thể khôi phục.

| Lần chạy | Cache | Tổng thời gian job | `./gradlew test` | Kết quả |
|---|---|---:|---:|---|
| Lần đầu (push ban đầu) | Cache miss, tạo cache | 49 giây | 40 giây | Thành công |
| Lần hai (push kế tiếp) | Cache hit, khôi phục Gradle và Wrapper | 20 giây | 15 giây | Thành công |

Trong lần thứ hai, log `setup-java` hiển thị `Cache restored successfully` cho cả Gradle dependencies và Gradle Wrapper. Tổng thời gian job giảm 29 giây (xấp xỉ 59%); thời gian bước test giảm 25 giây (xấp xỉ 62%). Đây là số liệu của hai lần chạy trên GitHub-hosted runner trong phiên kiểm thử này; thời gian thực tế có thể thay đổi theo tải runner và cache.

