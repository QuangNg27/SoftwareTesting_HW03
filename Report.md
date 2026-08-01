# BÁO CÁO GUI & Usability Testing on EMS (Event Management System)

* **Môn học:** Kiểm thử Phần mềm
* **Sinh viên:** Nguyễn Minh Quang - 23127462
* **Hệ thống kiểm thử (SUT):** EMS (Event Management System) - https://prod-dev.ems-fitus.cloud
* **Kịch bản lựa chọn (Chosen Scenario):** **Scenario D — User requests Support and Admin resolves it**

---

## 1. TỔNG QUAN VỀ PHẠM VI KIỂM THỬ

### 1.1. Lý do Lựa chọn Kịch bản
Trong bài tập HW03, **Scenario D — User requests Support and Admin resolves it** được lựa chọn nhằm bao phủ trọn vẹn vòng đời quản lý và xử lý yêu cầu hỗ trợ (Support Request lifecycle) trên cả hai khía cạnh **Giao diện Người dùng (User Side)** và **Giao diện Quản trị viên (Admin Side)** theo đúng yêu cầu đề bài:

- **Phía Người dùng (User Side):** Bao phủ luồng nghiệp vụ của sinh viên khi gặp sự cố trên hệ thống EMS: từ khâu khởi tạo phiếu hỗ trợ (Support Ticket) mới với tệp ảnh đính kèm minh chứng (`Screen D1`), quản lý danh sách phiếu hỗ trợ cá nhân và bộ lọc trạng thái (`Screen D2.1`), đến khâu xem chi tiết phản hồi chính thức từ nhà trường (`Screen D2.2`).
- **Phía Quản trị viên (Admin Side):** Bao phủ luồng nghiệp vụ của Admin khi tiếp nhận và giải quyết sự cố: theo dõi danh sách toàn bộ các yêu cầu hỗ trợ, phân loại các tab trạng thái `Pending` / `Resolved` và tìm kiếm (`Screen D3`), kiểm tra chi tiết nội dung sự cố, xem ảnh minh chứng qua Lightbox, bổ sung ghi chú nội bộ (`Internal note`) và phản hồi chính thức (`Official response`) (`Screen D4`).

### 1.2. Danh sách 5 Màn hình Kiểm thử được Lựa chọn
Để đảm bảo tính toàn diện và rõ ràng giữa phía User và Admin, 5 màn hình của **Scenario D** được đưa vào phạm vi kiểm thử:

| STT | Mã Màn hình | Tên Màn hình (Screen Name) | Vai trò & Phạm vi Nghiệp vụ | Interface aspects |
| :---: | :---: | :--- | :--- | :--- |
| 1 | **D1** | **Create Support Request Form (User)** | Form cho sinh viên tạo yêu cầu hỗ trợ mới: chọn danh mục sự cố, nhập nội dung chi tiết, tải tệp đính kèm minh chứng. | **IA-02** (Forms, Uploads) & **IA-01** (Layout) |
| 2 | **D2.1** | **My Support Requests List (User)** | Danh sách các yêu cầu hỗ trợ cá nhân của sinh viên: phân trang, lọc theo trạng thái (`Pending` / `Resolved`), hiển thị badge ticket. | **IA-03** (Navigation, Tabs) & **IA-04** (Badges) |
| 3 | **D2.2** | **Support Request Detail (User Side)** | Màn hình xem chi tiết yêu cầu hỗ trợ cá nhân: theo dõi dòng thời gian xử lý, câu trả lời chính thức từ Admin và ảnh đính kèm. | **IA-04** (Feedback) & **IA-01** (Typography) |
| 4 | **D3** | **Support Requests List (Admin Side)** | Màn hình Admin quản lý danh sách toàn bộ yêu cầu hỗ trợ: chuyển đổi các tab `Pending` / `Resolved`, tìm kiếm và lọc. | **IA-03** (Navigation, Tabs, Filters) & **IA-04** (Status Colours, Badges) |
| 5 | **D4** | **Support Request Detail (Admin Side)** | Màn hình Admin xử lý chi tiết yêu cầu: xem lightbox ảnh đính kèm, viết ghi chú nội bộ (internal note), nhập và gửi phản hồi chính thức (official response). | **IA-02** (Forms, Official Response) & **IA-04** (Lightbox, Toasts, Confirmation) |

---

## 2. KHUNG THỰC THI CHECKLIST TRÊN CÁC MÀN HÌNH SCENARIO D (CHECKLIST EXECUTION)

Dưới đây là Khung kiểm thử (Execution Tables) hoàn chỉnh trên 5 màn hình của **Scenario D**. Cấu trúc bảng của từng màn hình bao gồm các cột chuẩn: **ID**, **Khía Cạnh**, **Mục Kiểm Tra**, **Ánh Xạ Heuristics**, **Verdict (Pass/Fail/NA)** và **Ghi Chú Lỗi (Notes)**.

---

