# Phần Phê bình AI – HW01 (200–300 từ)

**Sinh viên:** Dương Trọng Hòa  
**MSSV:** 23120127  

---

Trong quá trình thực hiện HW01, tôi sử dụng AI (Antigravity / Claude Opus 4.6) rộng rãi cho việc nghiên cứu, cấu trúc nội dung và thiết kế test case. Dù AI thể hiện khả năng tổ chức thông tin và tạo đầu ra có cấu trúc ấn tượng, nhiều thiếu sót nghiêm trọng đã bộc lộ.

**AI sai ở đâu:** Mindmap ISTQB do AI tạo đã bỏ sót ba yếu tố quan trọng: "Giám sát và Kiểm soát Kiểm thử" như hoạt động độc lập, Kiểm thử Chấp nhận Vận hành (OAT), và toàn bộ nhánh Kiểm thử Tĩnh (Static Testing). Đây đều là khái niệm cơ bản trong ISTQB CTFL v4.0. Điều này cho thấy xu hướng đơn giản hóa quá mức của AI – tạo ra đầu ra trông toàn diện nhưng thiếu các chi tiết thiết yếu. Trong phần nghiên cứu lỗi phần mềm, AI đôi khi phân loại sai mức độ nghiêm trọng – ví dụ đánh giá một CVE có CVSS 9.8 là "Cao" thay vì "Nghiêm trọng" – cho thấy AI dựa vào mẫu ngôn ngữ chung thay vì hệ thống đánh giá chuẩn hóa.

**AI thiên vị và thiếu sót ở đâu:** Với test case cho thiết bị vật lý, AI thiên vị rõ ràng về "happy path" – chỉ tập trung vào điều kiện vận hành bình thường. AI hoàn toàn bỏ sót các edge case liên quan đến xuống cấp cơ khí (lồng bảo vệ bị lỏng), kiểm thử phụ thuộc giác quan (tiếng ồn khi đổi chiều xoay), và kịch bản đặc thù môi trường (chập điện – rất phổ biến ở Việt Nam). Sự thiên vị này xuất phát từ việc AI được huấn luyện trên tài liệu và kịch bản số hóa, thiếu hoàn toàn trải nghiệm thế giới vật lý.

**Bài học rút ra:** AI là điểm khởi đầu tuyệt vời để tạo khung cấu trúc và nội dung ban đầu, nhưng tuyệt đối không được coi là nguồn cuối cùng. Con người cần review để: (1) xác minh tính chính xác với nguồn uy tín như ISTQB và NVD, (2) bổ sung kiến thức chuyên môn từ trải nghiệm thực tế, (3) nhận diện edge case phụ thuộc ngữ cảnh. Quy trình hiệu quả nhất là "AI tạo, con người kiểm tra và bổ sung."

*Số từ: ~261 từ*
