# Yêu cầu 3 – Thiết kế Test Case cho Thiết bị Vật lý (25 điểm)

**Sinh viên:** Dương Trọng Hòa  
**MSSV:** 23120127  

---

## Thông tin Thiết bị

| Mục | Chi tiết |
|-----|----------|
| **Loại sản phẩm** | Quạt điện đứng (hoặc thiết bị gia dụng bạn chọn) |
| **Hãng** | ⚠️ **[BẠN CẦN TỰ ĐIỀN]** |
| **Model** | ⚠️ **[BẠN CẦN TỰ ĐIỀN]** |
| **Năm sản xuất** | ⚠️ **[BẠN CẦN TỰ ĐIỀN]** |
| **Số serial** | ⚠️ **[BẠN CẦN TỰ ĐIỀN]** – che 4 ký tự giữa (vd: SN-12\*\*\*\*89) |
| **Ảnh chụp** | ⚠️ **[BẠN CẦN TỰ CHỤP]** – thiết bị + thẻ SV trong cùng 1 khung hình |

> ⚠️ Nếu bạn không có quạt điện, hãy chọn thiết bị khác (bình lọc nước, nồi cơm điện, bóng đèn thông minh...) và điều chỉnh test case cho phù hợp.

---

## 15 Test Case

### TC-01: Kiểm tra nút Bật/Tắt nguồn

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-01 |
| **Mục tiêu** | Xác nhận quạt bật/tắt đúng cách khi nhấn nút nguồn |
| **Điều kiện trước** | Quạt đã cắm vào ổ điện hoạt động |
| **Đầu vào** | Nhấn nút bật nguồn |
| **Các bước** | 1. Đảm bảo quạt đã cắm điện và đang TẮT<br/>2. Nhấn nút BẬT<br/>3. Quan sát cánh quạt có quay không<br/>4. Nhấn nút TẮT<br/>5. Quan sát cánh quạt có dừng không |
| **Kết quả mong đợi** | Cánh quạt quay khi nhấn BẬT; quạt dừng hoàn toàn trong 10 giây khi nhấn TẮT |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | ⚠️ **[QUAY VIDEO ≤ 60s]** |

---

### TC-02: Kiểm tra điều chỉnh tốc độ

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-02 |
| **Mục tiêu** | Xác nhận tất cả các mức tốc độ (Thấp/Trung/Cao) hoạt động đúng |
| **Điều kiện trước** | Quạt đã cắm điện và đang BẬT |
| **Đầu vào** | Chuyển đổi tốc độ 1 → 2 → 3 |
| **Các bước** | 1. Bật quạt ở tốc độ 1 (Thấp)<br/>2. Cảm nhận sức gió<br/>3. Chuyển sang tốc độ 2 (Trung bình)<br/>4. Cảm nhận gió mạnh hơn<br/>5. Chuyển sang tốc độ 3 (Cao)<br/>6. Cảm nhận gió mạnh nhất |
| **Kết quả mong đợi** | Mỗi mức tốc độ tạo ra sức gió khác biệt rõ ràng; chuyển đổi mượt mà, motor không bị giật |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | ⚠️ **[QUAY VIDEO ≤ 60s]** |

---

### TC-03: Kiểm tra chức năng Xoay (Oscillation)

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-03 |
| **Mục tiêu** | Xác nhận quạt xoay đều qua trái-phải khi bật chế độ xoay |
| **Điều kiện trước** | Quạt đang BẬT ở bất kỳ tốc độ nào |
| **Đầu vào** | Nhấn nút/cần xoay |
| **Các bước** | 1. Bật quạt<br/>2. Kích hoạt chế độ xoay<br/>3. Quan sát đầu quạt xoay trái-phải<br/>4. Ước lượng góc xoay<br/>5. Tắt chế độ xoay, kiểm tra đầu quạt dừng |
| **Kết quả mong đợi** | Đầu quạt xoay mượt mà ~80-120° không bị giật; dừng ngay khi tắt chế độ xoay |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | ⚠️ **[QUAY VIDEO ≤ 60s]** |

---

