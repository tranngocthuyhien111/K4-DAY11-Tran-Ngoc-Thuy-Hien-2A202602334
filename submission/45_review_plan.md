# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| `adasind_006840.jpg` | 3 khác biệt L/R: `IGNORE_SCOPE`, `WRONG_CLASS`, `MISSING`; center có L thiếu 2/L thừa 1 | Có ca P0 scope và precision/recall frame thấp nhất trong local quality (accuracy 0.778) | Frame nguồn `submission/screenshots/adasind_006840_evidence.jpg`, compare và overlay QA |
| `adasind_056040.jpg` | 5 khác biệt L/R: 1 `IGNORE_SCOPE`, 3 `ATTRIBUTE`, 1 `MISSING` | Có khác biệt ở center/mid/edge, gồm scope và attribute cần phân biệt bằng ảnh gốc | Frame nguồn `submission/screenshots/adasind_056040_evidence.jpg`, compare và overlay QA |

Giới hạn của kết luận từ ba frame ADASIND: đây là một camera và ba frame, không đại diện cho bốn camera SVM hay tỷ lệ lỗi toàn bộ dữ liệu; teaching reference không tự chứng minh nhãn khóa sai.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: phân tầng theo camera × normal/hard, rải mẫu theo block thời gian/cảnh và không coi các frame liền nhau là ca độc lập. Kế hoạch chỉ tạo coverage review; không có gold set được duyệt hoặc lấy mẫu ngẫu nhiên đại diện nên không ước lượng tỷ lệ lỗi.
