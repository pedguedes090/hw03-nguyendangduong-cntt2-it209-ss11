# Bài 3 — Tối ưu CI với Gradle Dependency Cache

**Sinh viên:** Nguyễn Đăng Dương  
**Lớp:** CNTT2  
**Môn học:** IT209 — Session 11

Workflow dùng `actions/setup-java@v5` với `cache: 'gradle'` rồi chạy unit test. Báo cáo đối chiếu thời gian thực tế được lưu trong [report.md](report.md); GitHub Actions sẽ cung cấp kết quả sau khi workflow chạy.

## Chạy cục bộ

```bash
./gradlew test
```

Trên Windows có thể chạy `gradlew.bat test`.