### 2.1. Bảng Thực thi trên Màn hình D1: Create Support Request Form

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Verdict (Pass/Fail/NA) | Ghi Chú (Notes) |
|:---:|:---:|:---|:---|:---:|:---|
| **IA-01-01** | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-02** | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4: Consistency | Pass | |
| **IA-01-03** | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | Pass | |
| **IA-01-04** | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | Pass |  |
| **IA-01-05** | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1: Visibility | NA | Màn hình Form tạo mới, không áp dụng danh sách rỗng. |
| **IA-01-06** | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1: Visibility | NA | Không có load dữ liệu |
| **IA-01-07** | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-08** | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị (tỷ lệ 4:3 và 24:9) trên các kích thước màn hình khác nhau. | Shneiderman: Aesthetics | NA | |
| **IA-01-09** | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman: Aesthetics | Pass | |
| **IA-01-10** | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4: Consistency | Pass | |
| **IA-01-11** | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3: User Control | NA | Không có external link |
| **IA-01-12** | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4: Consistency | NA | |
| **IA-02-01** | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan (ví dụ dấu `*`). | Norman: Constraints | Pass | |
| **IA-02-02** | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng và đi sát với ô nhập liệu. | Nielsen #6: Recognition | Pass | |
| **IA-02-03** | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5: Error Prev. | Fail | Báo lỗi tổng ở dưới thay vì hiển thị báo lỗi đỏ ngay dưới từng ô nhập (Log USA-01). |
| **IA-02-04** | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục thay vì báo lỗi chung chung. | Nielsen #10: Help & Error | Pass | |
| **IA-02-05** | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman: Constraints | Pass | |
| **IA-02-06** | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ và hoạt động mượt mà. | Nielsen #7: Flexibility | NA | Form dùng ô Textarea đếm ký tự 0/255, không dùng Rich Text. |
| **IA-02-07** | Forms | Người dùng có thể nhấn `Tab` để di chuyển tuần tự qua các ô nhập liệu trong form. | Nielsen #7: Flexibility | Pass | |
| **IA-02-08** | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ. | Nielsen #5: Error Prev. | Fail | Nút Submit request vẫn active khi các trường trống (Bug Log ID BUG-01). |
| **IA-02-09** | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc đối với người dùng Việt Nam. | Nielsen #2: Match System | NA | Form D1 không có trường chọn ngày giờ. |
| **IA-02-10** | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3: User Control | NA | |
| **IA-02-11** | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill) cho các trường thông tin cơ bản. | Nielsen #7: Flexibility | NA | |
| **IA-02-12** | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu trực quan bằng biểu tượng con mắt. | Nielsen #7: Flexibility | NA | Form D1 không chứa trường nhập mật khẩu. |
| **IA-03-01** | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6: Recognition | Pass | |
| **IA-03-02** | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1: Visibility | NA | |
| **IA-03-03** | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó, không mất trạng thái. | Nielsen #3: User Control | Pass | |
| **IA-03-04** | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết sự kiện mà không bị lỗi 404. | Nielsen #4: Consistency | NA | |
| **IA-03-05** | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | Fail | Màn hình D1 không hiển thị thanh Breadcrumbs (Bug Log ID USA-02). |
| **IA-03-06** | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | NA | Form D1 không có chức năng kéo thả reorder. |
| **IA-03-07** | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | NA | Form D1 không có dạng tab chuyển đổi. |
| **IA-03-08** | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | Pass | |
| **IA-03-09** | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | Pass | Cuộn xuống tới cuối cùng mới có |
| **IA-03-10** | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | NA | Màn hình D1 dùng Header top navbar, không có sidebar. |
| **IA-03-11** | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | NA | Form D1 không có bộ lọc/tab. |
| **IA-03-12** | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | NA | Form D1 không dùng giao diện reorder. |
| **IA-04-01** | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | Fail | Màn hình D1 không hiện thông báo toast sau khi tạo yêu cầu thành công (Log BUG-02). |
| **IA-04-02** | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8: Aesthetic | NA | |
| **IA-04-03** | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5: Error Prev. | NA | |
| **IA-04-04** | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo; trạng thái vé thay đổi tương ứng khi được phê duyệt/hủy. | Nielsen #1: Visibility | Pass | |
| **IA-04-05** | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1: Visibility | Pass | |
| **IA-04-06** | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (Ví dụ: APPROVED màu xanh lá, REJECTED màu đỏ). | Nielsen #2: Match System | NA | Form D1 chưa hiển thị tag trạng thái vé. |
| **IA-04-07** | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có phản hồi | Nielsen #1: Visibility | Pass | |
| **IA-04-08** | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7: Flexibility | Pass | |
| **IA-04-09** | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | Pass | |
| **IA-04-10** | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | Fail | Màn hình D1 không hiển thị thông báo mất kết nối mạng (Log USA-03). |
| **IA-04-11** | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | Pass | |
| **IA-04-12** | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | NA | Form D1 không xuất mã QR code. |
| **IA-04-13** | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | Fail | Ô nhập liệu textbox không thay đổi (focus state) khi nhấp chuột vào (Log USA-04). |
| **IA-04-14** | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, hoặc phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | NA | |

---

### 2.2. Bảng Thực thi trên Màn hình D2.1: My Support Requests List

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Verdict (Pass/Fail/NA) | Ghi Chú (Notes) |
|:---:|:---:|:---|:---|:---:|:---|
| **IA-01-01** | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-02** | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4: Consistency | Pass | |
| **IA-01-03** | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | Pass | |
| **IA-01-04** | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | Pass | |
| **IA-01-05** | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1: Visibility | Pass | |
| **IA-01-06** | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1: Visibility | Pass | |
| **IA-01-07** | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-08** | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị (tỷ lệ 4:3 và 24:9) trên các kích thước màn hình khác nhau. | Shneiderman: Aesthetics | NA | Screen này không có hình ảnh |
| **IA-01-09** | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman: Aesthetics | Pass | |
| **IA-01-10** | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4: Consistency | Pass | |
| **IA-01-11** | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3: User Control | Pass |  |
| **IA-01-12** | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4: Consistency | NA | Screen này không có hình ảnh |
| **IA-02-01** | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan (ví dụ dấu `*`). | Norman: Constraints | NA | Không có required field |
| **IA-02-02** | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng và đi sát với ô nhập liệu. | Nielsen #6: Recognition | Pass | |
| **IA-02-03** | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5: Error Prev. | NA | |
| **IA-02-04** | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục thay vì báo lỗi chung chung. | Nielsen #10: Help & Error | NA | |
| **IA-02-05** | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman: Constraints | NA | |
| **IA-02-06** | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ và hoạt động mượt mà. | Nielsen #7: Flexibility | NA | |
| **IA-02-07** | Forms | Người dùng có thể nhấn `Tab` để di chuyển tuần tự qua các ô nhập liệu trong form. | Nielsen #7: Flexibility | NA | |
| **IA-02-08** | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ. | Nielsen #5: Error Prev. | NA | |
| **IA-02-09** | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc đối với người dùng Việt Nam. | Nielsen #2: Match System | Pass | |
| **IA-02-10** | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3: User Control | NA | Không có nút reset |
| **IA-02-11** | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill) cho các trường thông tin cơ bản. | Nielsen #7: Flexibility | NA | |
| **IA-02-12** | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu trực quan bằng biểu tượng con mắt. | Nielsen #7: Flexibility | NA | |
| **IA-03-01** | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6: Recognition | Pass | |
| **IA-03-02** | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1: Visibility | NA | Screen này nằm ở mục riêng không có trên thanh điều hướng |
| **IA-03-03** | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó, không mất trạng thái. | Nielsen #3: User Control | Pass | |
| **IA-03-04** | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết sự kiện mà không bị lỗi 404. | Nielsen #4: Consistency | NA | |
| **IA-03-05** | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | Fail | Màn hình D2 không hiển thị thanh Breadcrumbs (Log USA-05). |
| **IA-03-06** | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | NA | |
| **IA-03-07** | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | Pass | |
| **IA-03-08** | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | Pass | |
| **IA-03-09** | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | Pass | |
| **IA-03-10** | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | NA | Screen không có sidebar |
| **IA-03-11** | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | Pass | |
| **IA-03-12** | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | NA | Không có giao diện kéo thả |
| **IA-04-01** | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | NA | |
| **IA-04-02** | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8: Aesthetic | NA | |
| **IA-04-03** | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5: Error Prev. | NA | |
| **IA-04-04** | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo; trạng thái vé thay đổi tương ứng khi được phê duyệt/hủy. | Nielsen #1: Visibility | Pass | |
| **IA-04-05** | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1: Visibility | Pass | |
| **IA-04-06** | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (Ví dụ: APPROVED màu xanh lá, REJECTED màu đỏ). | Nielsen #2: Match System | Pass | |
| **IA-04-07** | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1: Visibility | Pass | |
| **IA-04-08** | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7: Flexibility | NA | |
| **IA-04-09** | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | Fail | Không tự động cập nhật danh sách khi có thay đổi dữ liệu ở tab/thiết bị khác (Log USA-06). |
| **IA-04-10** | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | Fail | Màn hình D2 không hiển thị thông báo/toast khi ngắt kết nối mạng (Log USA-07). |
| **IA-04-11** | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | NA | |
| **IA-04-12** | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | NA | |
| **IA-04-13** | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | Pass | |
| **IA-04-14** | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, hoặc phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | NA | |