### TC-04: Kiểm tra chức năng Hẹn giờ

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-04 |
| **Mục tiêu** | Xác nhận chức năng hẹn giờ tự tắt hoạt động đúng |
| **Điều kiện trước** | Quạt đang BẬT |
| **Đầu vào** | Đặt hẹn giờ ở mức ngắn nhất (vd: 30 phút hoặc 1 giờ) |
| **Các bước** | 1. Bật quạt<br/>2. Đặt hẹn giờ ở mức ngắn nhất<br/>3. Chờ hết thời gian<br/>4. Kiểm tra quạt có tự tắt không |
| **Kết quả mong đợi** | Quạt tự động tắt khi hết giờ, sai số ±2 phút |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | Không bắt buộc (timer quá dài cho video 60s) |

---

### TC-05: Kiểm tra cơ chế điều chỉnh chiều cao

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-05 |
| **Mục tiêu** | Xác nhận cơ chế điều chỉnh chiều cao khóa chắc ở các vị trí khác nhau |
| **Điều kiện trước** | Quạt đã lắp ráp và đứng thẳng |
| **Đầu vào** | Điều chỉnh chiều cao: thấp nhất, giữa, cao nhất |
| **Các bước** | 1. Nới lỏng khóa chiều cao<br/>2. Kéo cột quạt xuống thấp nhất<br/>3. Khóa lại và lắc nhẹ quạt<br/>4. Lặp lại cho vị trí giữa và cao nhất |
| **Kết quả mong đợi** | Chiều cao khóa chắc ở mỗi vị trí; quạt không bị tụt xuống hoặc lung lay |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | ⚠️ **[QUAY VIDEO ≤ 60s]** |

---

### TC-06: Kiểm tra điều chỉnh góc nghiêng (lên/xuống)

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-06 |
| **Mục tiêu** | Xác nhận đầu quạt nghiêng lên/xuống và giữ vị trí |
| **Điều kiện trước** | Quạt đang BẬT ở bất kỳ tốc độ |
| **Đầu vào** | Nghiêng đầu quạt lên và xuống bằng tay |
| **Các bước** | 1. Bật quạt ở tốc độ trung bình<br/>2. Nghiêng đầu quạt lên góc tối đa<br/>3. Thả ra, kiểm tra có giữ vị trí không<br/>4. Nghiêng xuống góc tối đa<br/>5. Thả ra, kiểm tra có giữ vị trí không |
| **Kết quả mong đợi** | Đầu quạt giữ vị trí nghiêng, không tự trượt về; phạm vi nghiêng khoảng 10-20° lên và xuống |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | Không bắt buộc |

---

### TC-07: Kiểm tra độ ổn định trên mặt phẳng

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-07 |
| **Mục tiêu** | Xác nhận quạt giữ vững trong khi hoạt động trên mặt phẳng |
| **Điều kiện trước** | Quạt đặt trên sàn phẳng, cứng |
| **Đầu vào** | Chạy quạt tốc độ cao nhất + bật xoay |
| **Các bước** | 1. Đặt quạt trên sàn gạch/gỗ phẳng<br/>2. Bật tốc độ cao nhất (mức 3)<br/>3. Bật chế độ xoay<br/>4. Quan sát 2 phút xem quạt có bị xê dịch, nghiêng, hoặc rung quá mức không |
| **Kết quả mong đợi** | Quạt đứng yên; không bị xê dịch, nghiêng, hoặc rung nguy hiểm |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | ⚠️ **[QUAY VIDEO ≤ 60s]** |

---

### TC-08: Kiểm tra an toàn dây nguồn

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-08 |
| **Mục tiêu** | Xác nhận dây nguồn nguyên vẹn và không quá nóng khi chạy lâu |
| **Điều kiện trước** | Quạt đã chạy ít nhất 30 phút |
| **Đầu vào** | Kiểm tra bằng mắt và sờ dây nguồn |
| **Các bước** | 1. Cho quạt chạy tốc độ cao nhất 30 phút<br/>2. Cẩn thận sờ dây nguồn ở nhiều điểm (đầu phích cắm, giữa dây, chỗ nối vào quạt)<br/>3. Kiểm tra có bị nóng quá, rách vỏ, lộ dây, hoặc lỏng kết nối không<br/>4. Nhẹ nhàng lay phích cắm trong ổ để kiểm tra tia lửa |
| **Kết quả mong đợi** | Dây ấm nhưng không nóng (< 45°C); không rách, không lộ dây, không có tia lửa |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | Không bắt buộc |

