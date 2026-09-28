# Guideline patch

- **Rule mới đề xuất:** thêm checklist review theo frame cho R07: ghi rõ `ego_body` hiện diện hay vắng mặt, rồi đối chiếu polygon với phần thân xe thấy được trên ảnh gốc.
- **Áp dụng cho:** `ignore_region.reason=ego_body` trong tất cả frame fisheye mà người gán nhãn phụ trách.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** R07 đã nêu quy tắc, nhưng self-QC không bắt buộc ghi kết quả theo từng frame. Điều này làm khó phân biệt polygon thừa với polygon thiếu khi compare báo `IGNORE_SCOPE`.
- **`rules_version` mới:** đề xuất v1.0.0 → v1.0.1; đây là đề xuất cho guideline, không sửa luật nguồn trong repo.
- **Hiệu lực từ:** chỉ áp dụng từ rework sau khi người soát/guideline owner chấp thuận.
