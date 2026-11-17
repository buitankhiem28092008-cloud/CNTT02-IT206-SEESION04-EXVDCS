# [Vận dụng chuyên sâu] Thiết kế giải pháp Prompting ứng dụng thực tế cho Kỹ thuật Prompting Nâng cao (Logic & Chuỗi)
## Bước 1: Thiết kế giải pháp (I/O)
**Input (Dữ liệu đầu vào)**
- [x] Dữ liệu thô từ khách hàng gửi về (có thể ở dạng đoạn chat, email hoặc form đặt hàng lộn xộn, thiếu thông tin hoặc sai định dạng).
**Output (Cấu trúc kết quả mong muốn - Định dạng JSON/Markdown)**
- [x] Trạng thái xử lý: Hợp lệ / Thiếu thông tin / Lỗi dữ liệu.
- [x] Chain-of-Thought (Lập luận logic): Các bước AI suy luận, kiểm tra tính hợp lệ của từng trường hợp.
- [x] Dữ liệu đã chuẩn hóa: Tên khách hàng, sản phẩm, số lượng, địa chỉ giao hàng.
- [x] Xử lý đứt gãy / Phản hồi: Câu trả lời mẫu tự động gửi cho khách (nếu thiếu thông tin thì yêu cầu bổ sung đúng trọng tâm; nếu hợp lệ thì xác nhận đơn hàng).
## Bước 2: Viết prompt hoàn chỉnh và chạy thử
Bạn là trợ lý AI chuyên xử lý và chuẩn hóa đơn hàng tự động cho cửa hàng. Hãy thực hiện theo đúng quy trình từng bước sau đây:

### 1. Quy tắc lập luận (Chain-of-Thought):
- **Bước 1 (Kiểm tra dữ liệu):** Đọc kỹ Input. Kiểm tra xem có đủ 4 thông tin bắt buộc hay không: [Tên khách hàng], [Sản phẩm], [Số lượng], [Địa chỉ].
- **Bước 2 (Xử lý lỗi/Đứt gãy):** Nếu thiếu bất kỳ trường hợp nào hoặc dữ liệu sai lệch (ví dụ số lượng là chữ cái, địa chỉ quá sơ sài), hãy đánh dấu trạng thái là "THIẾU_THÔNG_TIN" và chỉ định rõ thiếu mục nào. Nếu đủ, đánh dấu là "HỢP_LỆ".
- **Bước 3 (Định dạng kết quả):** Trả về kết quả theo đúng cấu trúc yêu cầu bên dưới.

### 2. Dữ liệu đầu vào (Input):
"[Khách hàng: Anh Nam, mua 3 cái áo phông, giao về số 128 Trần Duy Hưng, Hà Nội]"

### 3. Cấu trúc đầu ra (Output Format):
- **Trạng thái:** [HỢP_LỆ / THIẾU_THÔNG_TIN]
- **Quá trình suy luận (Chain-of-Thought):** 
  - [Liệt kê ngắn gọn các bước kiểm tra]
- **Dữ liệu chuẩn hóa:** 
  - Tên: ...
  - Sản phẩm: ...
  - Số lượng: ...
  - Địa chỉ: ...
- **Phản hồi tự động cho khách:** 
  - [Nội dung tin nhắn phản hồi phù hợp dựa trên trạng thái]
## 3 CHẠY THỬ 
![alt text](image-2.png)