---

### 2.3. Bảng Thực thi trên Màn hình D2.2: Support Request Detail - User Side

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Verdict (Pass/Fail/NA) | Ghi Chú Lỗi (Notes) |
|:---:|:---:|:---|:---|:---:|:---|
| **IA-01-01** | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-02** | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4: Consistency | Pass | |
| **IA-01-03** | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | Pass | |
| **IA-01-04** | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | Pass | |
| **IA-01-05** | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1: Visibility | NA | Màn hình chi tiết chứa dữ liệu của request, không áp dụng danh sách rỗng. |
| **IA-01-06** | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1: Visibility | Pass | |
| **IA-01-07** | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-08** | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị (tỷ lệ 4:3 và 24:9) trên các kích thước màn hình khác nhau. | Shneiderman: Aesthetics | Pass | |
| **IA-01-09** | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman: Aesthetics | Fail | Icon calendar chỗ thời gian bị lệch so với text (Log USA-08). |
| **IA-01-10** | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4: Consistency | Pass | |
| **IA-01-11** | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3: User Control | Pass | |
| **IA-01-12** | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4: Consistency | NA | Màn hình chi tiết không sử dụng banner/thumbnail. |
| **IA-02-01** | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan (ví dụ dấu `*`). | Norman: Constraints | NA | Thao tác nhập liệu không áp dụng trên vé đã Resolved. |
| **IA-02-02** | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng và đi sát với ô nhập liệu. | Nielsen #6: Recognition | NA | Thao tác nhập liệu không áp dụng trên vé đã Resolved. |
| **IA-02-03** | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5: Error Prev. | NA | Thao tác nhập liệu không áp dụng trên vé đã Resolved. |
| **IA-02-04** | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục thay vì báo lỗi chung chung. | Nielsen #10: Help & Error | NA | Thao tác nhập liệu không áp dụng trên vé đã Resolved. |
| **IA-02-05** | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman: Constraints | NA | Thao tác nhập liệu không áp dụng trên vé đã Resolved. |
| **IA-02-06** | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ và hoạt động mượt mà. | Nielsen #7: Flexibility | NA | Khung nhập phản hồi sử dụng ô Textarea chuẩn, không dùng Rich Text. |
| **IA-02-07** | Forms | Người dùng có thể nhấn `Tab` để di chuyển tuần tự qua các ô nhập liệu trong form. | Nielsen #7: Flexibility | NA | Thao tác nhập liệu không áp dụng trên vé đã Resolved. |
| **IA-02-08** | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ. | Nielsen #5: Error Prev. | NA | Thao tác nhập liệu không áp dụng trên vé đã Resolved. |
| **IA-02-09** | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc đối với người dùng Việt Nam. | Nielsen #2: Match System | Pass | |
| **IA-02-10** | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3: User Control | NA | Màn hình chi tiết không có nút Reset form. |
| **IA-02-11** | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill) cho các trường thông tin cơ bản. | Nielsen #7: Flexibility | NA | Thao tác nhập liệu không áp dụng trên vé đã Resolved. |
| **IA-02-12** | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu trực quan bằng biểu tượng con mắt. | Nielsen #7: Flexibility | NA | Màn hình chi tiết không có trường nhập mật khẩu. |
| **IA-03-01** | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6: Recognition | Pass | |
| **IA-03-02** | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1: Visibility | NA | Tuyến đường chi tiết /complaints/18 là sub-page. |
| **IA-03-03** | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó, không mất trạng thái. | Nielsen #3: User Control | Pass | |
| **IA-03-04** | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết sự kiện mà không bị lỗi 404. | Nielsen #4: Consistency | Pass | |
| **IA-03-05** | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | Fail | Màn hình D2.2 không hiển thị dải điều hướng Breadcrumbs (Log USA-09). |
| **IA-03-06** | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | NA | Màn hình chi tiết không dùng chức năng reorder. |
| **IA-03-07** | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | NA | Màn hình chi tiết không dùng giao diện tab. |
| **IA-03-08** | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | Pass | |
| **IA-03-09** | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | Pass | |
| **IA-03-10** | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | NA | Màn hình dùng Header top navbar, không dùng sidebar. |
| **IA-03-11** | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | NA | Màn hình chi tiết không có bộ lọc/tab. |
| **IA-03-12** | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | NA | Màn hình không có giao diện reorder. |
| **IA-04-01** | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | NA | Không có thao tác gửi form trên vé đã Resolved. |
| **IA-04-02** | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8: Aesthetic | NA | |
| **IA-04-03** | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5: Error Prev. | NA | Phía Student không có nút Hủy/Xóa vé hỗ trợ. |
| **IA-04-04** | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo; trạng thái vé thay đổi tương ứng khi được phê duyệt/hủy. | Nielsen #1: Visibility | Pass | |
| **IA-04-05** | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1: Visibility | Pass | |
| **IA-04-06** | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (Ví dụ: APPROVED màu xanh lá, REJECTED màu đỏ). | Nielsen #2: Match System | Pass | |
| **IA-04-07** | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1: Visibility | Pass | |
| **IA-04-08** | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7: Flexibility | Pass | |
| **IA-04-09** | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | Fail | Không tự động nhận phản hồi mới từ Admin nếu không reload trang (Log USA-10). |
| **IA-04-10** | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | Fail | Màn hình D2.2 không hiển thị thông báo/toast khi ngắt kết nối mạng (Log USA-11). |
| **IA-04-11** | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | NA | Không có nút Submit trên vé đã Resolved. |
| **IA-04-12** | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | NA | Yêu cầu hỗ trợ không phát hành mã QR code. |
| **IA-04-13** | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | NA | Màn hình chi tiết vé Resolved không chứa ô nhập liệu. |
| **IA-04-14** | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, hoặc phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | NA | | 

