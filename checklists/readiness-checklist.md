# Readiness Checklist – Lab 05

- [x] **Database ready:** container DB đã chạy và phản hồi `pg_isready`.
- [x] **AI service ready:** container AI service trả về `200` cho endpoint `/health`.
- [x] **API ready:** container API trả `200` cho `/health`.
- [x] **Environment variables:** `.env` đã được thiết lập đúng.
- [x] **Network & Ports:** mạng `team-internal` hoạt động; containers đều healthy.
- [ ] **Image tags:** chưa kiểm tra build tag `v0.1.0-<team>` và push registry.

Ghi chú thêm những vấn đề gặp phải hoặc điều chỉnh tại đây:

- AI service ban đầu lỗi `ModuleNotFoundError: No module named 'fastapi'`.
- Đã tạo Dockerfile riêng cho `src/ai_service` và build bằng Docker Compose.
- API bị `unhealthy` do healthcheck sử dụng `curl` nhưng image không có `curl`.
- Đã đổi healthcheck sang dùng Python (`urllib.request`) và container chuyển sang healthy.