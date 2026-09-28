# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi `DUPLICATE` hay cần một quy
   tắc riêng? Vì sao? Cần một quy tắc cross-camera riêng. Hai box có thể là quan sát hợp lệ của cùng vật từ hai camera ở seam; không được gọi là `DUPLICATE` hay tự xóa một box nếu thiếu timestamp, calibration và policy output.
2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái
   Outside? Nêu bằng chứng sẽ cần trước khi nối track qua hai camera. Giữ cùng track ID khi có bằng chứng đó là cùng vật và quan sát liên tục trên cùng camera; thêm keyframe khi hình học đổi đáng kể; đặt Outside khi vật rời trường nhìn. Trước khi nối qua camera cần timestamp đồng bộ, calibration/seam, bằng chứng tương ứng và policy ghép track.
3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/`object_ref`),
   bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm? `adasind_006840.jpg` object `L7` được compare báo `IGNORE_SCOPE`. Mình không đổi nhãn chỉ vì teaching reference; đã ghi escalation để review ảnh gốc. Nếu làm lại, mình sẽ kiểm soát phạm vi ignore theo từng frame trước khi khóa export.
