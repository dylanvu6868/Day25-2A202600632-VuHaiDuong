# Workshop 4: Vẽ Bản Đồ Phụ Thuộc (Dependency Map) & Đường Găng (Critical Path)

**Dự án:** MentorMind  
**Giai đoạn:** NOW (Triển khai MVP thử nghiệm trong 30 ngày)  
**Người thực hiện:** Vũ Hải Dương (MSSV: 2A20260632)

---

## 1. Bản Đồ Phụ Thuộc Ngoại Vi (3 External Dependencies)

Dưới đây là 3 yếu tố phụ thuộc bên ngoài có khả năng "giết chết" dự án MentorMind trong vòng 30 ngày tới nếu xảy ra sự cố, kèm theo kế hoạch dự phòng cụ thể:

### Phụ thuộc 1: Sự phê duyệt quyền truy cập dữ liệu học tịch của nhà trường (University SIS Data Access)
*   **Worst-case scenario:** Ban giám hiệu nhà trường từ chối hoặc trì hoãn cấp quyền truy cập dữ liệu điểm số, chuyên cần và học phí của sinh viên vì lý do bảo mật thông tin (GDPR/Luật An toàn thông tin), khiến dự án không có dữ liệu để chạy thử nghiệm và bị đình trệ vô thời hạn.
*   **Plan B:** Sử dụng bộ dữ liệu học tập đã ẩn danh hóa (anonymized) có sẵn của học kỳ cũ để làm demo, đồng thời hướng dẫn cố vấn tự tay import file Excel tự nhập (chỉ chứa ID sinh viên ẩn danh) thay vì kết nối hệ thống trực tiếp.
*   **Cost của Plan B:** 0 VNĐ và 5 ngày làm việc của 1 Data Engineer để làm sạch dữ liệu cũ và chuẩn hóa mẫu Excel.

### Phụ thuộc 2: Sự không đồng nhất về định dạng file Excel từ các khoa (Data Format Inconsistency)
*   **Worst-case scenario:** File Excel/CSV chuyên cần và điểm số xuất ra từ phần mềm quản lý của trường có cấu trúc cột lộn xộn và không thống nhất giữa các khoa, khiến bộ tải dữ liệu (CSV Ingest Tool) liên tục bị lỗi và không thể phân tích được dữ liệu.
*   **Plan B:** Ban hành một mẫu file Excel tiêu chuẩn (Excel template) duy nhất và yêu cầu các khoa tự chuẩn hóa dữ liệu vào form này trước khi tải lên, đồng thời cập nhật cơ chế ánh xạ cột (auto-mapping) tự động ở frontend để tự nhận diện tiêu đề cột thông dụng.
*   **Cost của Plan B:** 0 VNĐ và 3 ngày lập trình frontend.

### Phụ thuộc 3: Mức độ cam kết tham gia thử nghiệm của Cố vấn học tập (User Engagement & Participation)
*   **Worst-case scenario:** Cố vấn học tập phản đối sử dụng công cụ mới vì họ cho rằng nó làm tăng thêm khối lượng công việc hành chính mà không có lợi ích trực tiếp, dẫn đến tỷ lệ sử dụng thực tế bằng 0 và không có dữ liệu phản hồi để cải tiến.
*   **Plan B:** Tổ chức một buổi tập huấn trực tiếp ngắn 15 phút, đồng thời phối hợp với Phòng Đào tạo đưa việc sử dụng công cụ thử nghiệm vào tiêu chí cộng điểm thi đua tháng, tặng thẻ cào cà phê 50.000 VNĐ cho cố vấn hoàn thành 5 lượt can thiệp đầu tiên.
*   **Cost của Plan B:** 2.000.000 VNĐ tiền quà tặng/cà phê và 4 ngày chuẩn bị tài liệu + tổ chức workshop trực tiếp.

---

## 2. Đường Găng (Critical Path Analysis) cho Giai Đoạn NOW

Để khởi chạy thử nghiệm MVP trong vòng 30 ngày tới, đội ngũ phát triển cần thực hiện 7 nhiệm vụ cốt lõi sau.

