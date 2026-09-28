# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 10 | 2 | 1 | 5 | 6 | WRONG_CLASS (1) |
| mid | 7 | 0 | 0 | 3 | 6 | ATTRIBUTE (2) |
| edge | 3 | 1 | 0 | 2 | 5 | MISSING (1) |

## Nhận xét

- Về số lượng bất đồng, center có nhiều nhất: L thiếu 2, L thừa 1; model thiếu 5 và thừa 6. Mid có 3 model thiếu và 6 model thừa; edge có 1 L thiếu, 2 model thiếu và 5 model thừa.
- Ba frame không đủ để kết luận nguyên nhân là méo fisheye, box lỏng hay lỗi `ego_body`. Báo cáo chỉ cho thấy các cell L/R/M không khớp; cần xem ảnh gốc và policy trước khi rework.
