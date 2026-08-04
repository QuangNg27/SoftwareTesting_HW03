# HW03 EMS - GUI & Usability Testing Deliverables

**Course:** CS423 – CSC15003 Software Testing (AI-augmented · 2026)  
**Student Name:** Nguyễn Minh Quang  
**Student ID:** 23127462  
**Class:** 23KTPM4

---

## 1. Bảng Tự Đánh giá (Self-Assessment Table)

| No. | Criteria | Max Grade | Self-Assessed Grade |
|:---:|---|:---:|:---:|
| **1a** | **Task 1A — Shared checklist** (> 40 items, IA-01…IA-04) + reference sources + AI prompts (group) | 15 | **15 / 15** |
| **1b** | **Task 1B — Checklist execution** on ≥ 3 screens + bug reports (individual) | 15 | **15 / 15** |
| **2** | **Task 2 — User testing** with 5 real users (scenario + 5 sessions + analysis → Usability Report) | 25 | **25 / 25** |
| **3** | **Task 3 — Cross-Browser / Cross-Platform matrix** (3 OS × 5 browsers × 3 device classes) | 25 | **25 / 25** |
| **4** | **Bug & Usability Findings submission** (Google Form) + aggregated log | 10 | **10 / 10** |
| **5** | **Agent Skills** | 10 | **10 / 10** |
| **TOTAL** | | **100** | **100 / 100** |

---

## 2. Tóm tắt Kết quả Kiểm thử (Test Summary)

### Kịch bản Đã chọn (Chosen Scenario):
- **Scenario D:** User requests Support and Admin resolves it.

### Các Màn hình Đã Kiểm thử (5 Screens Tested):
1. **Screen D1:** Màn hình Tạo Yêu cầu Hỗ trợ Sinh viên (`/complaints/new`)
2. **Screen D2.1:** Màn hình Danh sách Yêu cầu Hỗ trợ Sinh viên (`/complaints`)
3. **Screen D2.2:** Màn hình Chi tiết Yêu cầu Hỗ trợ Sinh viên (`/complaints/[id]`)
4. **Screen D3:** Màn hình Danh sách Yêu cầu Hỗ trợ Quản trị viên (`/dashboard/admin/complaints`)
5. **Screen D4:** Màn hình Chi tiết Yêu cầu Hỗ trợ Quản trị viên (`/dashboard/admin/complaints/[id]`)

### Thống kê Bộ Tiêu chí Checklist (Checklist Metrics):
- **Số tiêu chí thiết kế (Designed):** 50 tiêu chí chuẩn (`IA-01-01` đến `IA-04-14` bao phủ Information Architecture, Interaction, Visual Aesthetics & Navigation).
- **Số lượt thực thi (Executed):** 50 tiêu chí × 5 màn hình = **250 lượt kiểm thử**.
- **Đạt (Passed):** 118 lượt.
- **Lỗi / Vi phạm (Failed / Friction):** 22 lượt.
- **Không áp dụng (N/A):** 110 lượt.

### Thống kê Lỗi Hệ thống (Bugs Count):
- **Tổng số Lỗi Hệ thống (System Bugs):** **3 Bugs**
  - `BUG-01`: Lỗi loading trang chi tiết yêu cầu khi click vào Toast thông báo điều hướng.
  - `BUG-02`: Lỗi thành phần chọn số dòng hiển thị mỗi trang (Rows per page) không cho phép thay đổi.
  - `BUG-03`: Lỗi xử lý sự kiện phím trên thanh tìm kiếm bị giật/khựng khi gõ phím liên tục.
- **Tổng số lỗi usability (Usability Findings):** 24 lỗi (`USA-01` đến `USA-25`, trừ `USA-12`).
  - **Mức độ 1 (Severity 1 - Minor):** 18 issues.
  - **Mức độ 2 (Severity 2 - Medium):** 6 issues.

### Thống kê Kiểm thử Người dùng (User-Testing Summary - Task 2):
- **Số lượng người tham gia thực tế:** **5 người dùng** (4 Sinh viên, 1 Khách).
  1. Nguyễn Vũ Minh Quang
  2. Phạm Hồng Thái Dương
  3. Võ Nhật Hào
  4. Ngô Thế Đạt
  5. Đặng Thị Xuyên Linh (Khách)
- **Thời gian hoàn thành trung bình (Time on Task):** 2 phút 18 giây.
- **Điểm số SUS trung bình (Mean SUS Score):** **54.0 / 100** (Phân loại: *Below Average / Grade D*).

### Ma trận Kiểm thử Tương thích (Compatibility Matrix Coverage - Task 3):
- **Số bảng ma trận:** 5 bảng (mỗi màn hình 1 bảng ma trận độc lập).
- **Tổ hợp kiểm thử:** 7 tổ hợp môi trường thực tế per screen (Tổng cộng 35 cell executions).
- **Hệ điều hành (3 OS):** Windows, macOS, iOS.
- **Trình duyệt (5 Browsers):** Chrome, Firefox, Safari, Edge, Opera.
- **Lớp thiết bị (3 Device Classes):** Desktop, Tablet, Phone.

---

## 3. Video demo agent skill

Youtube link: https://youtu.be/F0BHDoA6EF0