---

### 2.4. Bảng Thực thi trên Màn hình D3: Support Requests List - Admin Side

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Verdict (Pass/Fail/NA) | Ghi Chú Lỗi (Notes) |
|:---:|:---:|:---|:---|:---:|:---|
| **IA-01-01** | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-02** | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4: Consistency | Pass | |
| **IA-01-03** | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | Pass | |
| **IA-01-04** | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | Pass | |
| **IA-01-05** | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1: Visibility | Pass | |
| **IA-01-06** | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1: Visibility | Pass | |
| **IA-01-07** | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-08** | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị (tỷ lệ 4:3 và 24:9) trên các kích thước màn hình khác nhau. | Shneiderman: Aesthetics | NA | Giao diện danh sách không chứa ảnh Banner/Thumbnail. |
| **IA-01-09** | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman: Aesthetics | Pass | |
| **IA-01-10** | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4: Consistency | Pass | |
| **IA-01-11** | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3: User Control | Pass | |
| **IA-01-12** | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4: Consistency | NA | Giao diện danh sách không sử dụng banner/thumbnail. |
| **IA-02-01** | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan (ví dụ dấu `*`). | Norman: Constraints | NA | Giao diện danh sách không chứa form nhập liệu bắt buộc. |
| **IA-02-02** | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng và đi sát với ô nhập liệu. | Nielsen #6: Recognition | Pass | |
| **IA-02-03** | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5: Error Prev. | NA | Ô tìm kiếm Admin chấp nhận mọi từ khóa nhập vào. |
| **IA-02-04** | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục thay vì báo lỗi chung chung. | Nielsen #10: Help & Error | NA | Không có khung báo lỗi trên thanh tìm kiếm filter. |
| **IA-02-05** | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman: Constraints | NA | Màn hình danh sách không dùng tính năng Upload file. |
| **IA-02-06** | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ và hoạt động mượt mà. | Nielsen #7: Flexibility | NA | Không sử dụng Rich Text trên màn hình danh sách Admin. |
| **IA-02-07** | Forms | Người dùng có thể nhấn `Tab` để di chuyển tuần tự qua các ô nhập liệu trong form. | Nielsen #7: Flexibility | Pass | |
| **IA-02-08** | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ. | Nielsen #5: Error Prev. | NA | Các ô filter tự động tìm kiếm, không áp dụng nút Submit form. |
| **IA-02-09** | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc đối với người dùng Việt Nam. | Nielsen #2: Match System | Pass | |
| **IA-02-10** | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3: User Control | Pass | |
| **IA-02-11** | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill) cho các trường thông tin cơ bản. | Nielsen #7: Flexibility | NA | Thanh filter tìm kiếm không yêu cầu autofill. |
| **IA-02-12** | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu trực quan bằng biểu tượng con mắt. | Nielsen #7: Flexibility | NA | Màn hình danh sách không chứa trường mật khẩu. |
| **IA-03-01** | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6: Recognition | Pass | |
| **IA-03-02** | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1: Visibility | Pass | |
| **IA-03-03** | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó, không mất trạng thái. | Nielsen #3: User Control | Pass | |
| **IA-03-04** | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết sự kiện mà không bị lỗi 404. | Nielsen #4: Consistency | Pass | |
| **IA-03-05** | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | Fail | Màn hình D3 không hiển thị dải điều hướng Breadcrumbs (Log USA-13). |
| **IA-03-06** | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | NA | Màn hình danh sách Admin không dùng giao diện kéo thả reorder. |
| **IA-03-07** | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | Pass | |
| **IA-03-08** | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | Pass | |
| **IA-03-09** | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | Pass | |
| **IA-03-10** | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | Pass | |
| **IA-03-11** | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | Pass | |
| **IA-03-12** | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | NA | Màn hình không có giao diện reorder. |
| **IA-04-01** | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | NA | Giao diện danh sách Admin không áp dụng thao tác gửi form. |
| **IA-04-02** | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8: Aesthetic | NA | không phát sinh toast trên màn hình danh sách Admin. |
| **IA-04-03** | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5: Error Prev. | NA | Không có thao tác hủy/xóa trực tiếp trên danh sách Admin. |
| **IA-04-04** | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo; trạng thái vé thay đổi tương ứng khi được phê duyệt/hủy. | Nielsen #1: Visibility | Pass | |
| **IA-04-05** | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1: Visibility | Pass | |
| **IA-04-06** | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (Ví dụ: APPROVED màu xanh lá, REJECTED màu đỏ). | Nielsen #2: Match System | Pass | |
| **IA-04-07** | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1: Visibility | Pass | |
| **IA-04-08** | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7: Flexibility | NA | Ảnh đính kèm được xem ở màn hình chi tiết D4. |
| **IA-04-09** | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | Fail | Không tự động cập nhật danh sách Admin khi có sinh viên tạo yêu cầu mới (Log USA-14). |
| **IA-04-10** | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | Fail | Màn hình D3 không hiển thị thông báo/toast khi ngắt kết nối mạng (Log USA-15). |
| **IA-04-11** | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | NA | Giao diện danh sách không có nút Submit. |
| **IA-04-12** | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | NA | Yêu cầu hỗ trợ không phát hành mã QR code. |
| **IA-04-13** | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | Pass | |
| **IA-04-14** | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, hoặc phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | NA | |


