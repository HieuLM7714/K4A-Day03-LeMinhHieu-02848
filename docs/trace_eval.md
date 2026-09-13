# 📊 BÁO CÁO THU HOẠCH NGHIỆM THU BÀI LAB 3 (BƯỚC 3 — SUBMISSION ARTIFACT)

> **Họ và Tên Học viên:** Lê Minh Hiếu
> **Mã Sinh Viên / Mã Học viên:** 2A202602848
> **Chủ đề Lựa chọn:** Trợ lý Học vụ & Tra cứu Lịch thi VinUni

---

## 1. BẢNG CHẤM ĐIỂM AGENTIC FIT SCORING MATRIX (ĐÁNH GIÁ CHỦ ĐỀ)


| Tiêu chí Đánh giá | Mức độ (1 - 5) | Giải trình chi tiết lý do chọn điểm |
| :--- | :---: | :--- |
| **1. Multi-step Reasoning** | **4** / 5 | Luồng nghiệp vụ bắt buộc phân rã theo chuỗi logic: Xác thực sinh viên -> Tra cứu điều kiện học vụ/GPA -> Tìm khung giờ cố vấn khả dụng -> Ghi nhận lịch hẹn. |
| **2. Tool Interaction** | **5** / 5 | Bắt buộc kết nối tối thiểu 2 công cụ ngoại vi qua MCP Server: Tool tra cứu cơ sở dữ liệu sinh viên/điểm số (`academic_query`) và Tool ghi nhận/cập nhật sự kiện vào lịch (`advisor_booking`). |
| **3. Dynamic Decision** | **4** / 5 | Quyết định bước tiếp theo rẽ nhánh dựa vào quan sát (`observation`): Nếu GPA < 2.0 hoặc có điểm F thì chủ động gợi ý phiên cố vấn khẩn cấp; nếu slot lịch bận thì truy vấn đề xuất khung giờ thay thế. |
| **4. Long Horizon Goal** | **4** / 5 | Duy trì trạng thái qua nhiều lượt hội thoại: Ghi nhớ thông tin sinh viên từ đầu phiên, xác nhận lại nội dung tư vấn trước khi kích hoạt lệnh ghi lịch chính thức. |
| **TỔNG ĐIỂM AGENTIC FIT** | **17 / 20** | **Đạt chuẩn xuất sắc (> 12/20):** Bài toán hoàn toàn phù hợp để triển khai kiến trúc Agentic System. |
---

## 2. TRÍCH XUẤT KẾT QUẢ WATERFALL TRACE LOG (SAU KHI CHẠY TEST SUITE TRÊN API THẬT)

> ⚠️ **YÊU CẦU NGHIỆM THU:** Mở tệp `.env` điền `GEMINI_API_KEY` (hoặc `OPENAI_API_KEY`) để kết nối LLM thật trước khi thực thi `python src/app.py --all`. Bài nộp chỉ dùng Mock Offline Provider sẽ không đạt điểm nghiệm thực tế.

Dán 1 đoạn trích xuất log tiêu biểu từ file `docs/trace_waterfall.json` sinh ra từ phản hồi LLM API thật:

```json
[
  {
    "step": 1,
    "query": "Bạn kiểm tra giúp tôi hồ sơ học vụ và điểm số của sinh viên có mã SV9999999 nhé.",
    "action_type": "TOOL_EXECUTION",
    "tool_name": "academic_query",
    "arguments": {
      "student_id": "SV9999999"
    },
    "observation": {
      "status": "NOT_FOUND",
      "message": "Không tìm thấy dữ liệu sinh viên có mã 'SV9999999'"
    },
    "latency_ms": 2765.31
  },
  {
    "step": 2,
    "query": "Bạn kiểm tra giúp tôi hồ sơ học vụ và điểm số của sinh viên có mã SV9999999 nhé.",
    "action_type": "FINAL_ANSWER",
    "thought": "Tổng hợp kết quả từ MCP Server thành công.",
    "output": "Không tìm thấy dữ liệu sinh viên có mã 'SV9999999'",
    "latency_ms": 10.0
  }
]
```

---

## 3. TỔNG KẾT KẾT QUẢ NGHIỆM THU & NỘP BÀI

- [x] Đã điền API Key thật trong `.env` và xác nhận Agent chạy mượt mà trên LLM API thật (Gemini/OpenAI).
- **Tổng số Test Cases đã chạy thành công:** _5__ / 5 test cases.
- **Số lượt gọi Tool qua MCP Server chính xác:** _4__ lượt.
- **Kết quả đẩy Repo nộp bài:** [x] Đã Commit và Push mã nguồn thành công lên GitHub cá nhân.

---

> ✅ **HOÀN TẤT NỘP BÀI:** Sao chép đường link GitHub Repository cá nhân của bạn và dán vào ô nộp bài trên hệ thống LMS VLearn để hoàn tất Bài Lab 3!
