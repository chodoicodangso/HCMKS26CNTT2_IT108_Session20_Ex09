Phần 1: Thiết kế Prompt 3 Thành phần Chuẩn hóa  
1\. Nguyên nhân AI Hallucination: Câu hỏi thiếu bối cảnh và mã lỗi thực tế, buộc AI phải đoán mò (ảo giác) và đưa ra hướng dẫn sai lệch về phần cứng thay vì lỗi phân quyền phần mềm.  
2\. Prompt đề xuất:  
\[Context\]: Trạm sạc VoltCharge (Windows 11\) dừng đột ngột, hiện lỗi phần mềm.  
\[Raw Error\]: \[TERMINAL ERROR LOG... (dán toàn bộ 8 dòng log lỗi) ...verify NTFS file permissions.\]  
\[Instruction\]: Giải thích lỗi UnauthorizedAccessException bằng tiếng Việt đơn giản và đưa ra 3 bước cấp quyền ghi file cho thư mục data trên Windows 11\.  
Phần 2: Giải mã Lỗi & Kịch bản Khắc phục  
3\. Nguyên nhân gốc rễ: Lỗi UnauthorizedAccessException xảy ra do hệ điều hành chặn phần mềm ghi dữ liệu vào thư mục bảo vệ C:\\Program Files\\... vì chưa được cấp quyền admin  
4\. 3 Bước xử lý (Windows 11):  
Chạy tạm quyền Admin: Chuột phải biểu tượng VoltCharge \-\> Run as administrator để trạm hoạt động ngay.  
Mở cài đặt phân quyền: Vào C:\\Program Files\\VoltCharge\\, chuột phải thư mục data \-\> Properties \-\> tab Security \-\> bấm Edit.  
Cấp quyền vĩnh viễn: Chọn tài khoản Users, đánh dấu tích Allow ở dòng Full control (hoặc Modify/Write) \-\> Apply \-\> OK.  
5\. Bẫy an ninh (API\_KEY): Bắt buộc phải xóa hoặc che mờ  trước khi đưa log lên AI. Tránh rò rỉ dữ liệu bảo mật, giúp ngăn chặn nguy cơ tin tặc chiếm quyền điều khiển hệ thống trạm sạc.  
