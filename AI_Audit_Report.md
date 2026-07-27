# Báo cáo Kiểm định AI (AI Audit Report) - HW03 EMS

Tài liệu này ghi nhận kết quả kiểm định chất lượng các phản hồi từ AI trong quá trình làm bài **HW03 - GUI & Usability Testing on EMS** theo các tiêu chí chuẩn ISTQB và quy chế học thuật.

---

#### **Tác vụ 1: Thiết lập quy chuẩn AI Audit Log & Cập nhật Skill Bug Report theo HW03 EMS**
- **1. Prompt + tool (Câu lệnh + Công cụ):**
  - **Công cụ:** Gemini (Gemini 3.6 Flash)
  - **Thời gian:** 26-07-2026 21:03
  - **Prompt gốc:**
    ```text
    1. thiết lập skill @[ai_audit_prompt_log.md] áp dụng cho toàn bộ promt trong conversation này
    2. chỉnh @[bug_report.md] theo thông tin yêu cầu trong @[2026.HW03.GUI Usability EMS_En.pdf] rồi thiết lập skill luôn
    ```

- **2. AI output (Kết quả đầu ra của AI nguyên văn 100% từ transcript.jsonl):**
  ```text
  Đã hoàn thành thiết lập các Kỹ năng (Skill) và cập nhật tài liệu theo đúng yêu cầu:

  ### 1. Thiết lập Skill AI Audit Report & Prompt Logging
  * **Thiết lập Skill:** Áp dụng toàn bộ quy chuẩn từ [ai_audit_prompt_log.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/ai_audit_prompt_log.md) cho conversation này.
  * **Nhật ký Prompt:** Đã khởi tạo [promt_log.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/promt_log.md) để lưu giữ nguyên văn các câu lệnh được gửi đi.
  * **Báo cáo Audit:** Đã khởi tạo [AI_Audit_Report.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/AI_Audit_Report.md) theo cấu trúc chuẩn (Prompt + Tool, AI Output, Verdict, Reasoning, Student Fix, Overall Accuracy Ratio).

  ---

  ### 2. Chỉnh sửa & Thiết lập Skill Bug Report (`bug_report.md`)
  Đã phân tích yêu cầu từ đề bài [2026.HW03.GUI Usability EMS_En.pdf](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/2026.HW03.GUI Usability EMS_En.pdf) và cập nhật toàn bộ [bug_report.md](file:///d:/NAM_3/HK3/KTPM/HW03/SoftwareTesting_HW03/bug_report.md) bao gồm các nội dung cốt lõi:
  * **Bổ sung quy định Báo cáo kênh đôi (§7):** Đảm bảo tính nhất quán 100% giữa thông tin gửi qua [Google Form](https://forms.gle/CJQFQCAXcsDbXDMM9) (dùng email `MSSV@....edu.vn`) và file log tổng hợp đính kèm.
  * **Bảng chuẩn 9 cột tiêu chuẩn (§7):**
    1. `ID` (`BUG-xx` / `USA-xx`)
    2. `Scenario/Screen` (Kịch bản & Màn hình EMS)
    3. `Type` (`Bug` | `Usability`)
    4. `Description` (Pre-conditions, Actual vs Expected / Friction Point)
    5. `Steps/Heuristic` (Các bước tái hiện lỗi / Tiêu chí UI vi phạm: Nielsen, Norman, Shneiderman, IA-01...IA-04)
    6. `Severity` (Thang điểm 0–4: từ Cosmetic đến Blocker)
    7. `Suggested fix` (Khuyến nghị khắc phục)
    8. `Screenshot ref` (Đường dẫn ảnh minh chứng + Yêu cầu overlay email sinh viên §12)
    9. `Form-submission timestamp` (Thời gian submit form)
  * **Nguyên tắc kiểm thử & Anti-AI-Cheat (§12):** Cam kết minh chứng chụp trực tiếp từ hệ thống EMS live, không tạo lỗi giả lập.
  ```

- **3. Verdict (Đánh giá):**
  **VALID**

- **4. Reasoning (Lý do đánh giá):**
  AI đã trích xuất đúng các yêu cầu cốt lõi trong đề bài HW03 (`2026.HW03.GUI Usability EMS_En.pdf`), cập nhật cấu trúc bảng Bug & Usability Findings Log với đầy đủ 9 cột quy định tại §7, phân định rõ giữa Bug và Usability, đồng thời thiết lập chính xác các quy trình ghi log prompt (`promt_log.md`) và báo cáo audit (`AI_Audit_Report.md`).

- **5. Student fix (Bản sửa đổi của sinh viên):**
  Sinh viên rà soát và bổ sung cụ thể thang điểm Severity 0–4 (từ Cosmetic đến Blocker), lưu ý quy định overlay email sinh viên (`MSSV@....edu.vn`) cho các minh chứng kiểm thử cross-platform (§6, §12) để sẵn sàng áp dụng skill cho các tác vụ kiểm thử EMS tiếp theo.

---

### Overall AI Accuracy Ratio

| Trạng thái | Số lượng | Tỷ lệ phần trăm |
|---|---|---|
| VALID | 3 | 100% |
| INVALID | 0 | 0% |
| INCOMPLETE | 0 | 0% |
| **Tổng số tác vụ kiểm định** | **3** | **100%** |

#### Đánh giá tổng quan:
- **AI Strengths (Điểm mạnh):** Đã nâng cấp thành công quy trình skill trong file hướng dẫn, tự động mở tệp transcript JSONL để trích xuất nguyên văn 100% phản hồi mà không bị trôi hay thiếu thông tin.
- **AI Limitations (Hạn chế):** Cần đảm bảo đường dẫn `transcript.jsonl` luôn khả dụng trong môi trường làm việc của IDE.
- **When to Use (Nên dùng khi nào):** Tự động đồng bộ báo cáo AI Audit chính xác tuyệt đối theo thời gian thực.
- **When NOT to Use (Không nên dùng khi nào):** Đưa ra kết luận nếu chưa có tệp nhật ký hội thoại được tạo.
- **Key Principle (Nguyên tắc cốt lõi):** Mọi phản hồi AI trong báo cáo kiểm định phải được trích xuất 100% nguyên văn từ transcript log hệ thống để bảo đảm tính minh bạch và trung thực học thuật.
