# Sensor context

- Rig/camera: theo quan sát ba frame của slice `B1-center`, camera fisheye hướng về phía trước xe và đặt thấp gần vị trí người lái. Dữ liệu không cung cấp tài liệu rig hay calibration, vì vậy không khẳng định chính xác camera gắn trên bộ phận nào hoặc có thuộc hệ SVM bốn camera hay không.
- `ego_body`: một phần xe/người mang camera xuất hiện sát mép dưới, rõ nhất ở góc dưới-trái; có thể thấy tay/người lái và mép cong của thân xe trong một số frame. Chỉ coi các phần này là `ego_body` khi chúng thuộc về xe/cụm camera, không gán nhầm cho xe khác.
- Vòng kính: vùng ảnh hữu dụng là một vòng tròn/lễ hơi dịch lên phía trên, bao quanh bởi viền đen. Vòng kính chiếm gần toàn bộ bề ngang và khoảng 85–90% chiều cao khung; các góc và dải ngoài vòng là vùng không có nội dung cảnh. Một camera không cho phép suy ra seam, chồng lấp, khoảng cách thật hay track ID xuyên camera nếu thiếu timestamp, calibration và policy ghép.
