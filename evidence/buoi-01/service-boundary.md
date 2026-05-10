# Service Boundary của nhóm

## 1. Thông tin nhóm

- Tên nhóm: Nhóm 7
- Lớp: CNTT 17-09
- Thành viên:
  - Nguyễn Hữu Hưng
- Service nhóm phụ trách:
  - Camera Stream Processing Service
- Sản phẩm tổng thể của lớp:
  - Hệ thống tiếp nhận và xử lý luồng camera thông minh

## 2. Actor

Ai tương tác với hệ thống/service?

- Người dùng giám sát camera
- Quản trị viên hệ thống
- Thiết bị camera IP
- AI Detection Service

## 3. System Boundary

Nhóm em xây phần nào?

Phần nhóm kiểm soát:

- Tiếp nhận luồng camera RTSP/HTTP
- Xử lý stream video
- Chuyển tiếp dữ liệu camera
- Quản lý trạng thái camera
- API truy cập camera stream

Phần nhóm chỉ tích hợp:

- AI Detection Service
- Database
- Frontend Dashboard
- Notification Service

## 4. Service Boundary

Service của nhóm có trách nhiệm gì?

- Nhận luồng video từ camera
- Kiểm tra trạng thái camera
- Streaming video realtime
- Quản lý kết nối camera
- Cung cấp API cho frontend và AI service

Service KHÔNG làm gì?

- Không huấn luyện AI model
- Không xử lý giao diện frontend
- Không gửi thông báo trực tiếp
- Không lưu trữ video dài hạn

## 5. Input / Output

### Input

- RTSP Camera Stream
- HTTP Stream
- Camera configuration
- Request từ frontend

### Output

- Live video stream
- Camera status
- Stream metadata
- API response JSON

## 6. API dự kiến

| Method | Endpoint | Mục đích |
|---|---|---|
| GET | /health | Kiểm tra service |
| POST | /api/camera/connect | Kết nối camera |
| GET | /api/camera/stream | Lấy luồng camera |
| GET | /api/camera/status | Kiểm tra trạng thái camera |
| DELETE | /api/camera/disconnect | Ngắt kết nối camera |

## 7. Phụ thuộc service khác

Service này gọi đến service nào?

- PostgreSQL Database
- Redis Cache
- AI Detection Service

Service nào gọi đến service này?

- Frontend Dashboard
- Mobile App
- Monitoring Service

## 8. Sơ đồ minh họa

```mermaid
flowchart LR
    Camera[IP Camera] --> StreamService[Camera Stream Service]
    StreamService --> DB[(PostgreSQL)]
    StreamService --> Redis[(Redis Cache)]
    StreamService --> AI[AI Detection Service]
    Frontend[Frontend Dashboard] --> StreamService