# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ (mô tả vị trí trong ảnh): hai đoạn sơn trắng chéo phân chia ô đỗ ở khu vực tiền cảnh; một đoạn gần góc dưới-trái và một đoạn gần phía dưới/phải của ảnh.
- Một vạch/dấu sơn hoặc biên **không** vẽ, và vì sao: dải sơn dài chạy ngang/lối xe chạy không được gán `parking_line` vì không tạo ranh giới của một ô đỗ riêng lẻ.
- Polygon `free_space` dừng ở đâu; có phần bị che nào không: chỉ bao phần mặt đường trống của lối xe chạy giữa các ô; dừng trước xe đang đỗ, mép curb và vùng bị che.
- Ca chưa chắc cần hỏi người soát (nếu không có, ghi “không có”): không có.
