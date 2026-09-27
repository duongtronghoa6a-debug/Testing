# Mindmap Vai Trò QA/QC theo ISTQB

## Sơ đồ Mermaid

```mermaid
mindmap
  root((QA/QC trong<br/>Kiểm thử<br/>Phần mềm))
    Đảm bảo Chất lượng vs Kiểm soát Chất lượng
      QA["QA – Đảm bảo Chất lượng"]
        Hướng quy trình
        Phương pháp phòng ngừa
        Tập trung cải thiện quy trình phát triển
        Hoạt động: Đánh giá quy trình, Đào tạo, Tuân thủ chuẩn
      QC["QC – Kiểm soát Chất lượng"]
        Hướng sản phẩm
        Phương pháp phát hiện
        Tập trung tìm lỗi trong sản phẩm
        Hoạt động: Kiểm thử, Review, Thanh tra
    Các vai trò QA/QC chính
      Test Manager
        Lập kế hoạch và chiến lược kiểm thử
        Phân bổ nguồn lực
        Quản lý rủi ro
        Giao tiếp với các bên liên quan
      Test Analyst
        Thiết kế test case
        Chuẩn bị dữ liệu kiểm thử
        Phân tích yêu cầu
        Báo cáo lỗi
      Technical Test Analyst
        Kiểm thử phi chức năng
        Tự động hóa kiểm thử
        Kiểm thử hiệu suất
        Kiểm thử bảo mật
      Test Automation Engineer
        Thiết kế framework
        Phát triển script
        Tích hợp CI/CD
        Lựa chọn công cụ
      AI Test Engineer["AI/LLM Test Engineer (2026+)"]
        Xác thực mô hình AI
        Kiểm thử prompt
        Phát hiện bias
        Kiểm thử hallucination
    Quy trình Kiểm thử Cơ bản ISTQB
      Lập Kế hoạch Kiểm thử
        Xác định phạm vi và mục tiêu
        Nhận diện rủi ro
        Phân bổ nguồn lực
        Định nghĩa chiến lược kiểm thử
      Giám sát và Kiểm soát Kiểm thử
        Theo dõi tiến độ so với kế hoạch
        Thực hiện hành động khắc phục
        Báo cáo trạng thái kiểm thử
      Phân tích Kiểm thử
        Phân tích cơ sở kiểm thử
        Xác định điều kiện kiểm thử
        Đánh giá khả năng kiểm thử
      Thiết kế Kiểm thử
        Tạo test case
        Thiết kế dữ liệu kiểm thử
        Thiết kế môi trường kiểm thử
      Triển khai Kiểm thử
        Tạo quy trình kiểm thử
        Tạo bộ kiểm thử
        Chuẩn bị môi trường
      Thực thi Kiểm thử
        Chạy test case
        Ghi nhận kết quả
        So sánh thực tế với mong đợi
        Báo cáo lỗi
      Hoàn thành Kiểm thử
        Thu thập tài liệu kiểm thử
        Bài học kinh nghiệm
        Tạo báo cáo tổng kết
    Cấp độ Kiểm thử
      Kiểm thử Đơn vị
        Các module riêng lẻ
        Trách nhiệm lập trình viên
        Kỹ thuật hộp trắng
      Kiểm thử Tích hợp
        Kiểm thử giao diện
        Tương tác giữa các thành phần
        Top-down / Bottom-up
      Kiểm thử Hệ thống
        Kiểm thử đầu-cuối
        Chức năng và phi chức năng
        Đội kiểm thử độc lập
      Kiểm thử Chấp nhận
        UAT["Kiểm thử Chấp nhận Người dùng"]
        OAT["Kiểm thử Chấp nhận Vận hành"]
        Alpha / Beta
        Chấp nhận hợp đồng và quy định
    Kỹ thuật Kiểm thử
      Kiểm thử Tĩnh
        Review: Informal, Walkthrough, Technical, Inspection
        Phân tích tĩnh
      Kỹ thuật Hộp đen
        Phân vùng Tương đương
        Phân tích Giá trị Biên
        Bảng Quyết định
        Chuyển đổi Trạng thái
        Use Case Testing
      Kỹ thuật Hộp trắng
        Phủ Câu lệnh
        Phủ Nhánh
        Phủ Quyết định
        Phủ Điều kiện
      Kỹ thuật dựa trên Kinh nghiệm
        Dự đoán Lỗi
        Kiểm thử Khám phá
        Kiểm thử dựa trên Checklist
```

---

## 3 Lỗi Tìm được trong Mindmap do AI Tạo (Sinh viên Review)

### Lỗi 1: Thiếu "Giám sát và Kiểm soát Kiểm thử" như hoạt động riêng biệt
**Lỗi AI:** Ban đầu AI gộp "Giám sát và Kiểm soát Kiểm thử" vào "Lập Kế hoạch" như hoạt động con.  
**Sửa lỗi:** Theo ISTQB CTFL v4.0, Mục 1.4, "Giám sát và Kiểm soát Kiểm thử" là một **hoạt động kiểm thử cơ bản riêng biệt**, không phải hoạt động con của Lập Kế hoạch. Nó chạy liên tục trong suốt quy trình kiểm thử.  
**Tham chiếu ISTQB:** ISTQB CTFL v4.0, Mục 1.4.3 – "Test monitoring and control is an ongoing activity."

### Lỗi 2: Phân loại sai các loại Kiểm thử Chấp nhận
**Lỗi AI:** AI liệt kê "Alpha / Beta testing" là loại riêng biệt cạnh UAT, nhưng thiếu **Kiểm thử Chấp nhận Vận hành (OAT)** – một phân loại quan trọng.  
**Sửa lỗi:** Theo ISTQB CTFL v4.0, Mục 2.2.4, Kiểm thử Chấp nhận bao gồm: (1) UAT, (2) OAT (backup/restore, khắc phục thảm họa, quản lý người dùng, bảo trì), (3) Chấp nhận Hợp đồng và Quy định, (4) Alpha/Beta. OAT đã bị bỏ sót.  
**Tham chiếu ISTQB:** ISTQB CTFL v4.0, Mục 2.2.4

### Lỗi 3: Thiếu hoàn toàn "Kiểm thử Tĩnh" (Static Testing)
**Lỗi AI:** Mindmap chỉ có kỹ thuật kiểm thử động (hộp đen, hộp trắng, dựa trên kinh nghiệm) mà hoàn toàn bỏ sót **Kiểm thử Tĩnh** bao gồm Review (Informal Review, Walkthrough, Technical Review, Inspection) và Phân tích Tĩnh.  
**Sửa lỗi:** Theo ISTQB CTFL v4.0, Chương 3, Kiểm thử Tĩnh là phần cơ bản của kiểm thử, bổ sung cho kiểm thử động. Mindmap cần có nhánh "Kiểm thử Tĩnh" với Review và Phân tích Tĩnh.  
**Tham chiếu ISTQB:** ISTQB CTFL v4.0, Chương 3 – "Static Testing"
