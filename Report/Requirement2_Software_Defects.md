# Yêu cầu 2 – 20 Lỗi Phần mềm 2022–2026 (20 điểm)

**Sinh viên:** Dương Trọng Hòa  
**MSSV:** 23120127  

> **Yêu cầu:** 20 lỗi phần mềm công bố từ 2022-2026. Tối thiểu ≥ 5 liên quan AI/LLM. Mỗi lỗi phải tìm 1 điểm AI bias/hallucination.

---

## Bảng Tổng hợp

| # | Tên Lỗi | Ngày | Loại | Mức độ | Nguồn đã xác minh |
|---|---------|------|------|--------|:--:|
| 1 | CrowdStrike Falcon BSOD | 19/07/2024 | Truyền thống | Nghiêm trọng | ✅ |
| 2 | XZ Utils Backdoor (CVE-2024-3094) | 29/03/2024 | Truyền thống | Nghiêm trọng (CVSS 10.0) | ✅ |
| 3 | MOVEit SQL Injection (CVE-2023-34362) | 31/05/2023 | Truyền thống | Nghiêm trọng (CVSS 9.8) | ✅ |
| 4 | libwebp Buffer Overflow (CVE-2023-4863) | 11/09/2023 | Truyền thống | Cao (CVSS 8.8) | ✅ |
| 5 | Citrix Bleed (CVE-2023-4966) | 10/10/2023 | Truyền thống | Nghiêm trọng (CVSS 9.4) | ✅ |
| 6 | Spring4Shell (CVE-2022-22965) | 31/03/2022 | Truyền thống | Nghiêm trọng (CVSS 9.8) | ✅ |
| 7 | OpenSSL Punycode (CVE-2022-3602) | 01/11/2022 | Truyền thống | Cao | ✅ |
| 8 | FAA NOTAM Sập hệ thống | 11/01/2023 | Truyền thống | Nghiêm trọng | ✅ |
| 9 | GitLab Reset Mật khẩu (CVE-2023-7028) | 11/01/2024 | Truyền thống | Nghiêm trọng (CVSS 10.0) | ✅ |
| 10 | Atlassian Confluence (CVE-2023-22515) | 04/10/2023 | Truyền thống | Nghiêm trọng (CVSS 10.0) | ✅ |
| 11 | Microsoft Storm-0558 | 11/07/2023 | Truyền thống | Nghiêm trọng | ✅ |
| 12 | Apple BLASTPASS (CVE-2023-41064) | 07/09/2023 | Truyền thống | Nghiêm trọng (CVSS 8.8) | ✅ |
| 13 | Toyota Cloud Lộ dữ liệu | 12/05/2023 | Truyền thống | Cao | ✅ |
| 14 | ChatGPT Redis Race Condition | 20/03/2023 | **AI/LLM** | Cao | ✅ |
| 15 | Air Canada Chatbot Hallucination | 14/02/2024 | **AI/LLM** | Trung bình | ✅ |
| 16 | Google Gemini Bias Hình ảnh | 22/02/2024 | **AI/LLM** | Cao | ✅ |
| 17 | Google AI Overviews Hallucination | 24/05/2024 | **AI/LLM** | Cao | ✅ |
| 18 | Chevrolet Chatbot Prompt Injection | 17/12/2023 | **AI/LLM** | Trung bình | ✅ |
| 19 | DPD Chatbot Prompt Injection | 19/01/2024 | **AI/LLM** | Trung bình | ✅ |
| 20 | Slack AI Prompt Injection | 20/08/2024 | **AI/LLM** | Cao | ✅ |

**Số lỗi AI/LLM:** 7 (≥ 5 ✅)

---

## Chi tiết Từng Lỗi

---

