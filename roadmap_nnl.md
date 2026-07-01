# Workshop 2: Vẽ La Bàn Cho Startup - Now/Next/Later Roadmap

**Dự án:** MentorMind  
**Tên tài liệu:** Roadmap sản phẩm định hướng giải quyết vấn đề (Problem-Focused Roadmap)  
**Quy tắc áp dụng:** KHÔNG ghi ngày tháng. Tập trung mô tả **vấn đề cần giải quyết**, không ghi tên tính năng thuần túy.

---

## 1. Bản Đồ Tổng Quan Now/Next/Later Roadmap (1 Trang Gửi VC)

Tài liệu này được thiết kế để trả lời câu hỏi cốt lõi từ các quỹ đầu tư mạo hiểm (VC): *"Lộ trình phát triển sản phẩm của startup thế nào để giải quyết nỗi đau thị trường một cách bền vững?"*

```
+-----------------------------------------------------------------------------------------------------------------------+
|                                           MENTORMIND - PRODUCT ROADMAP                                                |
+-----------------------------------------------------------------------------------------------------------------------+
|                                                                                                                       |
|  [ NOW ] (Đang tập trung giải quyết)                                                                                   |
|  * Vấn đề 1: Cố vấn học tập không biết phải bắt đầu hỗ trợ từ sinh viên nào do dữ liệu rời rạc, dẫn đến bỏ lỡ         |
|             "thời điểm vàng" để can thiệp.                                                                            |
|             --> Hướng xử lý: Dashboard hiển thị danh sách phân loại mức độ rủi ro (F2).                               |
|  * Vấn đề 2: Hệ thống thiếu dữ liệu thô đầu vào về điểm số, chuyên cần và học phí của sinh viên để chạy các           |
|             phân tích cơ bản.                                                                                         |
|             --> Hướng xử lý: Công cụ nạp dữ liệu CSV/SIS thô nhanh gọn (F5).                                          |
|                                                                                                                       |
+-----------------------------------------------------------------------------------------------------------------------+
|                                                                                                                       |
|  [ NEXT ] (Sắp tới sẽ giải quyết)                                                                                     |
|  * Vấn đề 3: Cố vấn học tập không tin tưởng vào cảnh báo của AI hoặc không hiểu vì sao hệ thống xếp sinh viên đó      |
|             vào nhóm rủi ro để đưa ra hành động phù hợp.                                                              |
|             --> Hướng xử lý: Giao diện hiển thị Top 3 nguyên nhân cốt lõi do AI phân tích (F3).                       |
|  * Vấn đề 4: Tỷ lệ cảnh báo sai lệch hoặc dự báo rủi ro thiếu chính xác do chưa có mô hình máy học tối ưu hóa          |
|             theo dữ liệu đặc thù của nhà trường.                                                                      |
|             --> Hướng xử lý: Huấn luyện và tích hợp mô hình dự đoán rủi ro chuyên sâu (F1).                           |
|                                                                                                                       |
+-----------------------------------------------------------------------------------------------------------------------+
|                                                                                                                       |
|  [ LATER ] (Tầm nhìn dài hạn / Ý tưởng lớn)                                                                           |
|  * Vấn đề 5: Quy trình can thiệp của cố vấn học tập bị ngắt quãng, thiếu công cụ lưu trữ lịch sử tương tác và không   |
|             đo lường được hiệu quả của cuộc can thiệp.                                                                |
|             --> Hướng xử lý: Hệ thống quản lý lịch trình can thiệp và gợi ý mẫu liên hệ (F4).                         |
|  * Vấn đề 6: Việc nạp dữ liệu học tập thủ công định kỳ gây tốn công sức của phòng đào tạo và trễ hạn cập nhật         |
|             thông tin rủi ro của sinh viên.                                                                           |
|             --> Hướng xử lý: Tích hợp API thời gian thực với hệ thống thông tin sinh viên của trường (SIS Integration).|
|                                                                                                                       |
+-----------------------------------------------------------------------------------------------------------------------+
```

---

## 2. Chi Tiết Lộ Trình Giải Quyết Vấn Đề