---

### 2.5. Bảng Thực thi trên Màn hình D4: Support Request Detail - Admin Side

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Verdict (Pass/Fail/NA) | Ghi Chú Lỗi (Notes) |
|:---:|:---:|:---|:---|:---:|:---|
| **IA-01-01** | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-02** | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4: Consistency | Pass | |
| **IA-01-03** | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | Pass | |
| **IA-01-04** | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | Pass | |
| **IA-01-05** | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1: Visibility | NA | |
| **IA-01-06** | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1: Visibility | Pass | |
| **IA-01-07** | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4: Consistency | Pass | |
| **IA-01-08** | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị (tỷ lệ 4:3 và 24:9) trên các kích thước màn hình khác nhau. | Shneiderman: Aesthetics | NA | |
| **IA-01-09** | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman: Aesthetics | Pass | |
| **IA-01-10** | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4: Consistency | Pass | |
| **IA-01-11** | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3: User Control | Pass | |
| **IA-01-12** | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4: Consistency | NA | |
| **IA-02-01** | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan (ví dụ dấu `*`). | Norman: Constraints | Fail | Trường nội dung phản hồi bắt nhập nhưng không có dấu * (Log USA-16). |
| **IA-02-02** | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng và đi sát với ô nhập liệu. | Nielsen #6: Recognition | Pass | |
| **IA-02-03** | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5: Error Prev. | Fail | Lỗi hiện ở đầu screen chứ không ngay dưới ô nhập (Log USA-17). |
| **IA-02-04** | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục thay vì báo lỗi chung chung. | Nielsen #10: Help & Error | Pass | |
| **IA-02-05** | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman: Constraints | NA | |
| **IA-02-06** | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ và hoạt động mượt mà. | Nielsen #7: Flexibility | NA | |
| **IA-02-07** | Forms | Người dùng có thể nhấn `Tab` để di chuyển tuần tự qua các ô nhập liệu trong form. | Nielsen #7: Flexibility | Pass | |
| **IA-02-08** | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ. | Nielsen #5: Error Prev. | Fail | Vẫn có thể submit khi chưa điền thông tin cần thiết (Log BUG-03). |
| **IA-02-09** | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc đối với người dùng Việt Nam. | Nielsen #2: Match System | Pass | |
| **IA-02-10** | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3: User Control | NA | |
| **IA-02-11** | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill) cho các trường thông tin cơ bản. | Nielsen #7: Flexibility | NA | |
| **IA-02-12** | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu trực quan bằng biểu tượng con mắt. | Nielsen #7: Flexibility | NA | |
| **IA-03-01** | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6: Recognition | Pass | |
| **IA-03-02** | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1: Visibility | Pass | |
| **IA-03-03** | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó, không mất trạng thái. | Nielsen #3: User Control | Pass | |
| **IA-03-04** | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết sự kiện mà không bị lỗi 404. | Nielsen #4: Consistency | NA | |
| **IA-03-05** | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | Fail | Không có breadcrumbs (Log USA-18). |
| **IA-03-06** | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | NA | |
| **IA-03-07** | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | NA | |
| **IA-03-08** | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | NA | |
| **IA-03-09** | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | NA | |
| **IA-03-10** | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | Pass | |
| **IA-03-11** | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | Pass | |
| **IA-03-12** | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | NA | |
| **IA-04-01** | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | Fail | Thông báo không phải dạng toast (Log USA-19). |
| **IA-04-02** | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8: Aesthetic | NA | |
| **IA-04-03** | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5: Error Prev. | NA | |
| **IA-04-04** | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo; trạng thái vé thay đổi tương ứng khi được phê duyệt/hủy. | Nielsen #1: Visibility | Pass | |
| **IA-04-05** | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1: Visibility | Pass | |
| **IA-04-06** | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (Ví dụ: APPROVED màu xanh lá, REJECTED màu đỏ). | Nielsen #2: Match System | Pass | |
| **IA-04-07** | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1: Visibility | NA | |
| **IA-04-08** | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7: Flexibility | Pass | |
| **IA-04-09** | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | Pass | |
| **IA-04-10** | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | Fail | Màn hình D4 không hiển thị thông báo/toast khi ngắt kết nối mạng (Log USA-20). |
| **IA-04-11** | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | Pass | |
| **IA-04-12** | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | NA | |
| **IA-04-13** | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | Pass | |
| **IA-04-14** | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, hoặc phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | NA | |

---

## 3. Task 2: User Testing with 5 Real Users → Usability Report

