# Bug and Usability Findings Log - HW03 EMS

Tài liệu nhật ký ghi nhận toàn bộ Lỗi hệ thống (Bugs) và Lỗi khả năng sử dụng (Usability Issues) phát hiện được trên hệ thống EMS live theo đúng quy định tại Section 7 của `2026.HW03.GUI Usability EMS_En.pdf`.

---

## Bảng Nhật ký Lỗi & Khảo sát GUI (Bug & Usability Findings Log)

| ID | Scenario/Screen | Type (Bug \| Usability) | Description (Pre-conditions, Actual vs Expected / Friction) | Steps/Heuristic | Severity (0-4) | Suggested fix | Screenshot ref | Form-submission timestamp |
|---|---|---|---|---|---|---|---|---|
| **BUG-01** | Scenario D / Screen D1 (`/complaints/new`) | Bug | **Pre-conditions:** Để trống form.<br>**Actual:** Nút `Submit request` vẫn duy trì trạng thái enabled và click được khi form trống.<br>**Expected:** Nút Submit bị vô hiệu hóa (disabled) cho tới khi điền hợp lệ. | 1. Truy cập `/complaints/new`<br>2. Để trống các ô dữ liệu.<br>3. Kiểm tra nút Submit request.<br>*Vi phạm: Nielsen #5 Error Prevention (IA-02-08)* | 2 | Thêm thuộc tính `disabled` cho nút Submit khi form chưa đủ thông tin hợp lệ. | `bug_screenshot/BUG-01_D1_Submit_Enabled_On_Empty_Form.png` | 27-07-2026 11:33 |
| **USA-02** | Scenario D / Screen D1 (`/complaints/new`) | Usability | **Pre-conditions:** Đã đăng nhập sinh viên.<br>**Actual:** Màn hình tạo yêu cầu hỗ trợ không có thanh điều hướng Breadcrumbs.<br>**Expected:** Có Breadcrumbs `Home > Support Requests > Create`. | 1. Truy cập `/complaints/new`<br>2. Kiểm tra phần trên cùng của trang.<br>*Vi phạm: Nielsen #6 Recognition (IA-03-05)* | 1 | Bổ sung dải Breadcrumb trail ở góc trên tiêu đề form. | `bug_screenshot/USA-02_D1_Missing_Breadcrumb.png` | 27-07-2026 11:33 |