---

### TC-09: Kiểm tra an toàn lồng bảo vệ cánh quạt

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-09 |
| **Mục tiêu** | Xác nhận lồng bảo vệ ngăn không cho ngón tay chạm vào cánh quạt đang quay |
| **Điều kiện trước** | Quạt đang BẬT ở bất kỳ tốc độ |
| **Đầu vào** | Dùng bút (mô phỏng ngón tay trẻ em) thử chọc qua khe lồng |
| **Các bước** | 1. Bật quạt ở tốc độ thấp<br/>2. Dùng bút/bút chì thử chọc qua khe lồng bảo vệ<br/>3. Đo chiều rộng khe lồng<br/>4. Đối chiếu với tiêu chuẩn an toàn (khe phải < 12mm cho an toàn trẻ em) |
| **Kết quả mong đợi** | Bút không chạm được cánh quạt đang quay; khe lồng ≤ 12mm |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | ⚠️ **[QUAY VIDEO ≤ 60s – Dùng bút, TUYỆT ĐỐI KHÔNG dùng tay]** |

---

### TC-10: Đánh giá mức độ tiếng ồn

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-10 |
| **Mục tiêu** | Đánh giá mức tiếng ồn ở từng tốc độ |
| **Điều kiện trước** | Quạt trong phòng yên tĩnh (tiếng ồn nền < 35dB) |
| **Đầu vào** | Chạy quạt ở từng tốc độ và đo tiếng ồn |
| **Các bước** | 1. Dùng app đo decibel trên điện thoại (vd: "Decibel X", "Sound Meter")<br/>2. Đặt điện thoại cách quạt 1 mét, ngang đầu quạt<br/>3. Đo tiếng ồn ở tốc độ 1, 2, và 3<br/>4. Ghi lại kết quả |
| **Kết quả mong đợi** | Tốc độ 1: ≤ 45dB, Tốc độ 2: ≤ 55dB, Tốc độ 3: ≤ 65dB |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | Không bắt buộc |

---

### TC-11: Kiểm tra motor quá nhiệt

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-11 |
| **Mục tiêu** | Xác nhận motor không quá nóng sau khi chạy liên tục ở tốc độ cao |
| **Điều kiện trước** | Quạt hoạt động bình thường |
| **Đầu vào** | Cho quạt chạy tốc độ cao nhất liên tục 2 giờ |
| **Các bước** | 1. Bật quạt tốc độ cao nhất<br/>2. Để chạy liên tục 2 giờ<br/>3. Sau 2 giờ, cẩn thận sờ vùng vỏ motor<br/>4. Kiểm tra có mùi khét hoặc tiếng lạ không<br/>5. Kiểm tra quạt vẫn hoạt động bình thường |
| **Kết quả mong đợi** | Vỏ motor ấm nhưng không nóng nguy hiểm (< 65°C); không có mùi khét; quạt vẫn hoạt động bình thường |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Video** | Không bắt buộc |

---

### TC-12: Kiểm tra Remote (nếu có)

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-12 |
| **Mục tiêu** | Xác nhận remote điều khiển được tất cả chức năng từ khoảng cách ≥ 3 mét |
| **Điều kiện trước** | Quạt đang BẬT; remote có pin |
| **Đầu vào** | Dùng remote điều khiển BẬT/TẮT, tốc độ, xoay, hẹn giờ |
| **Các bước** | 1. Đứng cách quạt 3 mét<br/>2. Nhấn BẬT/TẮT trên remote<br/>3. Chuyển đổi tốc độ bằng remote<br/>4. Bật/tắt xoay bằng remote<br/>5. Đặt hẹn giờ bằng remote (nếu có)<br/>6. Thử từ 5 mét và từ sau vật cản |
| **Kết quả mong đợi** | Tất cả chức năng phản hồi trong 1 giây từ 3m; tín hiệu hoạt động từ 5m đường thẳng |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** – Nếu quạt không có remote, ghi N/A |
| **Đánh giá** | ⚠️ **[PASS/FAIL hoặc N/A]** |
| **Video** | Không bắt buộc |

