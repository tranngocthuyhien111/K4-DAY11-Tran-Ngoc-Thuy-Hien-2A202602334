# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B1 | IGNORE_SCOPE | 2 |
| center | B1 | MISSING | 1 |
| center | B1 | SPURIOUS | 3 |
| center | B1 | WRONG_CLASS | 1 |
| center | C0 | BOX_GEOMETRY | 1 |
| edge | B1 | IGNORE_SCOPE | 1 |
| edge | B1 | MISSING | 1 |
| edge | B1 | SPURIOUS | 1 |
| edge | C0 | SPURIOUS | 1 |
| edge | C0 | WRONG_CLASS | 1 |
| mid | B1 | ATTRIBUTE | 2 |
| mid | B1 | MISSING | 2 |
| mid | B1 | SPURIOUS | 3 |

## Top defects
- SPURIOUS: 8 (ví dụ frame adasind_019560.jpg)
- MISSING: 4 (ví dụ frame adasind_006840.jpg)
- IGNORE_SCOPE: 3 (ví dụ frame adasind_006840.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: nhiều ca `SPURIOUS` đến từ cell `M_only` nên được mã hóa là `E4_model_domain`; chúng là proposal của model, không phải kết luận nhãn người thiếu/sai. Các ca L/R không khớp được giữ `E5_unresolved` vì ba frame và teaching reference chưa đủ để kết luận nguyên nhân.
- Cách sửa và ai nhận việc (`owner`): `ai_team` xem lại proposal model; `qa` soát các ca `IGNORE_SCOPE`; `annotator` chỉ rework sau khi QA xác nhận trên ảnh fisheye gốc.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): `submission/screenshots/adasind_006840_evidence.jpg`, findings `r1_craft/B1-center/adasind_006840.jpg/L7`, `submission/r1_craft/compare.md`, R01 và R10.
