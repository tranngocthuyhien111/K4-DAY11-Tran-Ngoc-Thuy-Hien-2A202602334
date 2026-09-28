# So sánh L với R

Chỉ số L/R là thứ tự box cao ≥ H=40 trong từng frame, theo thứ tự XML; bắt đầu từ 1.
Box L trong ignore_region được báo IGNORE_SCOPE, không tính SPURIOUS.

## adasind_006840.jpg
- L7 center IGNORE_SCOPE
- L2+R4 center WRONG_CLASS
- R9 edge MISSING
## adasind_036720.jpg
- L4+R1 mid ATTRIBUTE
## adasind_056040.jpg
- L4 edge IGNORE_SCOPE
- L2+R5 center ATTRIBUTE
- L3+R2 edge ATTRIBUTE
- L7+R7 mid ATTRIBUTE
- R1 center MISSING

## Theo zone
| zone | n_ref | matched | missing | spurious |
|---|---|---|---|---|
| center | 10 | 8 | 2 | 1 |
| mid | 7 | 7 | 0 | 0 |
| edge | 3 | 2 | 1 | 0 |
