# Dependency Map & Critical Path

## 1. External Dependencies (Rủi ro Ký sinh & Plan B)

**Dependency 1: OpenAI API (Tier 1 - Critical)**
*   **Worst-case:** OpenAI đột ngột siết Rate Limit cho GPT-4o-mini hoặc khóa API Key không báo trước khiến tính năng cốt lõi sụp đổ.
*   **Plan B:** Đã code sẵn một Abstraction Layer cho LLM trong source code. Sẵn sàng switch toàn bộ request sang Google Gemini 1.5 Flash thông qua GCP trong vòng 24h.
*   **Cost:** Mất 1 tuần Dev để viết sẵn Abstraction Layer.

**Dependency 2: Cloud Infrastructure AWS/GCP (Tier 1 - Critical)**
*   **Worst-case:** Data center bị sập phân vùng (Region down), mất toàn bộ kết nối.
*   **Plan B:** Setup hạ tầng Multi-AZ (Nhiều vùng khả dụng) và chuẩn bị sẵn script Terraform để spin-up hệ thống sang server dự phòng (Vultr/DigitalOcean) trong vòng 4 giờ.
*   **Cost:** Mất 1.5 tuần Dev để cấu hình CI/CD dự phòng.

**Dependency 3: Payment Gateway MoMo/VNPay (Tier 2 - Important)**
*   **Worst-case:** Kẹt API hoặc tài khoản doanh nghiệp bị review hold tiền đúng ngày Launch.
*   **Plan B:** Tích hợp sẵn fallback hiển thị QR code "Chuyển khoản thủ công" tĩnh ngay trên màn hình Paywall để hứng dòng tiền khẩn cấp.
*   **Cost:** Mất 2 ngày code UI fallback.

---

## 2. Critical Path (Đường găng dự án)
*Đây là chuỗi task dài nhất và bắt buộc phải tuần tự. Trễ 1 ngày trên đường đỏ = Trễ Launch 1 ngày.*

**CRITICAL PATH (Chuỗi đỏ):**
Data Pipeline (Xây dựng CSDL 100 khóa học tĩnh) ➔ Legal Compliance (Điều khoản bảo mật, Không dùng CV user để train model) ➔ Model Fine-tuning / Prompt Engineering ➔ API Integration ➔ Core Launch.

**Buffer Tasks (Đường xám - Không quyết định Launch Date, làm song song):**
*   UI/UX Design.
*   Marketing Site / Landing Page.
*   Analytics Tracking (Mixpanel / GA4 setup).