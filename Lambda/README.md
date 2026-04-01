# AWS Lambda Function Lab

Hướng dẫn từng bước tạo AWS Lambda Function.

## Các bước thực hiện

### Bước 1 - Truy cập Lambda Console
![Lambda1](screenshot/Lambda1.png)
- Đăng nhập AWS Console
- Tìm kiếm và chọn dịch vụ **Lambda**

### Bước 2 - Tạo Function mới
![Lambda2](screenshot/Lambda2.png)
- Nhấn **Create function**
- Chọn **Author from scratch**

### Bước 3 - Cấu hình Function
![Lambda3](screenshot/Lambda3.png)
- Đặt **Function name**
- Chọn **Runtime** (Python, Node.js, ...)

### Bước 4 - Cấu hình IAM Role
![Lambda4](screenshot/Lambda4.png)
- Tạo hoặc chọn **Execution role**
- Nhấn **Create function**

### Bước 5 - Viết Code
![Lambda5](screenshot/Lambda5.png)
- Viết code trong phần **Code source**
- Nhấn **Deploy** để lưu

### Bước 6 - Tạo Test Event
![Lambda6](screenshot/Lambda6.png)
- Chọn **Test** → **Create new event**
- Đặt tên và cấu hình event

### Bước 7 - Chạy Test
![Lambda7](screenshot/Lambda7.png)
- Nhấn **Test** để chạy function
- Kiểm tra kết quả trong **Execution results**

### Bước 8 - Xem Logs
![Lambda8](screenshot/Lambda8.png)
- Xem logs trong **CloudWatch Logs**

### Bước 9 - Cấu hình Trigger
![Lambda9](screenshot/Lambda9.png)
- Thêm **Trigger** cho function (API Gateway, S3, ...)

### Bước 10 - Hoàn thành
![Lambda10](screenshot/Lambda10.png)
- Kiểm tra và xác nhận function hoạt động

## Tài liệu tham khảo
- [AWS Lambda Documentation](https://docs.aws.amazon.com/lambda/)
- [AWS Lambda Pricing](https://aws.amazon.com/lambda/pricing/)