### Giai Đoạn 1: NOW (Giải quyết ngay lập tức)
*Số lượng vấn đề: 2 vấn đề lớn.*

*   **Vấn đề 1: Phân bổ nguồn lực can thiệp không hiệu quả**
    *   *Chi tiết:* Cố vấn học tập bị quá tải do phải quản lý hàng trăm sinh viên nhưng dữ liệu học tập bị phân tán ở nhiều nơi. Họ không biết sinh viên nào đang thực sự rơi vào trạng thái nguy cấp cần liên hệ trước.
    *   *Cách giải quyết:* Thiết lập màn hình Dashboard trực quan hóa danh sách học sinh có rủi ro cao nhất được làm nổi bật trước. Cho phép lọc nhanh theo lớp, ngành và điểm số để cố vấn có thể lên kế hoạch làm việc trong ngày chỉ sau 5 phút mở máy.
    *   *Áp dụng từ Workshop 1:* Tính năng **F2 (At-risk Student Dashboard)** - Quick Win có công sức thấp nhưng giải quyết ngay lập tức nỗi đau ưu tiên công việc của người dùng.
*   **Vấn đề 2: Tắc nghẽn dòng dữ liệu đầu vào**
    *   *Chi tiết:* Hệ thống không có cơ sở dữ liệu để phân tích và đánh giá rủi ro. Trường học thường sử dụng nhiều phần mềm quản lý khác nhau và việc tích hợp hệ thống ngay lập tức là quá tốn kém và bất khả thi.
    *   *Cách giải quyết:* Cung cấp công cụ tải tệp tin Excel/CSV chuẩn hóa cho cán bộ phòng đào tạo, cho phép họ nạp dữ liệu chuyên cần, điểm số, học phí vào hệ thống chỉ bằng thao tác kéo thả trong vài giây.
    *   *Áp dụng từ Workshop 1:* Tính năng **F5 (CSV/SIS Data Ingestion Tool)** - Quick Win có điểm RICE cao nhất (10.000), là điều kiện tiên quyết để vận hành MVP.

---

### Giai Đoạn 2: NEXT (Sẽ giải quyết ở giai đoạn tiếp theo)
*Số lượng vấn đề: 2 vấn đề lớn.*

*   **Vấn đề 3: Sự hoài nghi của người dùng đối với kết quả từ AI (Hộp đen AI)**
    *   *Chi tiết:* Khi AI đưa ra điểm số rủi ro (ví dụ Nguyễn Văn A rủi ro 82%), cố vấn học tập thường không tin tưởng vì họ không biết thuật toán dựa vào đâu. Họ có xu hướng bỏ qua cảnh báo nếu không được giải thích rõ ràng.
    *   *Cách giải quyết:* Thiết kế màn hình chi tiết bóc tách rõ ràng **Top 3 lý do hàng đầu** khiến AI cảnh báo rủi ro cao (như: GPA giảm đột ngột 30%, nghỉ học liên tục 4 buổi trong tháng, chưa đóng học phí kỳ mới). Khi hiểu rõ lý do, cố vấn sẽ tin tưởng hơn và biết chính xác chủ đề cần thảo luận khi gặp sinh viên.
    *   *Áp dụng từ Workshop 1:* Tính năng **F3 (AI Risk Explanations Page)** - Giá trị cốt lõi giải quyết giả thuyết lớn nhất của sản phẩm.
*   **Vấn đề 4: Tỷ lệ cảnh báo ảo (False Positive) cao gây loãng thông tin**
    *   *Chi tiết:* Nếu chỉ sử dụng các quy tắc logic tĩnh (if-else thông thường) để cảnh báo, cố vấn học tập sẽ nhận được quá nhiều cảnh báo không chính xác, dẫn đến hiện tượng lờn cảnh báo (alert fatigue).
    *   *Cách giải quyết:* Triển khai và tinh chỉnh mô hình máy học (ML) dự đoán rủi ro bỏ học, huấn luyện trên tập dữ liệu lịch sử của chính nhà trường để tối ưu hóa độ chính xác và cá nhân hóa ngưỡng cảnh báo.
    *   *Áp dụng từ Workshop 1:* Tính năng **F1 (AI Risk Prediction Engine)** - Strategic Bet tạo hàng rào công nghệ vững chắc (moat).

