
## PHẦN 1: PHÂN TÍCH LỖI CÚ PHÁP VÀ HẬU QUẢ RENDER

Dưới đây là các lỗi cú pháp phát hiện được trong đoạn Markdown của giảng viên:

### 1. Lỗi ở tiêu đề Heading 3 (`###Lưu ý quan trọng`)
* **Lỗi cụ thể:** Thiếu khoảng trắng (space) ngay sau các dấu `#` (viết dính liền `###Lưu ý`).
* **Hậu quả khi render:** Trình biên dịch Markdown không nhận diện đây là một tiêu đề (Heading), do đó nó hiển thị nguyên văn chuỗi chữ `###Lưu ý quan trọng` thành một đoạn văn bản thường.

### 2. Lỗi ở danh sách bước nộp bài (`-Bước 1`, `-Bước 2`, ...)
* **Lỗi cụ thể:** Thiếu khoảng trắng sau dấu gạch ngang `-` ở tất cả 4 bước.
* **Hậu quả khi render:** Trình biên dịch không tạo thành danh sách dạng gạch đầu dòng (bullet points), khiến các bước bị dính liền thành các dòng chữ bình thường, làm mất cấu trúc danh sách trực quan.

### 3. Lỗi in đậm tên Repository (`**HNKS25CNTT1_IT101_Session08`)
* **Lỗi cụ thể:** Thiếu cặp dấu sao đôi `**` ở cuối chuỗi văn bản để đóng định dạng in đậm.
* **Hậu quả khi render:** Tên repository không được in đậm, đồng thời cặp dấu `**` mở đầu bị hiển thị thô ra màn hình hoặc làm lỗi định dạng in đậm lan sang các văn bản phía sau.

### 4. Lỗi ở liên kết Link (`[GitHub](github.com)`)
* **Lỗi cụ thể:** Đường dẫn URL trong ngoặc tròn thiếu tiền tố giao thức `https://`.
* **Hậu quả khi render:** Trình duyệt coi đây là một **đường dẫn tương đối (Relative Path)** nối tiếp vào URL hiện tại của trang (ví dụ: `https://ten-mien-truong.com/github.com`) thay vì chuyển hướng sang trang web GitHub chính thức, dẫn đến lỗi "404 Not Found".

### 5. Lỗi ở đoạn Blockquote chú ý cuối cùng (`> Deadline: ... *Nộp muộn sẽ bị trừ 50% điểm!**`)
* **Lỗi cụ thể:** Mở định dạng in nghiêng bằng 1 dấu sao `*` nhưng lại đóng bằng 2 dấu sao `**`.
* **Hậu quả khi render:** Mất định dạng in nghiêng của câu cảnh báo, đồng thời để thừa ký tự `*` hiển thị vô nghĩa trên màn hình.

---

## PHẦN 2: BẢN MARKDOWN ĐÃ SỬA ĐÚNG CHUẨN

```markdown
## Hướng Dẫn Nộp Bài Tập - Session 08

### Lưu ý quan trọng

Các bước nộp bài:
- Bước 1: Tạo tài khoản GitHub tại [GitHub](https://github.com)
- Bước 2: Tạo repository mới đặt tên theo định dạng **HNKS25CNTT1_IT101_Session08**
- Bước 3: Upload file .md của bài làm lên repository
- Bước 4: Copy đường dẫn và nộp lên Portal

> Deadline: Chủ nhật 23:59 — *Nộp muộn sẽ bị trừ 50% điểm!*
```

---

## PHẦN 3: GIẢI ĐÁP BẪY DỮ LIỆU VỀ ĐƯỜNG LINK

**Câu hỏi:** Nếu sinh viên paste đường link GitHub mà quên gõ `https://` ở đầu, điều gì sẽ xảy ra với link đó khi render?

**Trả lời:**  
Khi thiếu `https://` ở đầu, trình duyệt sẽ coi đường dẫn đó là một **đường dẫn tương đối (Relative URL)** thuộc về hệ thống website hiện tại. Khi người dùng bấm vào link, trình duyệt sẽ nối thêm chuỗi đó vào sau domain hiện tại (ví dụ: `https://lms.ptit.edu.vn/github.com`). Kết quả là người dùng sẽ bị dẫn sang một trang không tồn tại và gặp lỗi **404 Page Not Found**.