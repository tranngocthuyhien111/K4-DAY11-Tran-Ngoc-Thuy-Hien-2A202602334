# QA review · B1-center

Mã khóa: `268F-003D`

Đây là cold review trên chính export đã khóa, không phải peer review độc lập. Các nhận xét chỉ ghi nhận điểm lệch với teaching reference và yêu cầu soát ảnh gốc trước khi sửa.

| frame | object_ref | rule_id | nhận xét |
|---|---|---|---|
| adasind_006840.jpg | L7 | R10 | Compare báo `IGNORE_SCOPE`; cần kiểm tra bằng ảnh gốc trước khi thay đổi vì lỗi scope có thể làm sai phép đối chiếu. |
| adasind_036720.jpg | L4+R1 | R05 | Compare báo khác attribute; cần soát `truncated` và `occluded` theo đúng định nghĩa, không suy từ reference một mình. |
| adasind_056040.jpg | L4 | R10 | Compare báo `IGNORE_SCOPE` ở edge; giữ nhãn khóa, chuyển ca này sang review trực quan trước rework. |
