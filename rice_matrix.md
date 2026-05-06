# Prioritization: RICE & 2x2 Matrix
*Product: AI Skill-Gap Analyzer*

## 1. RICE Score Table
Dự phóng Reach (R) dựa trên tệp 50.000 user/năm, đã discount xuống mức realistic cho quý đầu. Confidence (C) tuân thủ quy tắc: chưa test thực tế = 50% MAX. Effort (E) tính theo person-month, đã nhân hệ số rủi ro 1.5x.

| Tính năng | R (Reach) | I (Impact) | C (Confidence) | E (Effort) | RICE Score |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1. Trích xuất đúng 3 kỹ năng hổng lõi** | 1000 | 3.0 | 80% (Đã test prompt) | 2 | **1200** |
| **2. Gợi ý khóa học từ Curated List tĩnh** | 1000 | 2.0 | 100% (Data tĩnh) | 1 | **2000** |
| **3. API kết nối thẳng HR (Job Referral)** | 200 | 3.0 | 50% (Chưa hỏi B2B) | 5 | **60** |
| **4. Dashboard tracking chứng chỉ CV** | 500 | 1.0 | 80% | 2 | **200** |
| **5. Quét lịch sử GitHub tự động điền CV** | 100 | 1.0 | 50% (Sinh viên VN ít dùng)| 4 | **12.5** |

*(Công thức: Score = R x I x C / E)*

## 2. 2x2 Value-Effort Matrix
*   **Quick Wins (Làm ngay):** Tính năng 2 (Gợi ý từ Curated List). Đem lại giá trị tức thì, dễ code vì CSDL tĩnh, tạo ra Aha moment ngay.
*   **Strategic Bets (Đầu tư dài hạn):** Tính năng 1 (Core AI). Cần thời gian tinh chỉnh Prompt Engineering để ép output đúng 3 kỹ năng, tạo ra "Workflow Moat".
*   **Fill-ins (Làm khi rảnh):** Tính năng 4 (Dashboard tracking). 
*   **Non-starters (Vứt sọt rác):** Tính năng 5 (Quét GitHub) và Tính năng 3 (API kết nối HR). Tốn quá nhiều nguồn lực nhưng reach/confidence quá thấp trong giai đoạn hạt giống.