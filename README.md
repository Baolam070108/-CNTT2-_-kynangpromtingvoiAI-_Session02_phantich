# SO SÁNH TRADE-OFF CÁC GIẢI PHÁP VIẾT PROMPT

## Bước 1: Đề xuất 2 prompt mẫu

**Giải pháp 1: Prompt đơn giản**

Bạn là nhân viên phân tích đánh giá khách hàng của TechShop. Hãy phân loại đánh giá thành 3 nhóm: Tích cực, Tiêu cực hoặc Trung lập.

Ví dụ:
- Sản phẩm rất tốt -> Tích cực.
- Sản phẩm bị lỗi -> Tiêu cực.
- Sản phẩm bình thường -> Trung lập.

Trả kết quả dưới dạng JSON gồm 2 trường: danh_gia và phan_loai.

**Giải pháp 2: Prompt chi tiết**

Bạn là chuyên viên phân tích đánh giá khách hàng của TechShop.

Nhiệm vụ: Phân loại đánh giá thành 3 nhóm:
- Tích cực: Khách hàng hài lòng.
- Tiêu cực: Khách hàng không hài lòng.
- Trung lập: Không thể hiện cảm xúc rõ ràng.

Yêu cầu:
1. Sử dụng 3 ví dụ mẫu để hướng dẫn AI phân loại.
2. Không tự ý thay đổi nội dung đánh giá.
3. Nếu đánh giá không rõ ràng thì chọn Trung lập.
4. Chỉ trả kết quả dưới dạng JSON hợp lệ.
5. JSON phải có đủ 2 trường: danh_gia và phan_loai.
6. Không thêm nội dung ngoài JSON.

## Bước 2: Bảng so sánh Trade-off

| Tiêu chí | Giải pháp 1 | Giải pháp 2 |
|---|---|---|
| Độ dễ hiểu | Cao | Trung bình |
| Độ dài | Ngắn | Dài |
| Tốn token | Ít | Nhiều |
| Độ chính xác | Khá | Cao |
| Chặn lỗi biên | Trung bình | Tốt |
| Kiểm soát kết quả | Cơ bản | Tốt |

**Nhận xét:**
- Giải pháp 1: Dễ viết, tiết kiệm thời gian nhưng dễ gặp lỗi khi xử lý trường hợp phức tạp.
- Giải pháp 2: Hướng dẫn rõ ràng, kết quả chính xác hơn nhưng tốn nhiều token.

## Bước 3: Lựa chọn và chạy thử

**Lựa chọn:** Em chọn Giải pháp 2 vì có hướng dẫn cụ thể, hạn chế lỗi và giúp AI trả kết quả đúng định dạng JSON.

**Chạy thử:**

Đầu vào: "Sản phẩm rất đẹp, chất lượng tốt và giao hàng nhanh."

Kết quả:

{
  "danh_gia": "Sản phẩm rất đẹp, chất lượng tốt và giao hàng nhanh.",
  "phan_loai": "Tích cực"
}

**Đánh giá kết quả:**
- Phân loại đúng: Đạt.
- Định dạng JSON: Đạt.
- Đủ 2 trường dữ liệu: Đạt.
