1.  computeActionFromValues cập nhật state tốt nhất đạt được bởi các action có thể xảy ra qua computeQValueFromValues
    computeQValueFromValues trả Q-value cho cặp state action đầu vào

2.  noise = 0

3.

4.  update: cập nhật q-value cho cặp state action
    computeValueFromQValues: trả về max q value trong các action hợp lệ
    getQValue: trả về q-value qua feature và trọng số của cặp state action
    computeActionFromQValues: random chọn action trong số các action có best q value
