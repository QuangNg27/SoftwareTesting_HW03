### [26-07-2026 21:03] | Gemini
```text
1. thiết lập skill @[ai_audit_prompt_log.md] áp dụng cho toàn bộ promt trong conversation này
2. chỉnh @[bug_report.md] theo thông tin yêu cầu trong @[2026.HW03.GUI Usability EMS_En.pdf] rồi thiết lập skill luôn
```

### [26-07-2026 21:06] | Gemini
```text
lấy output giống 100% trong conversation không được lược bớt
```

### [26-07-2026 21:08] | Gemini
```text
có thể chỉnh sửa skill để đảm bảo luôn lấy được output như vậy
```

### [26-07-2026 21:27] | Gemini
```text
đọc @[2026.HW03.GUI Usability EMS_En.pdf] xem có scenario nào tách ra được và vẫn có ý nghĩa để test
```

### [26-07-2026 21:30] | Gemini
```text
vẫn phải có đủ ít nhất 3 screen
```

### [26-07-2026 21:45] | Gemini
```text
ý là phải tách từ 1 trong 4 scenario đang có sẵn
```

### [26-07-2026 21:50] | Gemini
```text
cái A3 nằm trong màn của A2
```

### [27-07-2026 10:03] | Gemini
```text
phân tích yêu cầu đề bài về main report trong @[2026.HW03.GUI Usability EMS_En.pdf] rồi ghi vào @[Report.md] chọn Scenario D, làm đến phần checklist execution cho các screen (chưa cần điền)
```

### [27-07-2026 10:08] | Gemini
```text
dùng checklist từ @[shared_gui_checklist.md]
```

### [27-07-2026 10:14] | Gemini
```text
sử dụng @[shared_gui_checklist.md] cho mỗi screen chỉ cần để cột Verdict(Pass/Fail/NA) và Ghi chú lỗi (Notes)
```

### [27-07-2026 10:28] | Gemini
```text
Hãy dùng Puppeteer MCP mở trang  htps://promoter-starboard-prude.ngrok-free.dev
```

### [27-07-2026 10:30] | Gemini
```text
cấu hỉnh puppeteer mở browser bằng profile của tôi
```

### [27-07-2026 10:38] | Gemini
```text
Hãy dùng Puppeteer MCP mở trang  htps://promoter-starboard-prude.ngrok-free.dev, dùng option Sinh viên nhập tài khoản 23127462@student.hcmus.edu.vn / Qu@ng2702
```

### [27-07-2026 11:00] | Gemini
```text
tách màn hình D2 ra một cái là List 1 cái là Detail phần section 1.2
```

### [27-07-2026 11:31] | Gemini
```text
test screen D1 và điền vào checklist trong Report.md (không được chỉnh sửa gì khác ngoài bảng checklist của screen D1 (mục 2.1), nếu có bug thì điền vào @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\bug_and_usability_findings_log.md] kèm hình vào @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\bug_screenshot]. Nhập pass là Qu@n9462
```

### [27-07-2026 11:35] | Gemini
```text
ảnh chụp bug đâu sao không lưu vào @[bug_screenshot]
```

### [27-07-2026 11:42] | Gemini
```text
xóa bug USA-01 đi vì nó có dấu * mà
```

### [27-07-2026 11:44] | Gemini
```text
tự động điều chỉnh AI Audit Report những promt mà có sự điều chỉnh sau đó (đừng để Valid)
```

### [27-07-2026 11:47] | Gemini
```text
cập nhật lại AI output đầy đủ
```

### [27-07-2026 11:48] | Gemini
```text
chỉnh lại format AI Output
```

### [27-07-2026 11:50] | Gemini
```text
bỏ tác vụ 15, 16 đi
```

### [27-07-2026 11:52] | Gemini
```text
tạo agent skill GUI checklist execution rồi thiết lập
```

### [27-07-2026 11:54] | Gemini
```text
cách cài skill vào antigravity tự trigger luôn á
```

### [27-07-2026 11:56] | Gemini
```text
set cho 2 skill kia luôn
```

### [27-07-2026 11:58] | Gemini
```text
thế tôi xóa @[skill] được rồi nhỉ
```

### [27-07-2026 14:12] | Gemini
```text
tùy chỉnh lại section 1.1 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md] chỉ còn phía User thôi
```

### [27-07-2026 14:28] | Gemini
```text
cập nhật bảng checklist 2.1 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md] cái nào pass rồi thì bỏ ghi chú lỗi còn NA/Fail thì giữ
```

### [27-07-2026 14:30] | Gemini
```text
cập nhật skill phần ghi chú như vậy (nếu có)
```

### [27-07-2026 15:36] | Gemini
```text
thêm báo cáo bug cho IA-04-01, IA-04-10
```

### [27-07-2026 15:37] | Gemini
```text
chỉnh screenshot ref bấm được
```