---

### Giai Đoạn 3: LATER (Tầm nhìn dài hạn)
*Số lượng vấn đề: 2 vấn đề vĩ mô.*

*   **Vấn đề 5: Hiệu quả can thiệp bị đứt gãy và không có tính kế thừa**
    *   *Chi tiết:* Sau khi cố vấn liên hệ với sinh viên, thông tin can thiệp (gọi điện, gửi mail, hẹn gặp) thường chỉ được ghi chú trên sổ tay hoặc Excel cá nhân. Phòng đào tạo không thể theo dõi xem sinh viên đó đã được hỗ trợ chưa, kết quả ra sao, khiến các nỗ lực can thiệp bị rời rạc.
    *   *Cách giải quyết:* Xây dựng mô-đun quản lý lịch trình can thiệp, lưu lại nhật ký trao đổi giữa cố vấn và sinh viên ngay trên hệ thống. Đồng thời gợi ý tự động các kịch bản mail/tin nhắn phù hợp nhất cho từng trường hợp rủi ro.
    *   *Áp dụng từ Workshop 1:* Tính năng **F4 (Actionable Intervention & Tracking)** - Bị loại khỏi MVP do tốn sức (Effort 2.5 PM) nhưng sẽ làm ở giai đoạn phát triển quy mô (Scale).
*   **Vấn đề 6: Trễ hạn thông tin và rủi ro bảo mật do vận hành thủ công**
    *   *Chi tiết:* Việc tải file CSV thủ công từ phòng đào tạo định kỳ có thể bị trễ, khiến sinh viên đã nghỉ học 2 tuần mới được phát hiện. Đồng thời, việc tải file thủ công có nguy cơ rò rỉ dữ liệu điểm số.
    *   *Cách giải quyết:* Phát triển cổng kết nối tích hợp API thời gian thực trực tiếp với cơ sở dữ liệu SIS (Student Information System) của nhà trường, tự động đồng bộ hóa dữ liệu mỗi đêm và gửi thông báo khẩn cấp cho cố vấn qua Email/Zalo.

---

## 3. Lý Do Gửi Bản Roadmap Này Cho Quỹ Đầu Tư (VC) thay vì Bản Kế Hoạch Theo Ngày Tháng

Khi VC hỏi *"Roadmap thế nào?"*, việc gửi một bản Roadmap Now/Next/Later tập trung vào vấn đề (Problem-Focused) thay vì một bản Gantt Chart chi tiết ngày tháng sẽ thuyết phục họ hơn vì:

1.  **Thể hiện tư duy hướng khách hàng (Customer-Centric):** Chứng minh startup tập trung vào việc **giải quyết nỗi đau thực tế của cố vấn học tập và nhà trường** thay vì chỉ cắm đầu xây dựng các tính năng công nghệ hoa mỹ nhưng không ai dùng.
2.  **Khả năng thích ứng cao (Agility):** Trong môi trường startup, các giả định thay đổi liên tục. Nếu cam kết ngày tháng cụ thể (ví dụ: tháng 9 xong mô hình AI), startup sẽ dễ bị trễ hẹn do rào cản kỹ thuật hoặc thay đổi yêu cầu. Bản Roadmap này giúp đội ngũ linh hoạt thay đổi giải pháp kỹ thuật miễn là giải quyết được vấn đề đặt ra.
3.  **Tập trung vào giá trị (Value-Driven):** Giúp VC nhìn thấy rõ ràng thứ tự ưu tiên hợp lý: Giải quyết việc sắp xếp công việc cho cố vấn trước (Now), xây dựng lòng tin vào AI và độ chính xác sau (Next), rồi mới tối ưu quy trình tự động hóa (Later). Điều này chứng tỏ người sáng lập có năng lực quản trị nguồn lực tài chính cực kỳ tốt ở giai đoạn sơ khởi.
