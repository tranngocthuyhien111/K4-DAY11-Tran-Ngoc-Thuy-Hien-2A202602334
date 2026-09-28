# Đề xuất gold set theo camera — tình huống giả lập

**Đầu bài:** 50.000 frame từ bốn camera SVM, ngân sách chọn 200 frame để review/gold. Đây là tình huống trên slide,
**không phải** 50.000 frame có trong repo. Phân bổ đúng 200 ở `45_sampling_plan.csv` cho bốn camera, mỗi camera có
normal và hard slice. “Gold set” ở đây là **kế hoạch tạo** reference sau kiểm chứng, không phải teaching reference
ADASIND hoặc nhãn bạn vừa vẽ. Nếu cần, dùng `notebooks/day11-svm360-colab.ipynb` để thử tổng phân bổ; notebook
không làm thay phần lý do.

| camera_id | Hard case cần chọn | Vì sao dễ sai | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|
| front | Mép kính, thân xe ego và che khuất ở hướng tiến. | Méo fisheye và phần cảnh bị che làm sai biên box/mask. | Giữ tọa độ ảnh gốc, `lens_border`, `ego_body`, truncation và occlusion. | Hai người review độc lập; giải quyết bất đồng theo guideline trước khi gọi là gold. |
| rear | Mép kính, thân xe ego và che khuất ở hướng lùi. | Vật thể nhỏ/gần mép có thể bị cắt hoặc bị che. | Giữ tọa độ ảnh gốc, `lens_border`, `ego_body`, truncation và occlusion. | Hai người review độc lập; giải quyết bất đồng theo guideline trước khi gọi là gold. |
| left | Vật thể sát mép kính và che khuất theo phương ngang. | Méo ở rìa và hình học ảnh khác hướng trước/sau. | Giữ tọa độ ảnh gốc, `lens_border`, `ego_body`, truncation và occlusion. | Hai người review độc lập; giải quyết bất đồng theo guideline trước khi gọi là gold. |
| right | Vật thể sát mép kính và che khuất theo phương ngang. | Méo ở rìa và hình học ảnh khác hướng trước/sau. | Giữ tọa độ ảnh gốc, `lens_border`, `ego_body`, truncation và occlusion. | Hai người review độc lập; giải quyết bất đồng theo guideline trước khi gọi là gold. |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): khi đổi camera/rig, calibration, taxonomy hoặc guideline; cũng refresh khi lỗi review tập trung ở một camera hay hard slice.
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: chỉ ghép khi có policy về cùng thời điểm, calibration/seam và bằng chứng object tương ứng; nếu thiếu các điều kiện này, giữ annotation độc lập theo từng camera.
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: chúng chỉ phản ánh ảnh/camera và mẫu được review; không kiểm chứng được khác biệt hình học, che khuất, seam hoặc calibration của ba camera còn lại.
