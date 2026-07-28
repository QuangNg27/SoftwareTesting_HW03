# BÁO CÁO GUI & Usability Testing on EMS (Event Management System)

* **Môn học:** Kiểm thử Phần mềm
* **Sinh viên:** Nguyễn Minh Quang - 23127462
* **Hệ thống kiểm thử (SUT):** EMS (Event Management System) - https://promoter-starboard-prude.ngrok-free.dev/
* **Kịch bản lựa chọn (Chosen Scenario):** **Scenario D — User requests Support and Admin resolves it**

---

## 1. TỔNG QUAN VỀ PHẠM VI KIỂM THỬ

### 1.1. Lý do Lựa chọn Kịch bản
Trong bài tập HW03, **Scenario D — User requests Support and Admin resolves it** được lựa chọn với phạm vi tập trung chuyên sâu vào **Giao diện Người dùng (User Side)**.

Kịch bản này bao phủ trọn vẹn luồng nghiệp vụ của người dùng sinh viên khi gặp sự cố trên hệ thống EMS: từ khâu khởi tạo phiếu hỗ trợ (Support Ticket) mới, chọn loại yêu cầu, tải tệp đính kèm minh chứng lỗi, đến khâu quản lý danh sách các phiếu hỗ trợ cá nhân, theo dõi dòng thời gian xử lý và xem phản hồi chính thức từ nhà trường trực tiếp trên giao diện người dùng.

### 1.2. Danh sách 3 Màn hình Kiểm thử được Lựa chọn
Để đảm bảo tính rõ ràng, tách bạch giữa giao diện Danh sách (List) và giao diện Chi tiết (Detail), 3 màn hình của User được đưa vào phạm vi kiểm thử:

| STT | Mã Màn hình | Tên Màn hình (Screen Name) | Vai trò & Phạm vi Nghiệp vụ | Interface aspects |
| :---: | :---: | :--- | :--- | :--- |
| 1 | **D1** | **Create Support Request Form** | Màn hình Form cho người dùng tạo yêu cầu hỗ trợ mới: chọn danh mục sự cố, nhập nội dung chi tiết, tải lên tệp ảnh minh chứng. | **IA-02** (Forms, Uploads, RichText) & **IA-01** (Layout, i18n) |
| 2 | **D2.1** | **My Support Requests List** | Màn hình danh sách các yêu cầu hỗ trợ cá nhân của người dùng: phân trang, lọc theo trạng thái (`Pending` / `Resolved`), hiển thị tóm tắt ticket. | **IA-03** (Navigation, Tabs, Filters) & **IA-04** (Badges, Status Colours) |
| 3 | **D2.2** | **Support Request Detail (User Side)** | Màn hình xem chi tiết một yêu cầu hỗ trợ cá nhân: theo dõi dòng thời gian xử lý, xem phản hồi chính thức từ Admin và tệp đính kèm. | **IA-04** (Feedback, Timeline, Lightbox) & **IA-01** (Typography, Consistency) |

---

## 2. KHUNG THỰC THI CHECKLIST TRÊN CÁC MÀN HÌNH SCENARIO D (CHECKLIST EXECUTION)

Dưới đây là Khung kiểm thử (Execution Tables) sẵn sàng cho việc thực thi kiểm thử trực tiếp trên 3 màn hình của **Scenario D**. Cấu trúc bảng của từng màn hình bao gồm các cột chuẩn: **ID**, **Khía Cạnh**, **Mục Kiểm Tra**, **Ánh Xạ Heuristics**, **Verdict (Pass/Fail/NA)** và **Ghi Chú (Notes)**.

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

---

### 2.2. Bảng Thực thi trên Màn hình D2.1: My Support Requests List

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Verdict (Pass/Fail/NA) | Ghi Chú Lỗi (Notes) |
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
| **IA-03-05** | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | Fail | Không có breadcrumbs |
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
| **IA-04-09** | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | Fail | Tạo yêu cầu ở tab khác và quan sát tab của screen thì không thấy sự thay đổi |
| **IA-04-10** | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | Fail | |
| **IA-04-11** | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | NA | |
| **IA-04-12** | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | NA | |

---

