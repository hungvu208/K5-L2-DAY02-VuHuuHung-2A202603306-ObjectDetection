# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` |Phương tiện cơ giới đường bộ được thiết kế chủ yếu để chở người, thường có từ 4 bánh trở lên, kích thước nhỏ hoặc trung bình |Kích thước nhỏ, thường có 4–7 chỗ ngồi, không có thùng hàng lớn hoặc khoang chở khách công cộng |
| `truck` |Phương tiện cơ giới được thiết kế chủ yếu để vận chuyển hàng hóa, vật liệu hoặc các loại tải trọng khác. | Cabin lái tách biệt với khu vực chở hàng, có thùng hàng, bệ chở hàng hoặc container|
| `bus` |Phương tiện cơ giới được thiết kế chủ yếu để vận chuyển nhiều hành khách. |Thân xe dài, kích thước lớn, thường có cửa kính lớn dọc hai bên thân xe |
| `van` | Phương tiện cơ giới có thân xe dạng hộp, kích thước nhỏ hoặc trung bình, được thiết kế để vận chuyển hàng hóa hoặc hành khách| Thân xe cao, có hình dạng gần giống hình hộp, khoang cabin và khoang chở hàng thường nằm liền nhau, thường có cửa trượt ở bên hông|

## Quy tắc chung

- Box bám sát vật thể nghĩa là: các cạnh, góc của bounding box bám sát vào các cạnh biên của vật thể, không chứa quá nhiều nền
- Vật thể bị che khuất: vật thể ở sau vật khác, không quan sát được toàn bộ. bounding box toàn bộ phạm vi vật thể, cả phần bị khuất nếu đủ cơ sở xác định
- Vật thể bị cắt bởi rìa ảnh: không quan sát được toàn bộ vật thể do nằm ở ngoài phạm vi ảnh. bounding box phần xuất hiện trong ảnh
- Vật thể rất nhỏ/mơ hồ: kích thước quá nhỏ, hình dạng không rõ ràng/không đủ đặc điểm xác định chính xác đối tượng. bỏ qua 

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_002` |Nhiều xe xếp sát/che khuất nhau |không label các xe quá sát nhau |vật thể bị che khuất không đủ cơ sở xác định |
| `drive_019` |Nhiều xe ở phía xa xếp gần nhau |không label các xe phía xa |vật thể rất nhỏ, bị che khuất, không thể xác định |
| `drive_044` |Nhiều xe ở phía xa bị mờ |không label các xe bị mờ |vật thể rất nhỏ, không thể xác định |
