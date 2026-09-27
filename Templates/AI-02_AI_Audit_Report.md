# [AI-02] Báo cáo Kiểm tra AI – HW01

**Sinh viên:** Dương Trọng Hòa  
**MSSV:** 23120127  
**Ngày:** 27/09/2026  

---

## Artifact 1: Mindmap Vai trò QA/QC theo ISTQB

| Mục | Nội dung |
|-----|---------|
| **(1) Prompt + Công cụ** | **Prompt:** "Hãy vẽ một mindmap (dạng Mermaid markdown) về các vai trò QA/QC theo chuẩn ISTQB Foundation Level Syllabus mới nhất..."<br/>**Công cụ:** Antigravity (Claude Opus 4.6)<br/>**Thời gian:** 23:06 27/09/2026 |
| **(2) Đầu ra AI** | Xem `Mindmap/ISTQB_QA_QC_Mindmap.md` – sơ đồ Mermaid đầy đủ các nhánh. |
| **(3) Đánh giá** | **CHƯA ĐẦY ĐỦ** – AI tạo mindmap gần đúng nhưng thiếu 3 yếu tố quan trọng theo ISTQB CTFL v4.0. |
| **(4) Lý do** | Theo ISTQB CTFL v4.0: (1) Giám sát và Kiểm soát Kiểm thử là hoạt động riêng biệt (§1.4.3); (2) Kiểm thử Chấp nhận Vận hành (OAT) là phân loại riêng (§2.2.4); (3) Kiểm thử Tĩnh bao gồm Review và Phân tích Tĩnh (Chương 3) bị bỏ sót hoàn toàn. |
| **(5) Sinh viên sửa** | Bổ sung "Giám sát và Kiểm soát Kiểm thử" thành nhánh riêng; Thêm "OAT" trong Kiểm thử Chấp nhận; Thêm nhánh "Kiểm thử Tĩnh" hoàn chỉnh. Xem bản sửa trong `Mindmap/ISTQB_QA_QC_Mindmap.md`. |

---

## Artifact 2: Nghiên cứu 20 Lỗi Phần mềm 2022-2026

| Mục | Nội dung |
|-----|---------|
| **(1) Prompt + Công cụ** | **Prompt:** "Tìm và tổng hợp 20 lỗi phần mềm nổi bật được công bố từ 2022-2026..."<br/>**Công cụ:** Antigravity (Claude Opus 4.6)<br/>**Thời gian:** 23:07 27/09/2026 |
| **(2) Đầu ra AI** | Xem `Report/Requirement2_Software_Defects.md` – danh sách 20 lỗi với chi tiết. |
| **(3) Đánh giá** | **CHƯA ĐẦY ĐỦ** – AI xác định đúng các lỗi thực tế nhưng một số phân loại mức độ nghiêm trọng cần sửa và có 3 link nguồn bị hallucinate. |
| **(4) Lý do** | AI tạo link URL không tồn tại (The Verge, Ars Technica) – đây là hallucination điển hình. Ngoài ra, AI đánh giá sai CVSS libwebp là 10.0 trong khi NVD chính thức ghi 8.8. Theo ISTQB §5.5, mức độ nghiêm trọng cần dựa trên framework chuẩn hóa. |
| **(5) Sinh viên sửa** | Thay thế 3 link hallucinate bằng nguồn đã xác minh (Gizmodo, Simon Willison Blog); Sửa CVSS libwebp từ "10.0" thành "8.8 (Cao) theo NVD chính thức"; Kiểm tra chéo tất cả CVE với NVD. |

---

## Artifact 3: 15 Test Case cho Quạt điện

| Mục | Nội dung |
|-----|---------|
| **(1) Prompt + Công cụ** | **Prompt:** "Thiết kế 15 test case cho quạt điện đứng gia dụng..."<br/>**Công cụ:** Antigravity (Claude Opus 4.6)<br/>**Thời gian:** 23:08 27/09/2026 |
| **(2) Đầu ra AI** | Xem `Report/Requirement3_Physical_Product.md` – 15 test case đầy đủ. |
| **(3) Đánh giá** | **CHƯA ĐẦY ĐỦ** – AI tạo 12 test case hợp lý nhưng bỏ sót các edge case liên quan đến tương tác vật lý thực tế. |
| **(4) Lý do** | Theo ISTQB §4.4 về kỹ thuật dựa trên kinh nghiệm, edge case thường đến từ kiến thức miền và tương tác vật lý mà AI không có. AI thiếu đầu vào giác quan (sờ, nghe, ngửi) cần thiết cho kiểm thử sản phẩm vật lý (ISTQB §2.2.1). |
| **(5) Sinh viên sửa** | Bổ sung 3 edge case AI bỏ sót: (1) TC-13: Quạt hoạt động khi lồng bảo vệ bị lỏng; (2) TC-14: Tiếng ồn bất thường khi đổi chiều xoay; (3) TC-15: Phục hồi sau mất điện/chập điện. Có screenshot hội thoại AI chứng minh AI không tạo được. |

---

## Tóm tắt Độ chính xác AI

| Phân loại | Số lượng | Tỷ lệ |
|-----------|:---:|:---:|
| HỢP LỆ | 0 | 0% |
| KHÔNG HỢP LỆ | 0 | 0% |
| CHƯA ĐẦY ĐỦ | 3 | 100% |

### Kết luận: Khi nào nên/không nên dùng AI?

**NÊN dùng AI cho:**
- Nghiên cứu và thu thập thông tin ban đầu
- Tạo template và framework có cấu trúc (mindmap, format test case)
- Brainstorm kịch bản kiểm thử cho chức năng phổ biến
- Tổ chức và định dạng dữ liệu lớn

**KHÔNG NÊN dùng AI cho:**
- Xác minh dữ liệu thời gian thực (URL tin tuyển dụng, mức lương)
- Tương tác với thiết bị vật lý và kiểm thử giác quan
- Nhận diện edge case yêu cầu kiến thức miền và kinh nghiệm thực tế
- Chụp screenshot với thông tin đăng nhập cá nhân (yêu cầu chống gian lận)
- Quay video thực thi với giọng nói tường thuật
