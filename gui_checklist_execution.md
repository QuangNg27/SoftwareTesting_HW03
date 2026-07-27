# Hướng dẫn Kỹ năng: Thực thi Kiểm thử GUI Checklist (GUI Checklist Execution Skill) - HW03 EMS

Tài liệu này định nghĩa kỹ năng và quy trình chuẩn (Standard Operating Procedure - SOP) dành cho AI Agent để thực thi kiểm thử giao diện đồ họa (GUI Checklist Execution) trên từng màn hình của hệ thống **EMS (Event Management System)** theo yêu cầu của bài tập **HW03 – GUI & Usability Testing on EMS**.

---

## 1. Nguồn Tiêu chí Kiểm thử (Checklist Source of Truth)
AI Agent phải luôn sử dụng đầy đủ **48 tiêu chí kiểm thử tiêu chuẩn (IA-01-01 đến IA-04-12)** trích từ [shared_gui_checklist.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/shared_gui_checklist.md) bao phủ 4 khía cạnh chính.

---

## 2. Quy trình Thực thi Kiểm thử Live (Execution Protocol)

### Bước 1: Điều hướng & Khảo sát DOM qua Puppeteer MCP
- Khởi chạy Puppeteer MCP với `puppeteer_profile`.

### Bước 2: Đánh giá Tiêu chí (Verdict Assignment Rules)
- `Pass`: Thỏa mãn 100%.
- `Fail`: Vi phạm tiêu chí / xuất hiện lỗi.
- `NA`: Không áp dụng.

### Bước 3: Ghi nhận Lỗi & Chụp Minh chứng Live (Double Reporting §7 & §12)
- Log 9 cột vào `bug_and_usability_findings_log.md` & decode ảnh Base64 ra file PNG lưu tại `bug_screenshot/`.

### Bước 4: Cập nhật Báo cáo Chính (`Report.md`)
- **Quy tắc Cột Ghi Chú Lỗi (Notes Rule):**
  - đối với các tiêu chí đánh giá là **`Pass`**: Bắt buộc để trống cột *Ghi Chú Lỗi (Notes)*.
  - đối với các tiêu chí đánh giá là **`Fail`** hoặc **`NA`**: Giữ nguyên nội dung ghi chú chi tiết mô tả lỗi hoặc lý do không áp dụng.

### Bước 5: Nhật ký Prompt & Audit AI (`ai_audit_prompt_log.md` Alignment)
- Ghi prompt vào `promt_log.md`, trích 100% untruncated verbatim output vào `AI_Audit_Report.md`, mark `INVALID` nếu bị sửa đổi.