---

### ⭐ TC-13: EDGE CASE – Quạt hoạt động khi lồng bảo vệ bị lỏng (AI KHÔNG TÌM ĐƯỢC)

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-13 **(Edge Case – AI bỏ sót)** |
| **Mục tiêu** | Kiểm tra độ an toàn khi lồng bảo vệ phía trước bị lỏng 1 khớp trong lúc hoạt động |
| **Điều kiện trước** | Quạt hoạt động bình thường |
| **Đầu vào** | Nới lỏng nhẹ 1 khớp của lồng bảo vệ phía trước |
| **Các bước** | 1. TẮT quạt<br/>2. Nới lỏng nhẹ 1 khớp giữ lồng trước (KHÔNG THÁO HẲN)<br/>3. BẬT quạt ở tốc độ 1<br/>4. Quan sát lồng có rung quá mức hoặc nguy cơ rơi không<br/>5. TẮT NGAY nếu phát hiện nguy hiểm |
| **Kết quả mong đợi** | Quạt vẫn hoạt động; lồng không bị rơi khi chỉ lỏng 1 khớp |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Tại sao AI bỏ sót** | AI tập trung vào kịch bản "vận hành bình thường". AI không xét đến tình trạng xuống cấp vật lý (lắp ráp không hoàn chỉnh) vì AI thiếu kinh nghiệm tương tác vật lý. Trong thực tế, khớp lồng có thể bị lỏng dần theo thời gian do hao mòn – đây là edge case an toàn thực tế. |
| **Video** | ⚠️ **[QUAY VIDEO ≤ 60s – AN TOÀN TRÊN HẾT, TẮT NGAY NẾU NGUY HIỂM]** |

> ⚠️ **BẠN CẦN:** Chụp screenshot hội thoại AI cho thấy AI KHÔNG tạo ra test case này + viết giải thích tại sao AI bỏ sót.

---

### ⭐ TC-14: EDGE CASE – Tiếng ồn bất thường khi đổi chiều xoay (AI KHÔNG TÌM ĐƯỢC)

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-14 **(Edge Case – AI bỏ sót)** |
| **Mục tiêu** | Phát hiện tiếng click, nghiến, hoặc rít bất thường tại điểm đổi chiều xoay (tận cùng trái và phải) |
| **Điều kiện trước** | Quạt đang BẬT với chế độ xoay đang hoạt động |
| **Đầu vào** | Lắng nghe tại các điểm đổi chiều xoay |
| **Các bước** | 1. Bật quạt ở tốc độ 1 (yên tĩnh nhất) + bật xoay<br/>2. Đứng gần quạt (cách 0.5m)<br/>3. Lắng nghe kỹ tại thời điểm đầu quạt đổi chiều (trái→phải và phải→trái)<br/>4. Quay video/ghi âm tiếng ồn bất thường<br/>5. So sánh tiếng ồn tại cả hai điểm đổi chiều |
| **Kết quả mong đợi** | Đổi chiều mượt mà và gần như im lặng; không có tiếng nghiến, click, hoặc rít |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Tại sao AI bỏ sót** | AI không thể nghe âm thanh và không hiểu về hao mòn cơ khí. Cơ chế xoay (bánh răng/cam) phát ra tiếng ồn đặc biệt tại điểm đổi chiều do độ rơ (backlash) – đây là lỗi thực tế phổ biến mà chỉ có thể phát hiện bằng cách lắng nghe trực tiếp. |
| **Video** | ⚠️ **[QUAY VIDEO ≤ 60s – Ghi âm rõ ràng]** |

> ⚠️ **BẠN CẦN:** Chụp screenshot hội thoại AI + viết giải thích.

---

### ⭐ TC-15: EDGE CASE – Phục hồi sau mất điện/chập điện (AI KHÔNG TÌM ĐƯỢC)

