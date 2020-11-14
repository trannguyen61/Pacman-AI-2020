1. Perceptron
Duyệt lần lượt các feature và tính score dựa theo feature đó và weight.
Label được đoán sẽ là label có score cao nhất.
Lúc này, cập nhật weight để đần đưa weight về kết quả chính xác.
weight của label đúng += feature
weight của label dự đoán -= feature

2. Câu a.

3. MIRA
Duyệt feature, label tương tự Perceptron, cập nhật tính thêm t 
weight của label đúng += feature * t
weight của label dự đoán -= feature * t
Không nhân được feature * t nên sử dụng divideAll(1/t) để thực hiện phép tính này. (f.divideAll(1.0 / t))
Duyệt qua max_iteration
Lưu weight với c tốt nhất

4. Tính aspect ratio của ảnh

5. Tương tự perceptron thông thường

6. StopAgent: Trả là win hay lose state
FoodAgent: Food càng gần giá trị càng lớn, trọng số 30
SuicideAgent: Ghost càng gần giá trị càng lớn, trọng số 10
CapsuleAgent: Capsule càng gần giá trị càng lớn 