### 3.1. Kịch bản Kiểm thử Người dùng (Task Scenario Design)
- **Bối cảnh & Mục tiêu Kịch bản (Scenario D - Support Requests):** Xây dựng kịch bản kiểm thử nhập vai theo mục tiêu (Goal-oriented task) tập trung vào luồng Giao diện User.
- **Quy trình kịch bản chi tiết (Luồng User):** Đăng nhập tài khoản Sinh viên/Khách $\rightarrow$ Truy cập **Màn hình Tạo Yêu cầu Hỗ trợ (Screen D1)** để tạo 1 Yêu cầu Hỗ trợ (có thể kèm ảnh đính kèm minh chứng lỗi) $\rightarrow$ Theo dõi danh sách trạng thái các yêu cầu tại **Màn hình Danh sách Yêu cầu Hỗ trợ (Screen D2.1)** $\rightarrow$ Mở xem nội dung chi tiết tại **Màn hình Chi tiết Yêu cầu Hỗ trợ (Screen D2.2)** để kiểm tra thông tin và kết quả phản hồi.
- **Các chỉ số đo lường (Metrics to Measure):**

  - **Mức độ hoàn thành tác vụ (Task Success Rate):** Completed (Hoàn thành), Partial (Hoàn thành một phần), Failed (Thất bại).
  - **Thời gian hoàn thành tác vụ (Time on Task):** Đo bằng phút / giây từ lúc bắt đầu cho tới khi hoàn tất mục tiêu.
  - **Tần suất lỗi / Khập khiễng (Error / Hesitation Count):** Thống kê số lần nhấp chuột sai vị trí, thao tác thừa hoặc ngập ngừng trên giao diện.
  - **Điểm đánh giá trải nghiệm SUS (System Usability Scale) / UEQ-S (User Experience Questionnaire Short):** Khảo sát chuẩn hóa 10 câu hỏi SUS sau khi thực hiện kịch bản.
  - **Câu hỏi phỏng vấn mở (Open-ended Probe Questions):** Đánh giá cảm nhận về độ rõ ràng, tốc độ xử lý và mức độ tin cậy.

#### 3.1.1. Bộ Câu Hỏi Khảo Sát Trải Nghiệm Chuẩn Hóa SUS (System Usability Scale - 10 Items)
*Được khảo sát ngay sau khi người tham gia hoàn tất kịch bản kiểm thử trên thang đo Likert 5 điểm (1: Hoàn toàn không đồng ý $\rightarrow$ 5: Hoàn toàn đồng ý).*

| STT | Loại phát biểu | Nội dung Câu hỏi Khảo sát SUS | Thang điểm |
|---|---|---|---|
| **Q1** | Tích cực | Tôi nghĩ rằng tôi sẽ muốn sử dụng hệ thống này thường xuyên khi cần gửi yêu cầu hỗ trợ. | 1 – 2 – 3 – 4 – 5 |
| **Q2** | Tiêu cực | Tôi thấy giao diện và quy trình gửi hỗ trợ của hệ thống này phức tạp một cách không cần thiết. | 1 – 2 – 3 – 4 – 5 |
| **Q3** | Tích cực | Tôi nghĩ hệ thống này dễ sử dụng và thân thiện với người dùng. | 1 – 2 – 3 – 4 – 5 |
| **Q4** | Tiêu cực | Tôi nghĩ rằng tôi sẽ cần sự hỗ trợ của kỹ thuật viên/người hướng dẫn để có thể sử dụng hệ thống này. | 1 – 2 – 3 – 4 – 5 |
| **Q5** | Tích cực | Tôi thấy các chức năng trong hệ thống này (tạo yêu cầu hỗ trợ, đính kèm ảnh, theo dõi trạng thái) được tích hợp rất tốt. | 1 – 2 – 3 – 4 – 5 |
| **Q6** | Tiêu cực | Tôi nghĩ rằng có quá nhiều sự không thống nhất về giao diện/icon/thông báo trong hệ thống này. | 1 – 2 – 3 – 4 – 5 |
| **Q7** | Tích cực | Tôi tưởng tượng rằng hầu hết mọi người sẽ học cách sử dụng hệ thống này rất nhanh chóng. | 1 – 2 – 3 – 4 – 5 |
| **Q8** | Tiêu cực | Tôi thấy giao diện hệ thống này rất cồng kềnh và rườm rà khi thao tác. | 1 – 2 – 3 – 4 – 5 |
| **Q9** | Tích cực | Tôi cảm thấy rất tự tin và chủ động khi thao tác trên hệ thống này. | 1 – 2 – 3 – 4 – 5 |
| **Q10** | Tiêu cực | Tôi cần phải học/đọc hiểu rất nhiều điều trước khi có thể bắt đầu sử dụng thành thạo hệ thống này. | 1 – 2 – 3 – 4 – 5 |

- **Quy tắc Tính Điểm SUS (SUS Score Calculation Formula):**
  - Đối với các câu hỏi **số lẻ (Q1, Q3, Q5, Q7, Q9 - Tích cực)**: $\text{Điểm thành phần} = \text{Điểm đánh giá (1-5)} - 1$.
  - Đối với các câu hỏi **số cặp (Q2, Q4, Q6, Q8, Q10 - Tiêu cực)**: $\text{Điểm thành phần} = 5 - \text{Điểm đánh giá (1-5)}$.
  - **Điểm tổng SUS cá nhân** $= (\sum_{i=1}^{10} \text{Điểm thành phần}_i) \times 2.5$ (Quy đổi ra thang điểm từ 0 đến 100).
  - **Đánh giá điểm SUS:** Mức chuẩn trung bình ngành là **68/100** ($>68$: Above Average / Dễ sử dụng; $<68$: Below Average / Cần cải tiến gấp).

#### 3.1.2. Danh Sách Câu Hỏi Phỏng Vấn Đào Sâu Trải Nghiệm (Open-ended Probe Questions)
*Được người kiểm thử (Facilitator) sử dụng để phỏng vấn đào sâu ngay sau khi người tham gia hoàn tất kịch bản kiểm thử nhằm ghi nhận chi tiết các điểm nghẽn trải nghiệm (Friction Points).*

| Mã PQ | Mục tiêu Phỏng vấn | Nội dung Câu hỏi Phỏng vấn Đào sâu (Open-ended Probe Questions) |
|---|---|---|
| **PQ1** | Ấn tượng ban đầu & Nhận diện Giao diện | *"Khi lần đầu mở Màn hình Tạo Yêu cầu hỗ trợ, bạn thấy các nhãn và ô nhập liệu có rõ ràng không? Có thông tin nào khiến bạn bối rối hoặc ngập ngừng không?"* |
| **PQ2** | Thao tác Đính kèm Ảnh minh chứng | *"Thao tác chọn tệp và đính kèm hình ảnh minh chứng lỗi diễn ra như thế nào? Bạn có gặp khó khăn hoặc thắc mắc gì về định dạng/dung lượng ảnh được phép không?"* |
| **PQ3** | Trực quan hóa Trạng thái & Phản hồi | *"Khi theo dõi Danh sách yêu cầu và xem Chi tiết yêu cầu, bạn có dễ dàng nhận biết trạng thái xử lý (Đã xử lý, Từ chối, Đang xử lý) không? Thông báo phản hồi có đủ rõ ràng không?"* |
| **PQ4** | Khả năng Tự khắc phục Lỗi & Cảnh báo | *"Nếu bạn nhập thiếu thông tin hoặc gặp sự cố ngắt kết nối mạng, hệ thống có hiển thị cảnh báo/hướng dẫn rõ ràng giúp bạn tự khắc phục không?"* |
| **PQ5** | Đề xuất Cải tiến Trải nghiệm từ Người dùng | *"Nếu được thay đổi hoặc bổ sung 1 điểm duy nhất ở quy trình này để giúp việc gửi và theo dõi yêu cầu hỗ trợ thuận tiện hơn, bạn sẽ đề xuất điều gì?"* |