### [27-07-2026 15:38] | Gemini
```text
không bấm được
```

### [27-07-2026 20:00] | Gemini
```text
rà soát lại item nào fail ở checklist 2.1 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md] rồi kiểm tra @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\bug_and_usability_findings_log.md] xem có thiếu không thì điền thêm
```

### [27-07-2026 20:33] | Gemini
```text
điền thêm vào @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\bug_and_usability_findings_log.md] cho item IA-04-13 của section 2.1 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md]
```

### [28-07-2026 20:05] | Gemini
```text
log bug cho section 2.2 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md]
```

### [28-07-2026 21:02] | Gemini
```text
truy cập đây https://prod-dev.ems-fitus.cloud/complaints/18, thực hiện GUI checklist execution dùng skill  (có lỗi thì chụp vào @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\bug_screenshot] )  đã có cho section 2.3 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md]
```

### [28-07-2026 21:06] | Gemini
```text
hình truy cập sai địa chỉ rồi
```

### [28-07-2026 21:09] | Gemini
```text
ảnh chụp không bật lên được
```

### [28-07-2026 21:21] | Gemini
```text
điều chỉnh lại bug log của section 2.3
```

### [28-07-2026 21:45] | Gemini
```text
sửa section 1.1 và 1.2 thêm phần của Admin theo đề @[2026.HW03.GUI Usability EMS_En.pdf], thêm 2 checklist cho màn D3, D4
```

### [28-07-2026 21:48] | Gemini
```text
hủy kết quả test của màn D3, D4 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md]
```

### [28-07-2026 22:09] | Gemini
```text
vào trang https://prod-dev.ems-fitus.cloud/dashboard/admin/complaints, dùng tài khoản admin: admin@gmail.com/Admin@123, thực hiện /gui-checklist-execution cho màn hình D3 (section 2.4 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md] )
```

### [28-07-2026 22:13] | Gemini
```text
chỉnh lại skill là giữ nguyên kích thước màn hình khi test chứ đang màn hình to rồi thu nhỏ về xong chụp bug là không phù hợp
```

### [28-07-2026 22:14] | Gemini
```text
có thể thu lại để test cho việc responsive
```

### [29-07-2026 20:49] | Gemini
```text
cập bug log cho item nào fail của checklist section 2.5 @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md] (không cần chạy test)
```

### [29-07-2026 20:53] | Gemini
```text
tạo sẵn đường link ảnh cho các bug vừa add cho tôi @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\bug_and_usability_findings_log.md]
```

### [29-07-2026 21:21] | Gemini
```text
cập nhật tên màn hình trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\bug_and_usability_findings_log.md] ghi rõ ra chứ đừng ghi mã
```

### [29-07-2026 21:23] | Gemini
```text
mấy url có số thì để là [id]
```

### [29-07-2026 21:31] | Gemini
```text
đọc lại đề @[2026.HW03.GUI Usability EMS_En.pdf] ,xem yêu cầu của task 2 và 3 rồi tạo outline trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md]
```

### [29-07-2026 21:40] | Gemini
```text
bảng ma trận 4.2 chia ra mỗi màn một bảng
```

### [29-07-2026 21:42] | Gemini
```text
ghi tên hệ điều hành, browser, device ngắn gọn giống như này thôi  3 operatng systems — e.g. Windows, macOS, and Android or iOS.
 5 browsers — e.g. Chrome, Firefox, Safari, Edge, and Opera (or Samsung Internet on
mobile).
 3 device classes — desktop, tablet, and phone.
```

### [29-07-2026 21:44] | Gemini
```text
bỏ trường hợp android + chrome
```

### [29-07-2026 21:45] | Gemini
```text
đổi samsung internet thành chrome
```

### [29-07-2026 21:51] | Gemini
```text
phần Task 2 @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md]  chỉ cần giữ luồng user thôi
```

### [29-07-2026 21:54] | Gemini
```text
đổi đường dẫn thành tên màn hình (section 3.1 @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md] )
```

### [30-07-2026 21:19] | Gemini
```text
đổi thư mục các ảnh minh chứng ở section 4.2 @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md] sang @[cross_browser_sceenshot]
```

### [01-08-2026 09:45] | Gemini
```text
chỉnh tên file ảnh trong @[cross_browser_sceenshot] cái nào mac_opera thì đổi thành win_opera
```

### [01-08-2026 10:01] | Gemini
```text
xây dựng các câu hỏi SUS ở phần task 2
```

### [01-08-2026 10:16] | Gemini
```text
Tạo google form
```

### [01-08-2026 10:40] | Gemini
```text
Thêm probe question cho task 2 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md]
```

### [01-08-2026 11:15] | Gemini
```text
đưa 2 cái lỗi UI trong phần 4.2.4 và 4.2.5 trong @[d:\NAM_3\HK3\KTPM\HW03\SoftwareTesting_HW03\Report.md] ra bug log
```