| Mục | Nội dung |
|-----|----------|
| **Mã TC** | TC-15 **(Edge Case – AI bỏ sót)** |
| **Mục tiêu** | Kiểm tra hành vi quạt sau khi bị gián đoạn nguồn điện ngắn (mô phỏng chập/mất điện) |
| **Điều kiện trước** | Quạt đang chạy tốc độ 2 + bật xoay |
| **Đầu vào** | Nhanh chóng rút phích và cắm lại trong 2 giây |
| **Các bước** | 1. Cho quạt chạy tốc độ 2 + bật xoay<br/>2. Nhanh chóng rút phích cắm khỏi ổ điện<br/>3. Chờ 2 giây<br/>4. Cắm lại<br/>5. Quan sát: quạt có tự khởi động lại không? Có nhớ cài đặt trước đó không?<br/>6. Kiểm tra có tia lửa tại phích cắm không |
| **Kết quả mong đợi** | Quạt: (a) tự khởi động lại ở cài đặt cũ, HOẶC (b) giữ nguyên TẮT và cần bật tay (cả hai đều chấp nhận). Không có tia lửa, khói, hoặc tiếng lạ. |
| **Kết quả thực tế** | ⚠️ **[TỰ LÀM]** |
| **Đánh giá** | ⚠️ **[PASS/FAIL]** |
| **Tại sao AI bỏ sót** | AI thường kiểm tra hành vi ổn định (steady-state) thay vì tình huống quá độ/phục hồi (transient/recovery). Chập/mất điện rất phổ biến ở Việt Nam (đặc biệt mùa mưa bão) – là điều kiện thực tế ảnh hưởng đến độ tin cậy sản phẩm. AI thiếu ngữ cảnh môi trường về tình trạng lưới điện địa phương. |
| **Video** | ⚠️ **[QUAY VIDEO ≤ 60s]** |

> ⚠️ **BẠN CẦN:** Chụp screenshot hội thoại AI + viết giải thích.

---

## Bảng Tổng hợp Thực thi

| Mã TC | Đã thực hiện? | Có video? | Tìm được lỗi? | Mô tả lỗi |
|-------|:---:|:---:|:---:|---|
| TC-01 | ⚠️ | ⚠️ | ⚠️ | |
| TC-02 | ⚠️ | ⚠️ | ⚠️ | |
| TC-03 | ⚠️ | ⚠️ | ⚠️ | |
| TC-04 | ⚠️ | | ⚠️ | |
| TC-05 | ⚠️ | ⚠️ | ⚠️ | |
| TC-06 | ⚠️ | | ⚠️ | |
| TC-07 | ⚠️ | ⚠️ | ⚠️ | |
| TC-08 | ⚠️ | | ⚠️ | |
| TC-09 | ⚠️ | ⚠️ | ⚠️ | |
| TC-10 | ⚠️ | | ⚠️ | |
| TC-11 | ⚠️ | | ⚠️ | |
| TC-12 | ⚠️ | | ⚠️ | |
| TC-13 | ⚠️ | ⚠️ | ⚠️ | |
| TC-14 | ⚠️ | ⚠️ | ⚠️ | |
| TC-15 | ⚠️ | ⚠️ | ⚠️ | |

- **Tổng test case:** 15
- **Tối thiểu cần thực thi:** ≥ 5 (có video)
- **Tối thiểu lỗi cần tìm:** ≥ 5
- **Edge case AI bỏ sót:** 3 (TC-13, TC-14, TC-15)

---

## Danh sách Lỗi Tìm được (GitHub Issues)

> ⚠️ **BẠN CẦN:**
> 1. Tạo GitHub repository cho HW01
> 2. Ghi lại tất cả lỗi tìm được dưới dạng Issues trên GitHub
> 3. Chụp screenshot trang Issues có hiển thị GitHub username của bạn
> 4. Mục tiêu: tìm ≥ 5 lỗi từ thiết bị thật

| Lỗi # | GitHub Issue # | Tiêu đề | Mức nghiêm trọng | TC liên quan |
|--------|---------------|---------|:-:|:-:|
| D-01 | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| D-02 | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| D-03 | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| D-04 | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| D-05 | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
