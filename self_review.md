# Tự đánh giá — Trần Đức Hải · G05

## 1. Tự rà soát 4 cảnh

Nghỉ tay 1 phút, mở lại bài của mình, chọn 4 ảnh (2 S##, 2 D##), đọc như người lạ.

Loại lỗi: `seat_flip`, `wrong_class`, `guess`, `box`, `missing`, `extra`, `lr_flip` (trái/phải mặt), `flag` (thiếu cờ điểm), `ok`.

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S08_rgb | object/cup | missing | Bỏ sót cốc ở hàng ghế giữa. | Đã sửa |
| S08_ir | object/cup | missing | Lặp lại lỗi bỏ sót cốc ở ảnh IR. | Đã sửa |
| D02 | face.eye_left / face.eye_right | guess | Ghi open dù phản xạ IR che mắt. | Đã sửa |
| D04 | hand.side | lr_flip | Gán trái/phải theo ảnh thay vì theo người. | Đã sửa |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

Lỗi: Bỏ sót vật nhỏ ở hàng ghế giữa trong cả cặp S08 RGB/IR.

Vì sao mình mắc: Tập trung vào người và ghế lớn nên chưa rà hết khu vực giữa xe.

Lần sau tránh bằng cách: Rà lần lượt từng hàng ghế và đối chiếu cặp RGB/IR trước khi export.

## 3. Ghi chú về disagreement_log

Một dòng bạn của mình đúng và mình sai. Mình học được gì từ dòng đó: Ở D02, peer chọn eye_state=unknown vì phản xạ IR che mắt; không nên ghi open khi không nhìn rõ mí.