### Danh sách nhiệm vụ (Tasks) & Thời lượng ước tính:
1.  **T1:** Khảo sát quy trình xuất dữ liệu thô và cấu trúc file Excel/CSV từ phòng đào tạo (Thời gian: 2 ngày).
2.  **T2:** Thiết kế mẫu file Excel chuẩn hóa (Excel Template) và giao diện công cụ tải dữ liệu lên (Thời gian: 3 ngày).
3.  **T3:** Phát triển bộ lọc, parse dữ liệu và kiểm tra lỗi định dạng file Excel đầu vào (Thời gian: 4 ngày).
4.  **T4:** Thiết kế giao diện Dashboard danh sách sinh viên rủi ro (UI/UX) (Thời gian: 3 ngày).
5.  **T5:** Lập trình frontend và kết nối API hiển thị danh sách sinh viên rủi ro trên Dashboard (Thời gian: 5 ngày).
6.  **T6:** Kiểm thử tích hợp hệ thống End-to-End với dữ liệu ẩn danh mẫu (Thời gian: 2 ngày).
7.  **T7:** Tổ chức tập huấn cố vấn học tập sử dụng hệ thống thô để bắt đầu theo dõi sinh viên (Thời gian: 3 ngày).

### Các mối quan hệ phụ thuộc lẫn nhau (Task Blocks):
*   **T1 blocks T2:** Phải khảo sát xong cấu trúc file thực tế của trường mới thiết kế được mẫu Excel chuẩn hóa phù hợp.
*   **T2 blocks T3:** Phải thống nhất mẫu Excel và giao diện tải lên mới lập trình được bộ parse.
*   **T3 blocks T6:** Bộ tải và parse dữ liệu thô hoạt động ổn định là điều kiện bắt buộc để nạp dữ liệu chạy thử End-to-End.
*   **T4 blocks T5:** Bản vẽ UI/UX Dashboard phải được chốt trước khi tiến hành lập trình frontend và tích hợp API.
*   **T5 blocks T6:** Dashboard hoạt động là điều kiện bắt buộc để kiểm thử giao diện đầu ra trong quy trình End-to-End.
*   **T6 blocks T7:** Hệ thống phải hoàn thành kiểm thử tích hợp không lỗi mới tiến hành tập huấn cho người dùng thật.

### Biểu đồ Đường Găng (Critical Path Map):

```mermaid
flowchart TD
    T1["T1: Khảo sát xuất dữ liệu (2d)"] -->|blocks| T2["T2: Thiết kế mẫu Excel (3d)"]
    T2 -->|blocks| T3["T3: Lập trình bộ parse CSV (4d)"]
    T3 -->|blocks| T6["T6: Kiểm thử End-to-End (2d)"]
    
    T4["T4: Thiết kế UI/UX Dashboard (3d)"] -->|blocks| T5["T5: Lập trình Dashboard & API (5d)"]
    T5 -->|blocks| T6
    
    T6 -->|blocks| T7["T7: Tập huấn cố vấn (3d)"]
    
    style T1 fill:#f9f,stroke:#333,stroke-width:2px
    style T2 fill:#f9f,stroke:#333,stroke-width:2px
    style T3 fill:#f9f,stroke:#333,stroke-width:2px
    style T6 fill:#f9f,stroke:#333,stroke-width:2px
    style T7 fill:#f9f,stroke:#333,stroke-width:2px
    
    linkStyle 0,1,2,5,6 stroke:#ff3366,stroke-width:3px;
```

### Kết luận Đường Găng:
Có hai chuỗi song song chạy vào kiểm thử **T6**:
*   *Chuỗi Dữ liệu:* **T1 → T2 → T3 → T6 → T7** = $2 + 3 + 4 + 2 + 3 = \mathbf{14\text{ ngày}}$ (Đường Găng).
*   *Chuỗi Giao diện:* **T4 → T5 → T6 → T7** = $3 + 5 + 2 + 3 = \mathbf{13\text{ ngày}}$.

**Đường Găng (Critical Path)** của dự án chính là **Chuỗi Dữ liệu (T1 → T2 → T3 → T6 → T7)** với tổng thời lượng là **14 ngày**. Bất kỳ sự chậm trễ nào ở T1, T2 hoặc T3 sẽ trực tiếp làm trễ ngày ra mắt tập huấn sản phẩm MVP cho nhà trường. Do đó, Project Manager cần ưu tiên tối đa nhân sự để thông suốt luồng dữ liệu thô này trước.
