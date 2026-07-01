# Workshop 1: Chấm Điểm RICE Cho Dự Án MentorMind

**Dự án:** MentorMind  
**Mô tả:** Hệ thống AI hỗ trợ cố vấn học tập/phòng đào tạo phát hiện sớm sinh viên có nguy cơ bỏ học, giải thích nguyên nhân rủi ro và gợi ý hành động can thiệp phù hợp.  
**Người thực hiện:** Vũ Hải Dương (MSSV: 2A20260632)

---

## 1. Danh Sách 5 Tính Năng Cốt Lõi Để Đánh Giá

Dựa trên tài liệu PRD MentorMind (Day 17), chúng ta lựa chọn 5 tính năng cốt lõi sau để tiến hành chấm điểm RICE:

1. **F1. Mô hình dự đoán rủi ro sinh viên (AI Risk Prediction Engine)**: Thuật toán máy học phân tích dữ liệu học tập (GPA, số môn trượt, số buổi vắng) và trạng thái đóng học phí để tính toán điểm số rủi ro bỏ học (Risk Score).
2. **F2. Dashboard danh sách sinh viên rủi ro (At-risk Student Dashboard)**: Giao diện hiển thị danh sách sinh viên kèm bộ lọc theo ngành, học kỳ và thanh tìm kiếm, phân nhóm theo mức độ rủi ro (Cao/Trung bình/Thấp) giúp cố vấn ưu tiên liên hệ.
3. **F3. Màn hình chi tiết sinh viên & Giải thích AI (AI Risk Explanations Page)**: Trang chi tiết sinh viên hiển thị 3 nguyên nhân cốt lõi dẫn đến cảnh báo rủi ro (ví dụ: GPA giảm mạnh, vắng học đột xuất, nợ học phí) nhằm tạo sự tin tưởng cho cố vấn học tập.
4. **F4. Bộ gợi ý hành động & Theo dõi lịch trình can thiệp (Actionable Intervention & Tracking)**: Cung cấp các mẫu thư điện tử, kịch bản cuộc gọi có sẵn và cho phép ghi chép, lưu trạng thái can thiệp (Đã liên hệ, Chờ phản hồi, Đã giải quyết).
5. **F5. Công cụ tải dữ liệu CSV/SIS (CSV/SIS Data Ingestion Tool)**: Tính năng cho phép cán bộ phòng đào tạo upload dữ liệu học tập và học phí của sinh viên dạng CSV vào hệ thống để chạy mô hình AI.

---

## 2. Tiêu Chỉ Chấm Điểm RICE (Quy Ước)

*   **Reach (R - Độ tiếp cận trong 1 quý):** Được tính bằng **số lượng sinh viên** được tác động hoặc theo dõi trực tiếp bởi tính năng đó trong một học kỳ/quý (Giả định trường đại học quy mô vừa có **10.000 sinh viên** hoạt động và **100 cố vấn học tập**).
*   **Impact (I - Mức độ tác động):** Đánh giá mức độ đóng góp của tính năng vào mục tiêu cuối cùng (giúp cố vấn can thiệp thành công, giảm tỷ lệ sinh viên bỏ học).
    *   `3`: Tác động cực kỳ lớn (Massive)
    *   `2`: Tác động cao (High)
    *   `1`: Tác động trung bình (Medium)
    *   `0.5`: Tác động thấp (Low)
    *   `0.25`: Tác động tối thiểu (Minimal)
*   **Confidence (C - Mức độ tự tin của đội ngũ):**
    *   `100%`: Cực kỳ tự tin (Có dữ liệu hỗ trợ, công nghệ đơn giản, phản hồi khách hàng rõ ràng).
    *   `80%`: Tự tin trung bình (Có giả định hợp lý, cần kiểm chứng thêm qua prototype).
    *   `50%`: Tự tin thấp (Chưa kiểm chứng, có rủi ro người dùng không sử dụng).
*   **Effort (E - Công sức triển khai):** Tính bằng **Person-Months (PM)** - số tháng làm việc của 1 nhân sự phát triển.

---

## 3. Bảng Chấm Điểm RICE

| Mã tính năng | Tên tính năng | Reach (R) | Impact (I) | Confidence (C) | Effort (E) | RICE Score |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **F1** | AI Risk Prediction Engine | 10.000 | 2.0 | 80% | 4.0 PM | **4.000** |
| **F2** | At-risk Student Dashboard | 2.000 | 2.0 | 100% | 1.5 PM | **2.667** |
| **F3** | AI Risk Explanations Page | 800 | 3.0 | 80% | 2.0 PM | **960** |
| **F4** | Actionable Intervention & Tracking | 400 | 2.0 | 50% | 2.5 PM | **160** |
| **F5** | CSV/SIS Data Ingestion Tool | 10.000 | 1.0 | 100% | 1.0 PM | **10.000** |