### 2.3. Bảng Thực thi trên Màn hình D2.2: Support Request Detail - User Side

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Verdict (Pass/Fail/NA) | Ghi Chú Lỗi (Notes) |
|:---:|:---:|:---|:---|:---:|:---|
| **IA-01-01** | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4: Consistency | | |
| **IA-01-02** | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4: Consistency | | |
| **IA-01-03** | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | | |
| **IA-01-04** | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | | |
| **IA-01-05** | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1: Visibility | | |
| **IA-01-06** | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1: Visibility | | |
| **IA-01-07** | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4: Consistency | | |
| **IA-01-08** | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị (tỷ lệ 4:3 và 24:9) trên các kích thước màn hình khác nhau. | Shneiderman: Aesthetics | | |
| **IA-01-09** | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman: Aesthetics | | |
| **IA-01-10** | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4: Consistency | | |
| **IA-01-11** | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3: User Control | | |
| **IA-01-12** | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4: Consistency | | |
| **IA-02-01** | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan (ví dụ dấu `*`). | Norman: Constraints | | |
| **IA-02-02** | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng và đi sát với ô nhập liệu. | Nielsen #6: Recognition | | |
| **IA-02-03** | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5: Error Prev. | | |
| **IA-02-04** | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục thay vì báo lỗi chung chung. | Nielsen #10: Help & Error | | |
| **IA-02-05** | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman: Constraints | | |
| **IA-02-06** | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ và hoạt động mượt mà. | Nielsen #7: Flexibility | | |
| **IA-02-07** | Forms | Người dùng có thể nhấn `Tab` để di chuyển tuần tự qua các ô nhập liệu trong form. | Nielsen #7: Flexibility | | |
| **IA-02-08** | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ. | Nielsen #5: Error Prev. | | |
| **IA-02-09** | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc đối với người dùng Việt Nam. | Nielsen #2: Match System | | |
| **IA-02-10** | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3: User Control | | |
| **IA-02-11** | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill) cho các trường thông tin cơ bản. | Nielsen #7: Flexibility | | |
| **IA-02-12** | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu trực quan bằng biểu tượng con mắt. | Nielsen #7: Flexibility | | |
| **IA-03-01** | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6: Recognition | | |
| **IA-03-02** | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1: Visibility | | |
| **IA-03-03** | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó, không mất trạng thái. | Nielsen #3: User Control | | |
| **IA-03-04** | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết sự kiện mà không bị lỗi 404. | Nielsen #4: Consistency | | |
| **IA-03-05** | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | | |
| **IA-03-06** | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | | |
| **IA-03-07** | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | | |
| **IA-03-08** | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | | |
| **IA-03-09** | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | | |
| **IA-03-10** | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | | |
| **IA-03-11** | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | | |
| **IA-03-12** | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | | |
| **IA-04-01** | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | | |
| **IA-04-02** | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8: Aesthetic | | |
| **IA-04-03** | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5: Error Prev. | | |
| **IA-04-04** | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo; trạng thái vé thay đổi tương ứng khi được phê duyệt/hủy. | Nielsen #1: Visibility | | |
| **IA-04-05** | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1: Visibility | | |
| **IA-04-06** | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (Ví dụ: APPROVED màu xanh lá, REJECTED màu đỏ). | Nielsen #2: Match System | | |
| **IA-04-07** | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1: Visibility | | |
| **IA-04-08** | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7: Flexibility | | |
| **IA-04-09** | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | | |
| **IA-04-10** | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | | |
| **IA-04-11** | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | | |
| **IA-04-12** | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | | |
| **IA-04-13** | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | | |

---

## 4. CÁC BƯỚC TIẾP THEO (NEXT STEPS FOR COMPLETION)
1. **Thực thi Checklist trên SUT:** Tiến hành truy cập `https://promoter-starboard-prude.ngrok-free.dev/` để kiểm thử từng mục checklist trên 5 màn hình D1, D2, D3, D4, D5; cập nhật `Passed` / `Failed` / `NA` vào cột Verdict và điền nguyên nhân lỗi vào cột Notes.
2. **Ghi nhận Báo cáo Lỗi (Bug Reporting):** Điền các lỗi `Failed` tìm được vào [bug_report.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/bug_report.md) và submit lên Google Form.
3. **Thực hiện Task 2 (Usability Testing with 5 Users):** Thiết lập kịch bản thử nghiệm khả năng sử dụng trên Scenario D, mời 5 người dùng thử nghiệm, đo đạc chỉ số SUS/UEQ-S và viết Usability Report.
4. **Thực hiện Task 3 (Cross-Browser / Cross-Platform Matrix):** Thử nghiệm 5 màn hình trên 3 OS $\times$ 5 Browsers $\times$ 3 Device Classes, chụp ảnh minh chứng overlay email sinh viên.
