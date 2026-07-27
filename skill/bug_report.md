# Hướng dẫn Kỹ năng: Báo cáo Lỗi & Vấn đề Khả dụng (Bug & Usability Findings Log) - HW03 EMS

Tài liệu này định nghĩa kỹ năng và quy trình chuẩn để ghi nhận, quản lý và báo cáo các lỗi chức năng (Bugs) và các vấn đề về khả năng sử dụng (Usability Issues) đối với hệ thống **EMS (Event Management System)** theo yêu cầu của bài tập **HW03 – GUI & Usability Testing on EMS**.

---

## 1. Mục tiêu & Quy định Báo cáo (HW03 Section 7)
Mọi phát hiện lỗi (Defects) và cải tiến khả năng sử dụng (Usability Improvements) phát hiện được từ các Task 1–3 phải được báo cáo theo **kênh đôi (Double Reporting)**:
1. **Google Form:** Gửi từng phát hiện lên kênh tiếp nhận qua Google Form (https://forms.gle/CJQFQCAXcsDbXDMM9) sử dụng email sinh viên (`MSSV@....edu.vn`).
2. **Aggregated Findings Log:** Tổng hợp toàn bộ các item đã gửi lên form thành một file duy nhất (`Bug & Usability Findings Log` / `bug_report.md`) đính kèm trong bài nộp. Nội dung trong log và Google Form phải khớp chính xác 100%.

---

## 2. Cấu trúc Cột trong Bảng Bug & Usability Findings Log

Bảng nhật ký phải bảo đảm tối thiểu 9 cột tiêu chuẩn theo yêu cầu của đề bài HW03 (§7):

| STT | Tên Cột | Mô tả & Quy chuẩn |
| :---: | :--- | :--- |
| 1 | **ID** | Mã định danh duy nhất cho từng phát hiện (`BUG-01`, `BUG-02` cho Lỗi; `USA-01`, `USA-02` cho Usability). |
| 2 | **Scenario/Screen** | Kịch bản và Màn hình kiểm thử (Ví dụ: `Scenario A (A1) - Events List`, `Scenario B (B2) - Event Detail`). |
| 3 | **Type** | Phân loại phát hiện: **`Bug`** (Lỗi chức năng/giao diện) hoặc **`Usability`** (Vấn đề trải nghiệm người dùng/trực quan). |
| 4 | **Description** | Mô tả chi tiết vấn đề:<br>- *Đối với Bug:* Điều kiện tiên quyết (Pre-conditions), Kết quả thực tế (Actual Result) vs Kết quả mong đợi (Expected Result).<br>- *Đối với Usability:* Điểm gây khó khăn cho người dùng (Friction point), ngữ cảnh xảy ra và tác động. |
| 5 | **Steps/Heuristic** | Chi tiết kỹ thuật tái hiện hoặc cơ sở đánh giá:<br>- *Đối với Bug:* Các bước tái hiện lỗi (Steps to reproduce - 1, 2, 3...).<br>- *Đối với Usability:* Tiêu chí/Nguyên tắc GUI vi phạm (Ví dụ: Nielsen #1 Visibility, Norman Feedback, Shneiderman Rule #1, IA-01...IA-04). |
| 6 | **Severity** | Mức độ nghiêm trọng theo thang điểm **0 – 4** (HW03 §6 Phase 3):<br>- **4 - Blocker/Critical:** Crash hệ thống, mất dữ liệu, chặn hoàn toàn luồng chính.<br>- **3 - High:** Chức năng quan trọng lỗi, không có cách lách (workaround).<br>- **2 - Medium:** Lỗi chức năng phụ hoặc có cách lách tạm thời.<br>- **1 - Minor:** Lỗi nhỏ, bất tiện nhẹ trong thao tác.<br>- **0 - Cosmetic:** Lỗi thẩm mỹ, căn chỉnh UI, lỗi chính tả văn bản. |
| 7 | **Suggested fix** | Giải pháp hoặc khuyến nghị cải tiến cụ thể dành cho đội phát triển. |
| 8 | **Screenshot ref** | Đường dẫn hoặc mã đính kèm ảnh minh chứng (Ví dụ: `screenshots/A1_BUG01.png`). *Lưu ý: Ảnh kiểm thử tương thích thiết bị phải có overlay email sinh viên `MSSV@....edu.vn` (§6 & §12).* |
| 9 | **Form-submission timestamp** | Thời gian chính xác khi gửi báo cáo lên Google Form (Định dạng: `DD-MM-YYYY HH:MM:SS`). |

---

## 3. Bảng Mẫu Bug & Usability Findings Log (`bug_report.md`)

| ID | Scenario/Screen | Type | Description | Steps/Heuristic | Severity | Suggested fix | Screenshot ref | Form-submission timestamp |
| :---: | :--- | :---: | :--- | :--- | :---: | :--- | :--- | :---: |
| BUG-01 | Scenario A (A2) Add/Edit Event | Bug | **Pre-conditions:** Đã đăng nhập tài khoản ADMIN.<br>**Actual:** Tải ảnh thumbnail tỷ lệ 16:9 không báo lỗi validation mà bị xén mép ảnh.<br>**Expected:** Hiển thị thông báo yêu cầu đúng tỷ lệ 4:3. | **Steps:**<br>1. Vào Admin > Events > Add Event.<br>2. Upload tệp ảnh 16:9 vào ô Thumbnail.<br>3. Nhấn Lưu. | 2 | Thêm hàm check aspect ratio ở client và thông báo lỗi rõ ràng trước khi upload. | `screenshots/A2_BUG01.png` | 26-07-2026 21:15:00 |
| USA-01 | Scenario B (B1) Home listing | Usability | **Friction:** Carousel sự kiện nổi bật không có nút tạm dừng hoặc indicator chỉ số trang, khiến người dùng bị trôi thông tin khi đang đọc. | **Heuristic:** Nielsen #3 (User control and freedom) / IA-03 (Navigation & control). | 1 | Bổ sung nút Pause/Play khi hover và thanh chỉ số dots cho Carousel. | `screenshots/B1_USA01.png` | 26-07-2026 21:20:00 |

---

## 4. Nguyên tắc Viết Báo cáo & Kiểm định Chất lượng (HW03 Integrity Guidelines)

1. **Tính Tái Hiện (Reproducibility):** Mọi Bug phải được xác minh tái hiện tối thiểu 2-3 lần trên môi trường SUT thực tế (`https://promoter-starboard-prude.ngrok-free.dev/`).
2. **Minh Chứng Thực Tế (Anti-AI-Cheat §12):** 
   - Không bịa đặt lỗi hoặc tạo ảnh giả lập do AI sinh.
   - Minh chứng ảnh chụp màn hình phải phản ánh đúng trạng thái EMS live.
   - Minh chứng kiểm thử cross-platform (Task 3) bắt buộc có overlay email `MSSV@....edu.vn`.
3. **Đồng Bộ Dữ Liệu (§7):** Đảm bảo số lượng, nội dung và Severity trong file log này trùng khớp chính xác với các lượt submit trên Google Form.
4. **Phân Định Rõ Bug vs Usability:** Bug là hệ thống chạy sai đặc tả/kỹ thuật; Usability là hệ thống chạy đúng kỹ thuật nhưng gây khó hiểu, thao tác bất tiện cho người dùng.
