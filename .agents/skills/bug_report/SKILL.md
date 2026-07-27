---
name: bug-report
description: Manages double-channel bug and usability reporting (§7 HW03 EMS). Defines 9 mandatory columns (ID, Scenario/Screen, Type, Description, Steps/Heuristic, Severity 0-4, Suggested fix, Screenshot ref, Form-submission timestamp) for bug_and_usability_findings_log.md and physical PNG screenshot saving into bug_screenshot/. Trigger this skill whenever logging bugs, usability issues, or saving evidence screenshots.
---

# Hướng dẫn Kỹ năng: Báo cáo Lỗi & Vấn đề Khả dụng (Bug & Usability Findings Log) - HW03 EMS

Tài liệu này định nghĩa kỹ năng và quy trình chuẩn để ghi nhận, quản lý và báo cáo các lỗi chức năng (Bugs) và các vấn đề về khả năng sử dụng (Usability Issues) đối với hệ thống **EMS (Event Management System)** theo yêu cầu của bài tập **HW03 – GUI & Usability Testing on EMS**.

---

## 1. Mục tiêu & Quy định Báo cáo (HW03 Section 7)
Mọi phát hiện lỗi (Defects) và cải tiến khả năng sử dụng (Usability Improvements) phát hiện được từ các Task 1–3 phải được báo cáo theo **kênh đôi (Double Reporting)**:
1. **Google Form:** Gửi từng phát hiện lên kênh tiếp nhận qua Google Form (https://forms.gle/CJQFQCAXcsDbXDMM9) sử dụng email sinh viên (`MSSV@....edu.vn`).
2. **Aggregated Findings Log:** Tổng hợp toàn bộ các item đã gửi lên form thành một file duy nhất (`bug_and_usability_findings_log.md`) đính kèm trong bài nộp. Nội dung trong log và Google Form phải khớp chính xác 100%.

---

## 2. Cấu trúc Cột trong Bảng Bug & Usability Findings Log

Bảng nhật ký phải bảo đảm tối thiểu 9 cột tiêu chuẩn theo yêu cầu của đề bài HW03 (§7):

| STT | Tên Cột | Mô tả & Quy chuẩn |
| :---: | :--- | :--- |
| 1 | **ID** | Mã định danh duy nhất cho từng phát hiện (`BUG-01`, `BUG-02` cho Lỗi; `USA-01`, `USA-02` cho Usability). |
| 2 | **Scenario/Screen** | Kịch bản và Màn hình kiểm thử (Ví dụ: `Scenario D (D1) - Create Support Request Form`). |
| 3 | **Type** | Phân loại phát hiện: **`Bug`** (Lỗi chức năng/giao diện) hoặc **`Usability`** (Vấn đề trải nghiệm người dùng/trực quan). |
| 4 | **Description** | Mô tả chi tiết vấn đề:<br>- *Đối với Bug:* Điều kiện tiên quyết (Pre-conditions), Kết quả thực tế (Actual Result) vs Kết quả mong đợi (Expected Result).<br>- *Đối với Usability:* Điểm gây khó khăn cho người dùng (Friction point), ngữ cảnh xảy ra và tác động. |
| 5 | **Steps/Heuristic** | Chi tiết kỹ thuật tái hiện hoặc cơ sở đánh giá:<br>- *Đối với Bug:* Các bước tái hiện lỗi (Steps to reproduce - 1, 2, 3...).<br>- *Đối với Usability:* Tiêu chí/Nguyên tắc GUI vi phạm (Ví dụ: Nielsen #1 Visibility, Norman Feedback, Shneiderman Rule #1, IA-01...IA-04). |
| 6 | **Severity** | Mức độ nghiêm trọng theo thang điểm **0 – 4** (HW03 §6 Phase 3):<br>- **4 - Blocker/Critical:** Crash hệ thống, mất dữ liệu, chặn hoàn toàn luồng chính.<br>- **3 - High:** Chức năng quan trọng lỗi, không có cách lách (workaround).<br>- **2 - Medium:** Lỗi chức năng phụ hoặc có cách lách tạm thời.<br>- **1 - Minor:** Lỗi nhỏ, bất tiện nhẹ trong thao tác.<br>- **0 - Cosmetic:** Lỗi thẩm mỹ, căn chỉnh UI, lỗi chính tả văn bản. |
| 7 | **Suggested fix** | Giải pháp hoặc khuyến nghị cải tiến cụ thể dành cho đội phát triển. |
| 8 | **Screenshot ref** | Đường dẫn tệp ảnh PNG thực tế saved trên ổ đĩa (Ví dụ: `bug_screenshot/BUG-01_D1_Submit_Enabled_On_Empty_Form.png`). |
| 9 | **Form-submission timestamp** | Thời gian chính xác khi gửi báo cáo lên Google Form (Định dạng: `DD-MM-YYYY HH:MM:SS`). |

---

## 3. Nguyên tắc Viết Báo cáo & Kiểm định Chất lượng (HW03 Integrity Guidelines)

1. **Tính Tái Hiện (Reproducibility):** Mọi Bug phải được xác minh tái hiện tối thiểu 2-3 lần trên môi trường SUT thực tế (`https://promoter-starboard-prude.ngrok-free.dev/`).
2. **Minh Chứng Thực Tế (Anti-AI-Cheat §12):** Không bịa đặt lỗi hoặc tạo ảnh giả lập. Minh chứng ảnh chụp màn hình phải là tệp PNG thực tế lưu trong `bug_screenshot/`.
3. **Đồng Bộ Dữ Liệu (§7):** Đảm bảo số lượng, nội dung và Severity trong file log trùng khớp chính xác với các lượt submit trên Google Form.
