---
name: gui-checklist-execution
description: Automatically performs GUI Checklist Execution for EMS SUT screens, evaluates 48 criteria (IA-01-01 to IA-04-12), logs defects into bug_and_usability_findings_log.md, saves PNG screenshots to bug_screenshot/, updates Report.md (leaving Notes empty for Pass items and keeping Notes for Fail/NA items), and maintains AI_Audit_Report.md and promt_log.md. Activate/trigger this skill whenever the user asks to test an EMS screen, run a GUI checklist execution, or log bugs.
---

# Hướng dẫn Kỹ năng: Thực thi Kiểm thử GUI Checklist (GUI Checklist Execution Skill) - HW03 EMS

Tài liệu này định nghĩa kỹ năng và quy trình chuẩn (Standard Operating Procedure - SOP) dành cho AI Agent để thực thi kiểm thử giao diện đồ họa (GUI Checklist Execution) trên từng màn hình của hệ thống **EMS (Event Management System)** theo yêu cầu của bài tập **HW03 – GUI & Usability Testing on EMS**.

---

## 1. Nguồn Tiêu chí Kiểm thử (Checklist Source of Truth)
AI Agent phải luôn sử dụng đầy đủ **48 tiêu chí kiểm thử tiêu chuẩn (IA-01-01 đến IA-04-12)** trích từ [shared_gui_checklist.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/shared_gui_checklist.md) bao phủ 4 khía cạnh chính:
1. **IA-01 General UI Standards (12 items):** Grid, Spacing, Typography, Buttons, i18n EN/VI, Empty State, Loading State, Responsive, Image Aspect Ratios (4:3 & 24:9), Icon Alignment, Contrast (WCAG), Links (_blank vs current tab), Cropping.
2. **IA-02 Forms (12 items):** Required Fields (* đỏ), Label Proximity, Real-time Validation, Specific Error Messages, File Upload Constraints (accept & max 5MB), Rich Text, Keyboard Tab Order, Disabled Submit Button, Date Format, Reset/Cancel Form, Autofill, Toggle Password.
3. **IA-03 Navigation (12 items):** Fixed/Sticky Header, Active Nav State, Back Action, Deep Links, Breadcrumbs, Reorder Drag UI, Quick Tabs, Broken Links 404, Back to Top, Sidebar Toggle, URL Filter Sync, Drag Handles.
4. **IA-04 Feedback & State (12 items):** Toasts (3-5s), Toast Colors, Confirmation Dialog, Badges, Loading Spinner, Semantic Colors, Notification Dot, Lightbox Image View, Real-time Updates, Offline Toast, Double-click Prevention, Barcode/QR Legibility.

---

## 2. Quy trình Thực thi Kiểm thử Live (Execution Protocol)

### Bước 1: Điều hướng & Khảo sát DOM qua Puppeteer MCP
- **Khởi chạy Puppeteer:** Bắt buộc sử dụng Puppeteer MCP với tham số Profile cá nhân:
  ```json
  {
    "allowDangerous": true,
    "launchOptions": {
      "headless": false,
      "args": ["--user-data-dir=C:\\Users\\admin\\.gemini\\antigravity\\puppeteer_profile", "--no-sandbox"]
    },
    "url": "<Target_Screen_URL>"
  }
  ```
- **Khảo sát DOM:** Sử dụng `puppeteer_evaluate` trích xuất thông tin thực tế: H1-H4, Inputs, Selects, Textareas, Labels, Buttons, Links, Toast notifications, ARIA labels và thuộc tính HTML.

### Bước 2: Đánh giá Tiêu chí (Verdict Assignment Rules)
Dựa trên bằng chứng thực nghiệm thu thập từ Puppeteer DOM:
- **`Pass`:** Giao diện SUT live thỏa mãn 100% mục tiêu của tiêu chí kiểm thử.
- **`Fail`:** Giao diện SUT live vi phạm tiêu chí, xuất hiện lỗi kỹ thuật/giao diện hoặc điểm gây khó khăn (friction point) cho trải nghiệm người dùng.
- **`NA`:** Tiêu chí không áp dụng cho bản chất vật lý của màn hình hiện tại.

### Bước 3: Ghi nhận Lỗi & Chụp Minh chứng Live (Double Reporting §7 & §12)
Nếu tiêu chí được đánh giá là **`Fail`**:
1. **Phân loại:** 
   - Hệ thống chạy sai spec/kỹ thuật -> Ghi nhận là **`Bug`** (`BUG-xx`).
   - Hệ thống chạy đúng spec nhưng thao tác khó khăn -> Ghi nhận là **`Usability`** (`USA-xx`).
2. **Cập nhật Nhật ký Lỗi:** Ghi 9 cột tiêu chuẩn vào [bug_and_usability_findings_log.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/bug_and_usability_findings_log.md).
3. **Lưu trữ File Ảnh PNG:**
   - Chụp Base64 bằng `puppeteer_screenshot` (với `encoded: true`).
   - Sử dụng script Python `save_images.py` decode và lưu file ảnh PNG vật lý vào thư mục `d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\bug_screenshot\<BUG_ID>_<Screen>_<Name>.png`.

### Bước 4: Cập nhật Báo cáo Báo cáo Chính (`Report.md`)
- **Tập trung Phạm vi:** Chỉ cập nhật Bảng thực thi của màn hình được yêu cầu.
- **Quy tắc Cột Ghi Chú Lỗi (Notes Rule):**
  - đối với các tiêu chí đánh giá là **`Pass`**: Bắt buộc để trống cột *Ghi Chú Lỗi (Notes)*.
  - đối với các tiêu chí đánh giá là **`Fail`** hoặc **`NA`**: Giữ nguyên nội dung ghi chú chi tiết mô tả lỗi hoặc lý do không áp dụng.
- **Tuyệt đối tuân thủ:** Không thay đổi bất kỳ mục hoặc bảng kiểm thử của các màn hình khác trong `Report.md`.

### Bước 5: Nhật ký Prompt & Audit AI (`ai_audit_prompt_log.md` Alignment)
1. Cập nhật prompt gốc của người dùng vào [promt_log.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/promt_log.md).
2. Trích xuất **100% nguyên văn phản hồi của AI (untruncated response)** từ `transcript_full.jsonl` và ghi vào mục `2. AI output` (dùng 4 backtick ````text ... ````) trong [AI_Audit_Report.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/AI_Audit_Report.md).
3. Nếu người dùng phản hồi điều chỉnh lại kết quả của AI ở tác vụ trước đó, bắt buộc chuyển Verdict của tác vụ trước thành **`INVALID`** để đảm bảo tính trung thực học thuật.
