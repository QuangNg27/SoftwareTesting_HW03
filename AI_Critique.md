# Báo cáo Phản biện & Phản tư Tương tác AI - HW03 EMS

### 1. AI đã mắc sai sót, thiên vị hoặc thiếu sót ở những đâu?
AI đã bộc lộ ba dạng sai sót chính:
- **Ảo giác thị giác (Visual Hallucinations):** Ở Tác vụ 11, AI đánh giá sai tiêu chí IA-02-01 thành Fail khi cho rằng các nhãn form thiếu dấu * màu đỏ, trong khi thực tế trên giao diện SUT live các dấu * hiển thị rất rõ ràng.
- **Tiền giả định kiến trúc quá đà:** Ở các Tác vụ 4, 30 và 31, AI đã tự ý gộp chung các màn hình riêng biệt (Màn hình D2 Danh sách & Chi tiết) và tự điền kết quả kiểm thử trước khi thực sự chạy test.
- **Phân loại sai bản chất lỗi:** Ở Tác vụ 59, AI đã phân loại nhầm một lỗi chức năng điều hướng nghiêm trọng (Load thông báo bị lỗi) thành lỗi usability nhẹ thay vì lỗi hệ thống (System Bug).

---

### 2. Tại sao AI lại không phát hiện hoặc mắc phải các lỗi này?
- **Thiếu khả năng cảm nhận thị giác thực tế:** AI hoạt động dựa trên cây DOM và chuỗi văn bản thay vì quan sát hình ảnh hiển thị thực tế, dẫn đến các điểm mù về mặt thẩm mỹ và bố cục giao diện.
- **Thiên kiến hoàn thành vội vã (Eager Completion Bias):** AI ưu tiên xử lý nhanh câu lệnh bằng cách điền sẵn khung mẫu, lầm tưởng việc tạo văn bản đồng nghĩa với việc đã thực thi kiểm thử thực tế.
- **Áp dụng quy tắc cứng nhắc:** AI gặp khó khăn với các ngoại lệ theo ngữ cảnh, chẳng hạn như cấm tuyệt đối việc thu nhỏ màn hình mà bỏ sót ngoại lệ bắt buộc khi kiểm thử giao diện tương thích responsive (IA-01-07).

---

### 3. Nguyên tắc cốt lõi rút ra khi hợp tác với AI
Nguyên tắc quan trọng nhất rút ra là **"Giám sát trực tiếp (Human-in-the-Loop) thay vì tin tưởng mù quáng."** AI là công cụ tăng tốc mạnh mẽ cho việc thực thi nhanh, tạo khung báo cáo và rà soát checklist. Tuy nhiên, tư duy phản biện của con người là bắt buộc để xác minh thực nghiệm, chẩn đoán nguyên nhân gốc rễ và kiểm soát chất lượng. Việc kết hợp quy trình SOP rõ ràng trong các Kỹ năng Agent (Agent Skills) với sự giám sát chặt chẽ của con người sẽ tạo ra các sản phẩm chuẩn xác và đáng tin cậy.