### 3.2. Danh sách 5 Người tham gia Kiểm thử (Participant Recruitment Table)



| STT | Họ và Tên | Vai trò Target Profile | Email / Zalo / SĐT (Masked) |
|---|---|---|---|
| 1 | Participant 1 | Student | `participant1@****.edu.vn` / `090****123` |
| 2 | Participant 2 | Student | `participant2@****.edu.vn` / `091****456` |
| 3 | Participant 3 | Student | `participant3@****.edu.vn` / `098****789` |
| 4 | Participant 4 | Event-goer / Guest | `participant4@****.com` / `093****321` |
| 5 | Participant 5 | Student / User | `participant5@****.edu.vn` / `097****654` |

### 3.3. Bảng Kết quả Thu thập Chỉ số Kiểm thử (Execution Metrics Table)

| Người tham gia | Trạng thái (Task Success Rate) | Thời gian hoàn thành (Time on Task) | Số lỗi / Ngập ngừng (Errors / Hesitations) | Điểm SUS / UEQ-S | Ghi chú phản hồi / Điểm nghẽn (Friction Points) |
|---|---|---|---|---|---|
| Participant 1 | *TBD* | *TBD* | *TBD* | *TBD* | *TBD* |
| Participant 2 | *TBD* | *TBD* | *TBD* | *TBD* | *TBD* |
| Participant 3 | *TBD* | *TBD* | *TBD* | *TBD* | *TBD* |
| Participant 4 | *TBD* | *TBD* | *TBD* | *TBD* | *TBD* |
| Participant 5 | *TBD* | *TBD* | *TBD* | *TBD* | *TBD* |
| **Trung bình (Mean)** | **TBD%** | **TBD** | **TBD** | **TBD / 100** |  |

### 3.4. Phân tích Phản hồi Usability & Đề xuất Cải tiến (Usability Findings & Recommendations)
- **Phân loại vấn đề & Thang điểm Severity (0–4):** Nhóm các điểm nghẽn trải nghiệm, phân định lỗi isolated bugs với lỗi systemic design issues.

| ID phát hiện | Màn hình vi phạm | Mô tả điểm nghẽn Usability | Severity (0–4) | Đề xuất cải tiến (Actionable Recommendation) |
|---|---|---|---|---|
| *TBD* | *TBD* | *TBD* | *TBD* | *TBD* |


---

## 4. Task 3: Cross-Browser / Cross-Platform Testing Matrix

### 4.1. Khung Chiến lược Ma trận Tương thích (Compatibility Strategy)
- **Phạm vi bao phủ bắt buộc (Coverage Required):**
  - **3 Operating Systems:** e.g., Windows, macOS, and Android or iOS.
  - **5 Browsers:** e.g., Chrome, Firefox, Safari, Edge, and Opera (or Samsung Internet on mobile).
  - **3 Device Classes:** desktop, tablet, and phone.
- **Công cụ kiểm thử:** BrowserStack / Real Physical Devices.

### 4.2. Bảng Ma trận Tương thích Cross-Browser / Cross-Platform (Compatibility Matrix Tables)

#### 4.2.1. Màn hình D1 - Tạo Yêu cầu Hỗ trợ (`/complaints/new`)