### Công thức tính toán chi tiết:
$$\text{RICE Score} = \frac{\text{Reach} \times \text{Impact} \times \text{Confidence}}{\text{Effort}}$$

*   **F1:** $(10.000 \times 2 \times 0.8) / 4.0 = 4.000$
*   **F2:** $(2.000 \times 2 \times 1.0) / 1.5 = 2.667$
*   **F3:** $(800 \times 3 \times 0.8) / 2.0 = 960$
*   **F4:** $(400 \times 2 \times 0.5) / 2.5 = 160$
*   **F5:** $(10.000 \times 1 \times 1.0) / 1.0 = 10.000$

---

## 4. Phân Tích Ma Trận 2x2 Value-Effort

Để trực quan hóa giá trị mang lại so với công sức bỏ ra, ta định nghĩa giá trị (**Value**) bằng tích của $(\text{Reach} \times \text{Impact} \times \text{Confidence})$.

*   **Trục Hoành (Effort - PM):** Thấp ($\le 2.0$ PM) | Cao ($> 2.0$ PM)
*   **Trục Tung (Value):** Thấp ($< 1.000$) | Cao ($\ge 4.000$)

```
                       VALUE (Reach x Impact x Confidence)
       Cao  ^
            |
            |     [F5] CSV Uploader (Value: 10K, Effort: 1.0)
            |     [F2] Dashboard (Value: 4K, Effort: 1.5)         [F1] Prediction Engine (Value: 16K, Effort: 4.0)
            |     ----------------------------------------        ------------------------------------------------
            |                   QUICK WINS                                         STRATEGIC BETS
            |
            |
            |                   FILL-INS / MAJOR                                    NON-STARTERS
            |     ----------------------------------------        ------------------------------------------------
            |     [F3] AI Explanations (Value: 1.9K, Effort: 2.0) [F4] Intervention Tracking (Value: 0.4K, Effort: 2.5)
            |
       Thấp +------------------------------------------------------------------------------------------->
            0                                   2.0 PM                                                 EFFORT
                                                 Thấp  |  Cao
```

Dựa trên ma trận, ta xác định các nhóm tính năng ưu tiên như sau:

1.  **Quick Win (Làm trước):**
    *   **F5. CSV/SIS Data Ingestion Tool** (Score: 10.000, Effort: 1.0 PM): Rất dễ làm nhưng giá trị cực kỳ cao vì nếu không có dữ liệu đầu vào, toàn bộ hệ thống không thể hoạt động.
    *   **F2. At-risk Student Dashboard** (Score: 2.667, Effort: 1.5 PM): Cố vấn học tập có thể bắt đầu sử dụng ngay để lọc và ưu tiên sinh viên.
2.  **Strategic Bet (Moat dài hạn):**
    *   **F1. AI Risk Prediction Engine** (Score: 4.000, Effort: 4.0 PM): Yêu cầu nhiều thời gian huấn luyện mô hình máy học, là cốt lõi công nghệ giúp dự án có lợi thế cạnh tranh lâu dài (moat).
3.  **Non-starter (Bỏ thẳng ở giai đoạn MVP):**
    *   **F4. Actionable Intervention & Tracking** (Score: 160, Effort: 2.5 PM): Tốn nhiều công sức lập trình phần ghi nhận trạng thái và tạo kịch bản, trong khi mức độ tự tin rất thấp (cố vấn học tập hoàn toàn có thể dùng Excel hoặc Email trường để thay thế). Bỏ tính năng này giúp tối ưu hóa nguồn lực cho MVP.
4.  **Core Differentiator (Tính năng cốt lõi tạo khác biệt - Cần ưu tiên ngay sau Quick Wins):**
    *   **F3. AI Risk Explanations Page** (Score: 960, Effort: 2.0 PM): Đây là tính năng giải quyết trực tiếp giả thuyết cốt lõi (Hypothesis) của MentorMind: cố vấn cần hiểu 3 lý do chính dẫn đến rủi ro thì mới tin tưởng AI và hành động.

---

## 5. Kết Luận & Định Hướng Block 2
Kết quả của Workshop 1 đã cung cấp dữ liệu đầu vào sắc bén cho việc xây dựng Roadmap ở Workshop 2. Chúng ta sẽ bỏ hoàn toàn **F4** khỏi kế hoạch ngắn hạn, triển khai **F5** và **F2** ngay lập tức để người dùng có công cụ sử dụng thô sơ, song song đó phát triển **F1** và tích hợp **F3** để hiện thực hóa giá trị cốt lõi của giải pháp AI.