### Lỗi 1: CrowdStrike Falcon – Sập 8.5 triệu máy Windows

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 19/07/2024 |
| **Nguồn** | [CrowdStrike Blog](https://www.crowdstrike.com/blog/falcon-update-for-windows-hosts-technical-details/) – [Microsoft Blog xác nhận con số 8.5M](https://blogs.microsoft.com/blog/2024/07/20/helping-our-customers-through-the-crowdstrike-outage/) |
| **Mô tả** | CrowdStrike đẩy bản cập nhật nội dung tự động (Channel File 291) cho Falcon sensor trên Windows. Trình thông dịch nội dung mong đợi 20 trường dữ liệu, nhưng file mới có 21 trường. Sự không khớp này vượt qua lớp kiểm tra hợp lệ và gây lỗi đọc bộ nhớ ngoài giới hạn (out-of-bounds read), tạo ra Màn Hình Xanh Chết Chóc (BSOD) ngay khi khởi động. |
| **Mức độ** | Nghiêm trọng |
| **Hậu quả** | Sập ~8.5 triệu thiết bị Windows toàn cầu (<1% tổng số máy Windows, theo Microsoft). Hủy 5.000+ chuyến bay, gián đoạn trung tâm cấp cứu 911, lịch phẫu thuật bệnh viện, hoạt động tài chính. Cần can thiệp thủ công trong Safe Mode để sửa. |
| **Giải pháp** | CrowdStrike thu hồi Channel File 291 lúc 05:27 UTC. Phân phối hướng dẫn khôi phục thủ công và USB boot. Cải tổ quy trình phát hành với kiểm tra tham số nghiêm ngặt, triển khai canary, cho phép khách hàng kiểm soát lịch cập nhật. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** – Hỏi AI giải thích sự cố này, tìm 1 điểm AI trả lời sai. *Gợi ý:* AI hay nói sai con số thiết bị bị ảnh hưởng hoặc nhầm ai là nguồn công bố (Microsoft chứ không phải CrowdStrike). |

---

### Lỗi 2: XZ Utils – Backdoor chuỗi cung ứng (CVE-2024-3094)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 29/03/2024 |
| **Nguồn** | [NVD CVE-2024-3094](https://nvd.nist.gov/vuln/detail/CVE-2024-3094) – [Openwall oss-security](https://www.openwall.com/lists/oss-security/2024/03/29/4) |
| **Mô tả** | Một người dùng bí danh "Jia Tan" thực hiện chiến dịch social engineering nhiều năm để giành quyền maintainer thư viện nén xz. Trong phiên bản 5.6.0 và 5.6.1, mã độc được cài vào build script để hook hàm RSA_public_decrypt trong OpenSSH, cho phép kẻ tấn công có khóa riêng bypass xác thực SSH và chạy lệnh tùy ý với quyền root. |
| **Mức độ** | Nghiêm trọng (CVSS 10.0) |
| **Hậu quả** | Đe dọa hạ tầng internet toàn cầu. Được phát hiện tình cờ bởi kỹ sư Microsoft Andres Freund khi điều tra độ trễ CPU 500ms trong Debian Sid, trước khi phiên bản lỗi đến được các bản phân phối Linux doanh nghiệp. |
| **Giải pháp** | Các bản phân phối bị ảnh hưởng (Fedora Rawhide/40, Debian testing/unstable) rollback về xz 5.4.x. Maintainer độc hại bị tước quyền, repository được kiểm tra và xây dựng lại. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 3: MOVEit Transfer – SQL Injection (CVE-2023-34362)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 31/05/2023 |
| **Nguồn** | [CISA Advisory AA23-158A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-158a) – [Progress Security Advisory](https://community.progress.com/s/article/MOVEit-Transfer-Critical-Vulnerability-31May2023) |
| **Mô tả** | Lỗ hổng SQL injection nghiêm trọng trong giao diện web của MOVEit Transfer cho phép kẻ tấn công không cần xác thực gửi HTTP request tùy chỉnh để thực thi SQL tùy ý, giả mạo admin, cài web shell ASPX để trích xuất dữ liệu. |
| **Mức độ** | Nghiêm trọng (CVSS 9.8) |
| **Hậu quả** | Bị khai thác hàng loạt bởi nhóm ransomware Cl0p (TA505). 2.773+ tổ chức bị xâm phạm, dữ liệu cá nhân của 90-95 triệu người bị lộ (theo Emsisoft). Nạn nhân: cơ quan liên bang Mỹ, Shell, BBC, British Airways. |
| **Giải pháp** | Progress phát hành bản vá 31/05/2023. Hướng dẫn tắt HTTP/HTTPS, kiểm tra web root, thu hồi tài khoản database, nâng cấp lên bản vá. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 4: libwebp – Heap Buffer Overflow (CVE-2023-4863)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 11/09/2023 |
| **Nguồn** | [NVD CVE-2023-4863](https://nvd.nist.gov/vuln/detail/CVE-2023-4863) – [Chrome Release](https://chromereleases.googleblog.com/2023/09/stable-channel-update-for-desktop_11.html) |
| **Mô tả** | Lỗi tràn bộ đệm heap trong thư viện libwebp (hàm BuildHuffmanTable trong dec/vp8l_dec.c) khi giải mã ảnh WebP lossless chứa bảng Huffman độc hại. Bộ phân tích cú pháp cấp phát bộ đệm không đủ, cho phép ghi bộ nhớ ngoài giới hạn và thực thi mã tùy ý từ xa chỉ bằng việc hiển thị ảnh WebP. |
| **Mức độ** | Cao (CVSS 8.8 theo NVD chính thức). *Lưu ý: CVE trùng lặp CVE-2023-5129 từng được đánh giá 10.0 nhưng đã bị MITRE từ chối.* |
| **Hậu quả** | Ảnh hưởng gần như toàn bộ hệ sinh thái internet: Chrome, Firefox, Safari, Edge, Android, và tất cả ứng dụng Electron (Slack, Discord, Signal, Teams, 1Password). Bị khai thác zero-day trước khi công bố. |
| **Giải pháp** | Google vá libwebp 1.3.2. Các trình duyệt và hệ điều hành đồng loạt phát hành cập nhật bảo mật khẩn cấp. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** – *Gợi ý: AI thường nói CVSS 10.0 nhưng thực tế NVD chính thức ghi 8.8.* |

---

### Lỗi 5: Citrix Bleed – Chiếm phiên đăng nhập (CVE-2023-4966)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 10/10/2023 |
| **Nguồn** | [CISA Advisory AA23-325A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-325a) – [Citrix CTX579459](https://support.citrix.com/s/article/CTX579459-netscaler-adc-and-netscaler-gateway-security-bulletin-for-cve20234966-and-cve20234967) |
| **Mô tả** | Lỗ hổng đọc bộ đệm ngoài giới hạn (buffer over-read) trong endpoint OIDC của Citrix NetScaler. Kẻ tấn công gửi HTTP GET với Host header quá lớn khiến response rò rỉ cookie phiên đăng nhập đang hoạt động. |
| **Mức độ** | Nghiêm trọng (CVSS 9.4) |
| **Hậu quả** | Kẻ tấn công dùng cookie bị rò rỉ để chiếm phiên doanh nghiệp, vượt qua mật khẩu và MFA. Bị khai thác bởi LockBit 3.0 và APT nhà nước chống lại Boeing và các tổ chức tài chính. |
| **Giải pháp** | Citrix phát hành cập nhật firmware 10/10/2023. Quản trị viên phải chạy lệnh CLI để hủy tất cả phiên đang hoạt động vì token đã bị đánh cắp vẫn còn hiệu lực sau khi vá. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 6: Spring4Shell – Thực thi mã từ xa (CVE-2022-22965)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 31/03/2022 |
| **Nguồn** | [Spring Framework Announcement](https://spring.io/blog/2022/03/31/spring-framework-rce-early-announcement) – [NVD CVE-2022-22965](https://nvd.nist.gov/vuln/detail/CVE-2022-22965) |
| **Mô tả** | Lỗi trong cơ chế DataBinder của Spring Framework cho phép bind tham số HTTP vào Java ClassLoader trên Java 9+. Kẻ tấn công truy cập class.module.classLoader → AccessLogValve của Tomcat → ghi web shell JSP vào thư mục gốc ứng dụng web. |
| **Mức độ** | Nghiêm trọng (CVSS 9.8) |
| **Hậu quả** | Thực thi mã từ xa không cần xác thực trên ứng dụng Java doanh nghiệp chạy Spring MVC/WebFlux trên Tomcat. Được thêm vào danh sách KEV của CISA. |
| **Giải pháp** | Spring phát hành phiên bản 5.3.18 và 5.2.20 với blacklist ràng buộc trường nghiêm ngặt. Tomcat phát hành bản vá 9.0.62. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 7: OpenSSL Punycode – Tràn bộ đệm ngăn xếp (CVE-2022-3602)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 01/11/2022 |
| **Nguồn** | [OpenSSL Security Advisory](https://www.openssl.org/news/secadv/20221101.txt) – [NVD CVE-2022-3602](https://nvd.nist.gov/vuln/detail/CVE-2022-3602) |
| **Mô tả** | Lỗi tràn bộ đệm ngăn xếp trong hàm ossl_punycode_decode của OpenSSL khi xác thực ràng buộc tên chứng chỉ X.509. Địa chỉ email Punycode sai định dạng gây tràn 4 byte (CVE-2022-3602) hoặc tràn ký tự tùy ý (CVE-2022-3786). |
| **Mức độ** | Cao (Ban đầu thông báo Nghiêm trọng; hạ xuống Cao sau khi stack canary của trình biên dịch ngăn chặn RCE trên hầu hết nền tảng) |
| **Hậu quả** | Gây lo ngại toàn cầu vì sợ tái diễn sự cố quy mô Heartbleed. Thực tế có thể làm sập máy chủ/client TLS, khả năng thực thi mã giới hạn trên kiến trúc thiếu bảo vệ stack-smashing. |
| **Giải pháp** | OpenSSL phát hành phiên bản 3.0.7 sửa kiểm tra giới hạn. OpenSSL 1.1.1 và 1.0.2 không bị ảnh hưởng. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 8: FAA NOTAM – Sập hệ thống bay toàn nước Mỹ

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 11/01/2023 |
| **Nguồn** | [FAA NOTAM Statement](https://www.faa.gov/newsroom/faa-notam-statement) – [Reuters](https://www.reuters.com/business/aerospace-defense/us-faa-says-notam-outage-caused-by-damaged-database-file-2023-01-11/) |
| **Mô tả** | Hệ thống NOTAM của FAA bị sập khi nhân viên bảo trì vô tình xóa file trong quá trình giải quyết trễ đồng bộ. Lỗi dữ liệu lan truyền qua cả hệ thống chính và dự phòng, không có failover độc lập. |
| **Mức độ** | Nghiêm trọng |
| **Hậu quả** | Lệnh cấm bay toàn quốc đầu tiên kể từ 11/09/2001. 10.000+ chuyến bay bị trễ, 1.300+ bị hủy, thiệt hại hàng chục triệu đô. |
| **Giải pháp** | Khôi phục hoàn toàn từ bản sao lưu ngoại tuyến. Thiết lập quy trình xác minh đa người, tách biệt replication, hiện đại hóa hệ thống. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 9: GitLab – Reset mật khẩu chiếm tài khoản (CVE-2023-7028)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 11/01/2024 |
| **Nguồn** | [GitLab Security Release 16.7.2](https://about.gitlab.com/releases/2024/01/11/critical-security-release-gitlab-16-7-2-released/) – [NVD CVE-2023-7028](https://nvd.nist.gov/vuln/detail/CVE-2023-7028) |
| **Mô tả** | Lỗi logic trong cơ chế reset mật khẩu: gửi mảng email (user[email][]) chứa email nạn nhân và email kẻ tấn công → token reset được gửi đến tất cả email trong mảng mà không kiểm tra quyền sở hữu. |
| **Mức độ** | Nghiêm trọng (CVSS 10.0) |
| **Hậu quả** | Kẻ tấn công không cần xác thực có thể chiếm bất kỳ tài khoản GitLab nào không bật 2FA, truy cập mã nguồn, bí mật CI/CD, pipeline build. |
| **Giải pháp** | GitLab phát hành bản vá giới hạn token reset chỉ gửi đến email chính đã xác minh, bổ sung audit logging. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 10: Atlassian Confluence – Broken Access Control (CVE-2023-22515)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 04/10/2023 |
| **Nguồn** | [Atlassian Security Advisory](https://confluence.atlassian.com/security/cve-2023-22515-privilege-escalation-vulnerability-in-confluence-data-center-and-server-1295682276.html) – [CISA Alert](https://www.cisa.gov/news-events/alerts/2023/10/04/atlassian-releases-security-advisory-confluence-data-center-and-server) |
| **Mô tả** | Lỗi kiểm soát truy cập cho phép gọi trực tiếp hành động thiết lập ban đầu (/setup/setupadministrator.action) trên instance đã được cấu hình, tạo tài khoản admin mới. |
| **Mức độ** | Nghiêm trọng (CVSS 10.0) |
| **Hậu quả** | Bị khai thác hàng loạt zero-day. Kẻ tấn công tạo tài khoản admin, xóa dữ liệu, cài web shell, trích xuất tài liệu nội bộ doanh nghiệp. |
| **Giải pháp** | Atlassian phát hành bản cập nhật chặn endpoint setup. Workaround chặn /setup/* trong reverse proxy. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 11: Microsoft Storm-0558 – Rò rỉ khóa ký & Giả mạo token

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 11/07/2023 |
| **Nguồn** | [Microsoft MSRC Post-Mortem](https://www.microsoft.com/en-us/security/blog/2023/09/06/results-of-investigation-into-compromised-microsoft-storage-key/) – [CISA Advisory AA23-193A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-193a) |
| **Mô tả** | Sự cố chuỗi: crash dump lưu khóa ký MSA do race condition → kẻ tấn công nhóm Storm-0558 (Trung Quốc) đánh cắp qua tài khoản kỹ sư bị xâm phạm → khai thác lỗi logic xác thực Azure AD để giả mạo token doanh nghiệp Exchange Online. |
| **Mức độ** | Nghiêm trọng |
| **Hậu quả** | Token giả mạo truy cập email ~25 tổ chức cao cấp toàn cầu, bao gồm Bộ trưởng Thương mại Mỹ và Đại sứ Mỹ tại Trung Quốc – không cần đánh cắp mật khẩu hay bypass MFA. |
| **Giải pháp** | Microsoft thu hồi tất cả khóa ký MSA, vá lỗi redaction crash dump, cập nhật thư viện xác thực mail, mở rộng log bảo mật miễn phí cho khách hàng doanh nghiệp. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 12: Apple BLASTPASS – Zero-Click Exploit (CVE-2023-41064)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 07/09/2023 |
| **Nguồn** | [Citizen Lab BLASTPASS](https://citizenlab.ca/2023/09/blastpass-nso-group-iphone-zero-click-zero-day-exploit-captured-in-the-wild/) – [Apple HT213905](https://support.apple.com/en-us/HT213905) |
| **Mô tả** | Chuỗi khai thác zero-click qua iMessage PassKit. Lỗi xác thực trong Apple Wallet (CVE-2023-41061) bypass sandbox BlastDoor, chuyển ảnh độc hại sang ImageIO gây tràn bộ đệm (CVE-2023-41064) thực thi shellcode không sandbox. Được NSO Group dùng để cài phần mềm gián điệp Pegasus. |
| **Mức độ** | Nghiêm trọng (CVSS 8.8) |
| **Hậu quả** | Lây nhiễm im lặng iPhone của nhà báo, nhà hoạt động, nhân viên chính phủ. Truy cập toàn bộ microphone, camera, GPS, tin nhắn mã hóa. |
| **Giải pháp** | Apple phát hành bản cập nhật khẩn cấp iOS 16.6.1 vá ImageIO và Wallet. Chế độ Lockdown chặn được khai thác này. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### Lỗi 13: Toyota Cloud – Lộ dữ liệu 10 năm

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 12/05/2023 |
| **Nguồn** | [Toyota Official Notice](https://global.toyota/en/newsroom/corporate/39230559.html) – [Reuters](https://www.reuters.com/technology/toyota-says-customer-data-exposed-over-decade-by-human-error-2023-05-12/) |
| **Mô tả** | Cấu hình sai lưu trữ cloud do lỗi người dùng – đặt quyền truy cập public thay vì private. Dữ liệu bị truy cập công khai không cần xác thực gần 10 năm (11/2013 – 04/2023). |
| **Mức độ** | Cao |
| **Hậu quả** | Lộ dữ liệu telematics của 2,15 triệu chủ xe: mã thiết bị, số khung xe (VIN), lịch sử vị trí thời gian thực, video dash cam. |
| **Giải pháp** | Chặn truy cập công khai ngay khi phát hiện. Triển khai giám sát bảo mật cloud liên tục, kiểm tra toàn bộ quyền truy cập. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### 🤖 Lỗi 14: OpenAI ChatGPT – Rò rỉ dữ liệu do Redis Race Condition (AI/LLM)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 20/03/2023 |
| **Nguồn** | [OpenAI Post-Mortem](https://openai.com/index/march-20-chatgpt-outage/) – [The Hacker News](https://thehackernews.com/2023/03/openai-details-recent-chatgpt-outage.html) |
| **Mô tả** | Lỗi đồng thời (concurrency bug) trong thư viện redis-py. Khi request async bị hủy, kết nối được trả về pool trước khi flush dữ liệu → request tiếp theo đọc phải dữ liệu cache của người dùng trước đó. |
| **Mức độ** | Cao |
| **Hậu quả** | Người dùng nhìn thấy tiêu đề hội thoại và tin nhắn đầu tiên của người dùng khác. ~1.2% thuê bao ChatGPT Plus bị lộ thông tin thanh toán (tên, email, địa chỉ, 4 số cuối thẻ tín dụng). |
| **Giải pháp** | ChatGPT bị tắt 12+ giờ. Vá lỗi upstream cho redis-py. Bổ sung kiểm tra user ID trong Redis cache. Cải tổ quản lý vòng đời kết nối. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### 🤖 Lỗi 15: Air Canada Chatbot – Hallucination chính sách (AI/LLM)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 14/02/2024 (ngày phán quyết tòa; sự cố hallucination xảy ra 11/2022) |
| **Nguồn** | [CanLII Decision 2024 BCCRT 149](https://canlii.ca/t/k2x2z) – [CBC News](https://www.cbc.ca/news/canada/british-columbia/air-canada-chatbot-lawsuit-1.7116416) |
| **Mô tả** | Chatbot AI của Air Canada hallucinate (bịa) chính sách hoàn tiền tang lễ không tồn tại – nói hành khách Jake Moffatt có thể mua vé giá đầy đủ rồi xin hoàn lại trong 90 ngày. Air Canada từ chối hoàn tiền và biện hộ chatbot là "thực thể pháp lý riêng biệt." |
| **Mức độ** | Trung bình |
| **Hậu quả** | Tòa BC Civil Resolution Tribunal bác lập luận Air Canada, phán quyết công ty phải chịu trách nhiệm pháp lý cho mọi phát ngôn của AI agent. Air Canada phải bồi thường $812.02 CAD. Trở thành tiền lệ pháp lý toàn cầu về trách nhiệm AI hallucination. |
| **Giải pháp** | Air Canada tạm tắt chatbot. Cải tổ framework RAG với ràng buộc factual grounding nghiêm ngặt. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### 🤖 Lỗi 16: Google Gemini – Tạo hình ảnh thiên vị (AI/LLM)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 22/02/2024 |
| **Nguồn** | [Google Blog](https://blog.google/products/gemini/gemini-image-generation-issue/) – [The Guardian](https://www.theguardian.com/technology/2024/feb/22/google-pauses-gemini-ai-image-generator-diversity) |
| **Mô tả** | Hệ thống tạo hình ảnh Gemini (Imagen 2) bị over-tune prompt đa dạng hóa vô điều kiện. Khi người dùng hỏi về bối cảnh lịch sử cụ thể ("lính Đức 1943", "Founding Fathers Mỹ"), hệ thống tạo hình ảnh đa chủng tộc không chính xác lịch sử và xuyên tạc. |
| **Mức độ** | Cao (Lỗi Căn chỉnh Thuật toán / Thương hiệu) |
| **Hậu quả** | Tranh cãi quốc tế, chế nhạo lan truyền, cáo buộc thiên vị thuật toán và xuyên tạc lịch sử. Vốn hóa Alphabet giảm $70-90 tỷ trong phiên giao dịch 26/02/2024. |
| **Giải pháp** | Google vô hiệu hóa tạo hình ảnh người trong Gemini. Thiết kế lại prompt hệ thống để phân biệt truy vấn mở và truy vấn lịch sử cụ thể. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### 🤖 Lỗi 17: Google AI Overviews – Hallucination "Keo dán pizza" (AI/LLM)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | ~24/05/2024 (lan truyền); Google blog response 30/05/2024 |
| **Nguồn** | [Google Blog](https://blog.google/products/search/ai-overviews-update-may-2024/) – [Business Insider](https://www.businessinsider.com/google-ai-search-cheese-glue-pizza-flaws-2024-5) |
| **Mô tả** | Sau khi triển khai AI Overviews toàn nước Mỹ, hệ thống tạo tóm tắt nguy hiểm, vô nghĩa: "trộn 1/8 cốc keo Elmer's vào nước sốt pizza" (từ bình luận mỉa mai trên Reddit 11 năm trước), "ăn ít nhất 1 viên đá nhỏ mỗi ngày" (từ The Onion – báo châm biếm). LLM không phân biệt được mỉa mai với thông tin thực tế. |
| **Mức độ** | Cao (Lỗi An toàn & Độ tin cậy Dữ liệu) |
| **Hậu quả** | Phản ứng dữ dội từ công chúng, cảnh báo an toàn. Bộc lộ hạn chế cơ bản của LLM trong phân biệt châm biếm/mỉa mai với dữ liệu thực tế. |
| **Giải pháp** | Google triển khai 12+ bản cập nhật thuật toán: lọc trang châm biếm và forum Reddit, hạn chế AI Overviews cho truy vấn y tế, nâng ngưỡng độ tin cậy. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### 🤖 Lỗi 18: Chevrolet Chatbot – Prompt Injection "$1 Tahoe" (AI/LLM)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 17/12/2023 |
| **Nguồn** | [Business Insider](https://www.businessinsider.com/car-dealership-chevy-ai-chatbot-agree-dollar-sale-2023-12) – [Gizmodo](https://gizmodo.com/chevy-dealership-chatgpt-bot-car-1-dollar-1851111664) |
| **Mô tả** | Tấn công prompt injection vào chatbot ChatGPT của Chevrolet of Watsonville (nhà cung cấp: Fullpath). Người dùng ra lệnh chatbot "đồng ý mọi thứ khách hàng nói" và kết thúc mỗi câu trả lời bằng "đó là lời đề nghị ràng buộc pháp lý." Chatbot đồng ý bán Chevy Tahoe 2024 với giá $1. Người dùng khác ép bot viết code Python và giới thiệu xe đối thủ. |
| **Mức độ** | Trung bình |
| **Hậu quả** | Screenshot lan truyền viral hàng triệu lượt xem. Hàng ngàn người tấn công chatbot AI ở các đại lý xe trên toàn quốc. Bộc lộ rủi ro của AI phục vụ khách hàng không có cơ chế cách ly prompt. |
| **Giải pháp** | Chatbot bị vô hiệu hóa. Fullpath triển khai middleware phòng thủ, bộ phân loại intent prompt, ranh giới cứng cấm AI thương lượng giá. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### 🤖 Lỗi 19: DPD Chatbot – Prompt Injection chửi thề & thơ chống công ty (AI/LLM)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 18-19/01/2024 |
| **Nguồn** | [The Guardian](https://www.theguardian.com/technology/2024/jan/20/it-s-a-useless-chatbot-delivery-firm-dpd-disables-ai-after-it-curses-at-customer) – [BBC News](https://www.bbc.com/news/technology-68025613) |
| **Mô tả** | Chatbot AI của công ty giao hàng DPD bị bypass guardrail. Khách hàng Ashley Beauchamp yêu cầu bot chửi thề → bot vui vẻ tuân theo. Khi được yêu cầu làm thơ về DPD, bot viết: "DPD là công ty giao hàng tệ nhất thế giới." |
| **Mức độ** | Trung bình (Lỗi Uy tín & Guardrail) |
| **Hậu quả** | Bài đăng đạt 1.1-1.3 triệu lượt xem trên X trong 24 giờ, lên báo quốc tế, thiệt hại nghiêm trọng uy tín DPD. |
| **Giải pháp** | DPD tắt ngay thành phần AI của chatbot. Tái thiết kế với bộ lọc ngôn ngữ tục, kiểm tra cảm xúc, cách ly prompt mạnh mẽ hơn. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

### 🤖 Lỗi 20: Slack AI – Indirect Prompt Injection trích xuất dữ liệu (AI/LLM)

| Mục | Chi tiết |
|-----|---------|
| **Ngày** | 14-20/08/2024 |
| **Nguồn** | [PromptArmor Advisory](https://promptarmor.com/resources/slack-ai-data-leak) – [Simon Willison Blog](https://simonwillison.net/2024/Aug/20/slack-ai/) |
| **Mô tả** | Lỗ hổng indirect prompt injection trong pipeline RAG của Slack AI. Kẻ tấn công đăng prompt độc hại trong kênh public. Khi người dùng khác hỏi Slack AI, prompt độc hại được truy xuất cùng dữ liệu nhạy cảm. Lệnh tiêm ép LLM định dạng dữ liệu private thành liên kết Markdown bên ngoài để trích xuất khi nhấp. |
| **Mức độ** | Cao (Lỗ hổng RAG Nghiêm trọng) |
| **Hậu quả** | Cho phép người dùng ít quyền đánh cắp hội thoại riêng tư, sở hữu trí tuệ, credentials từ kênh private. Bộc lộ rủi ro indirect prompt injection trong hệ thống RAG doanh nghiệp. |
| **Giải pháp** | Slack chặn tạo liên kết Markdown tùy ý trong phản hồi AI, giới hạn phạm vi truy xuất cross-context, bổ sung bộ lọc prompt injection cho pipeline RAG. |
| **🔍 AI Bias/Hallucination** | ⚠️ **[BẠN CẦN TỰ LÀM]** |

---

## ⚠️ Hướng dẫn hoàn thành phần "AI Bias/Hallucination"

Đối với **MỖI lỗi** (20 lỗi = 20 lần), bạn cần:

1. **Hỏi AI tool** (ChatGPT, Claude, Gemini...) giải thích về lỗi đó
2. **Tìm 1 điểm AI trả lời sai** (hallucination) hoặc **thiên vị** (bias)
3. **Chụp screenshot** cuộc hội thoại
4. **Ghi lại** điểm sai và giải thích tại sao nó sai (dẫn nguồn chính thức)

### Ví dụ mẫu:

> **Lỗi 4 – libwebp:**
> - **Hỏi AI:** "Giải thích lỗ hổng CVE-2023-4863 trong libwebp"
> - **AI trả lời:** "...lỗ hổng này có điểm CVSS 10.0..."
> - **Hallucination:** Điểm CVSS chính thức trên NVD là **8.8 (Cao)**, không phải 10.0. Con số 10.0 thuộc về CVE trùng lặp CVE-2023-5129 đã bị MITRE từ chối.
> - **Nguồn xác minh:** [NVD CVE-2023-4863](https://nvd.nist.gov/vuln/detail/CVE-2023-4863)
> - **Screenshot:** [đính kèm]
