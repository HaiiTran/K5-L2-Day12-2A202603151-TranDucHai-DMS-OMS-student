# Danh sách lớp v0 — Trần Đức Hải · G05

Viết tiếp từ slide 54 bài giảng. Mỗi lớp trả lời: **model cần nhận ra cái này để làm gì?**
Xóa 2 dòng ví dụ trước khi nộp.

## DMS (ít nhất 6 lớp)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | eye_state | open / closed / unknown | Phát hiện mắt nhắm kéo dài để cảnh báo buồn ngủ | Có; trừ khi có phản xạ kính |
| 2 | gaze_zone | road / mirror_l / mirror_r / mirror_c / cluster / center / lap / other | Phát hiện tài xế mất tập trung khi lái xe | Có; khi  thấy được mắt và hướng đầu |
| 3 | glasses | unknown / none / clear / sun | Giúp xử lý trường hợp mắt bị kính râm che hoặc phản xạ | Một phần; kính râm có thể khó phân biệt trên NIR |
| 4 | face13 | 13 điểm mặt; occluded / outside | Định vị mắt, mũi, miệng để phân tích trạng thái mặt | Nhìn được khi rõ mặt, các điểm bị chói hoặc khuất cần gắn cờ |
| 5 | hand | whose / side / on_wheel | Nhận biết tay tài xế và đảm bảo tay trên vô lăng | Có; nếu tay không bị che |
| 6 | phone | held / mounted / lap | Phát hiện việc sử dụng điện thoại khi lái xe | Có; theo hình dạng, vật nhỏ hoặc bị che có thể khó thấy |

## OMS (ít nhất 6 lớp)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | person | seat: driver / front_passenger / rear_left / rear_middle / rear_right | Xác định vị trí người ngồi trong xe | Có; theo hình dáng người, ảnh tối có thể giảm tương phản |
| 2 | seatbelt | worn_correct / worn_incorrect / not_worn / unknown | Theo dõi thắt dây an toàn | Một phần; dây tối hoặc chìm vào áo có thể khó thấy |
| 3 | child_seat | occupied: no / unknown / yes | Nhận biết trẻ em trên ghế để hỗ trợ cảnh báo và cài đặt an toàn | Có; theo hình dạng ghế |
| 4 | infant_seat | facing: rear / front | Nhận biết nôi em bé và hướng lắp nôi | Có; theo hình dạng và hướng ghế |
| 5 | object | type: bag / box / cup / other | Nhận biết đồ vật trong cabin để quản lý vật dụng | Có; theo hình dạng|
| 6 | face | box | Định vị mặt người lớn cùng box person | Có nếu mặt đủ rõ |

## 2 câu hỏi leo thang

Câu hỏi bạn muốn hỏi người viết guideline (hoặc khách hàng) vì guideline v1.0 chưa trả lời. Mỗi câu kèm **tên khung** làm ví dụ.

1. Câu hỏi: Khi infant_seat rỗng và chỉ thấy một phần vỏ ghế, tiêu chí nào để xác định facing=rear hay facing=front?
   Khung ví dụ: S02_rgb
   Bạn tạm gán thế nào và vì sao: Dựa vào điểm cao ước chừng giữa 2 điểm đầu xe.
2. Câu hỏi: Khi phản xạ NIR che một phần mắt, ngưỡng nào để chọn occluded thay vì outside cho điểm face13?
   Khung ví dụ: D02
   Bạn tạm gán thế nào và vì sao: Chọn occluded trong trường hợp xác định được vị trí, chọn outside nếu không xác định được, và eye_state=unknown khi không thấy rõ.