| STT | Hệ điều hành (OS) | Trình duyệt (Browser) | Lớp thiết bị (Device Class) | Verdict (Pass/Fail) | Ảnh minh chứng | Ghi chú Lỗi Giao diện / Layout Fail |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1KMeCHfO80ArbsVb7df72WwJbH4Rq14F8/view?usp=drive_link) | Không lỗi |
| 2 | Windows | Edge | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/14o9XuV73tnGqtU38DOFor-s2z5B3EAlR/view?usp=drive_link) | Không lỗi |
| 3 | Windows | Firefox | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1QlmeqXf6lAkdpfltq6zAYbWHJajQcV6b/view?usp=drive_link) | Không lỗi |
| 4 | macOS | Safari | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1hM9SGifHIy1ejAnCvwRqgaUdxNGIKkwE/view?usp=drive_link) | Không lỗi |
| 5 | Windows | Opera | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/155Fh3-SNKd-sFja5f_lhNVbZxfQcy-Zs/view?usp=drive_link) | Không lỗi |
| 6 | Android | Chrome | tablet | Pass | [PNG Ref](https://drive.google.com/file/d/1Wu9w-Bgrahi7CC3Eoay8ZWEMJiOcmQsZ/view?usp=drive_link) | Không lỗi |
| 7 | iOS | Safari | phone | Pass | [PNG Ref](https://drive.google.com/file/d/1OaW3HHpYNzohAimWqd10RtFWFbPEMkDP/view?usp=drive_link) | Không lỗi |

#### 4.2.2. Màn hình D2.1 - Danh sách Yêu cầu Hỗ trợ (`/complaints`)

| STT | Hệ điều hành (OS) | Trình duyệt (Browser) | Lớp thiết bị (Device Class) | Verdict (Pass/Fail) | Ảnh minh chứng | Ghi chú Lỗi Giao diện / Layout Fail |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1jjIZTmkloezcMcCW1dUr-YfgFlOB5fFF/view?usp=drive_link) | Không lỗi |
| 2 | Windows | Edge | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1KwbKUP64Fbo3ydu1s8If5zLLmMXpO4Cn/view?usp=drive_link) | Không lỗi |
| 3 | Windows | Firefox | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/13x9UTdujtNWyaktP_wp1mom5W7nhAgkK/view?usp=drive_link) | Không lỗi |
| 4 | macOS | Safari | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1T1gd2O0NxKC8deMzuJAsY04LrON68fow/view?usp=drive_link) | Không lỗi |
| 5 | Windows | Opera | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1Y5orviLFszNPenNU7J3fsaHB6EPpHtq1/view?usp=drive_link) | Không lỗi |
| 6 | Android | Chrome | tablet | Pass | [PNG Ref](https://drive.google.com/file/d/1fO5BENZh_T-DV5AHXDa7etRHldlGLmyu/view?usp=drive_link) | Không lỗi |
| 7 | iOS | Safari | phone | Pass | [PNG Ref](https://drive.google.com/file/d/1rhVo9ZZk5rF1eB82-zq0kiHpyOSdZnid/view?usp=drive_link) | Không lỗi |

#### 4.2.3. Màn hình D2.2 - Chi tiết Yêu cầu Hỗ trợ (`/complaints/[id]`)

| STT | Hệ điều hành (OS) | Trình duyệt (Browser) | Lớp thiết bị (Device Class) | Verdict (Pass/Fail) | Ảnh minh chứng | Ghi chú Lỗi Giao diện / Layout Fail |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1fMyoNUfxBF0bTkM8QAD_suHV6aIx4kly/view?usp=drive_link) | Không lỗi |
| 2 | Windows | Edge | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1LKcE3HUl8ExmCWOAv9Dx1MvdRLCy225E/view?usp=drive_link) | Không lỗi |
| 3 | Windows | Firefox | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1yhHXlTojYoZA1z9VG6j4ftzq2FnrYN5d/view?usp=drive_link) | Không lỗi |
| 4 | macOS | Safari | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/168AuTdTGuPjgdJhraoKeoXduF0Hv37tP/view?usp=drive_link) | Không lỗi |
| 5 | Windows | Opera | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1neHcWGaI_z7gJnaUZcznYoO102fJ2jpS/view?usp=drive_link) | Không lỗi |
| 6 | Android | Chrome | tablet | Pass | [PNG Ref](https://drive.google.com/file/d/1DrrDOw4UnoN7t5rtRIGtxG3OC0XQAIq4/view?usp=drive_link) | Không lỗi |
| 7 | iOS | Safari | phone | Pass | [PNG Ref](https://drive.google.com/file/d/1V8tOY_iqupn44bhSxvikTMf9dZUp1leZ/view?usp=drive_link) | Không lỗi |

#### 4.2.4. Màn hình D3 - Danh sách Yêu cầu Hỗ trợ Quản trị viên (`/dashboard/admin/complaints`)

| STT | Hệ điều hành (OS) | Trình duyệt (Browser) | Lớp thiết bị (Device Class) | Verdict (Pass/Fail) | Ảnh minh chứng | Ghi chú Lỗi Giao diện / Layout Fail |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1rJyFLqqPVjfr7ggZEbhFg3WlysydsNbN/view?usp=drive_link) | Không lỗi |
| 2 | Windows | Edge | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1Y2s2N2gSQ9JIVU220Gmvx3rypY2sq6qy/view?usp=drive_link) | Không lỗi |
| 3 | Windows | Firefox | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1_AzMG0ymROXZj3dOJTq7b-sqFHj6a4B1/view?usp=drive_link) | Không lỗi |
| 4 | macOS | Safari | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1J1WDNrZm_2uBq0K-L3WvecTZTKIHkeiP/view?usp=drive_link) | Không lỗi |
| 5 | Windows | Opera | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1N0y29y6ktQlguFzZTNQ_qqH9KLdkfPfx/view?usp=drive_link) | Không lỗi |
| 6 | Android | Chrome | tablet | Pass | [PNG Ref](https://drive.google.com/file/d/1Si6NSAmYoOATpPVkgB29uGMbXJ8Q27cC/view?usp=drive_link) | Không lỗi |
| 7 | iOS | Safari | phone | Fail | [PNG Ref](https://drive.google.com/file/d/1oJGHvSSarInGs8p2pBB0v2kFMOLZoqUV/view?usp=drive_link) | Thanh sidebar chèn làm lỗi layout của trang, rút gọn lại thì mới nhìn bình thường |

#### 4.2.5. Màn hình D4 - Chi tiết Yêu cầu Hỗ trợ Quản trị viên (`/dashboard/admin/complaints/[id]`)

| STT | Hệ điều hành (OS) | Trình duyệt (Browser) | Lớp thiết bị (Device Class) | Verdict (Pass/Fail) | Ảnh minh chứng | Ghi chú Lỗi Giao diện / Layout Fail |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1pQ_UD9I1whflxhrsAARfqwJ1H7ZTCoMl/view?usp=drive_link) | Không lỗi |
| 2 | Windows | Edge | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1-2NbeB6Lm5-MX8C4JpePWKY4ZjGZbsE8/view?usp=drive_link) | Không lỗi |
| 3 | Windows | Firefox | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1_GZhDddEWKKZN4xWGTv4j39BQBpAG_tr/view?usp=drive_link) | Không lỗi |
| 4 | macOS | Safari | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1Rm8ShvXYRAJENfSr2xxOxEPZL8SqbQMK/view?usp=drive_link) | Không lỗi |
| 5 | Windows | Opera | desktop | Pass | [PNG Ref](https://drive.google.com/file/d/1-seJ8CDKMr3GkCNjRye1egTo1w4ESqwn/view?usp=drive_link) | Không lỗi |
| 6 | Android | Chrome | tablet | Pass | [PNG Ref](https://drive.google.com/file/d/1GKWKnVIj9s9YPrxs0Ue_l4d49QHN-0HO/view?usp=drive_link) | Không lỗi |
| 7 | iOS | Safari | phone | Fail | [PNG Ref](https://drive.google.com/file/d/1_kPijl5-YzTqaUat78yK_7ZtrCpsAfmi/view?usp=drive_link) | Thanh sidebar chèn làm lỗi layout của trang, rút gọn lại thì mới nhìn bình thường |
