# Rework delta

| zone | matched before | matched after | missing before | missing after | spurious before | spurious after |
|---|---:|---:|---:|---:|---:|---:|
| center | 8 | 8 | 2 | 2 | 1 | 1 |
| mid | 7 | 7 | 0 | 0 | 0 | 0 |
| edge | 2 | 2 | 1 | 1 | 0 | 0 |

## Findings action=rework

Không có finding nào được đổi sang `action=rework`. Các mismatch còn lại được giữ là `E5_unresolved` theo quyết định D05 trong `40_decision_log.csv`; vì vậy export rework trùng export B1 đã khóa và bảng delta không thay đổi.
