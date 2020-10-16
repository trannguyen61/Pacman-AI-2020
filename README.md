1. Reflex Agent
   Tính evaluation score dựa trên score hiện tại của successor và:

- Khoảng cách đến food gần nhất: Tỉ lệ nghịch. Khoảng cách càng ngắn thì điểm càng cao
- Ma đang ở gần pacman (distance <= 2): Trừ nhiều điểm đối với state có ma ở gần
- Thời gian để ma hết sợ pacman nhỏ (time <= 2): Trừ nhiều điểm đối với state đang có thời gian ma hết sợ ngắn

2. Minimax

- Ở hàm getAction, gọi đến hàm minimax. Hàm minimax trả về 1 tuple (stateValue, action)
- Hàm Minimax:
  - agentIndex = depth % numAgents; hàm đang duyệt đến mức sâu nhất khi depth == self.depth \* numAgents vì self.depth tính là 1 lượt di chuyển cho toàn bộ agent, còn depth tính là 1 lượt di chuyển cho 1 agent
  - Khi agent là pacman (agentIndex = 0), trả về hàm maxValue
  - Khi agent là ghost (agentIndex != 0), trả về hàm minValue
  - Khi là terminal state, trả evaluationFunction của state
- Hàm maxValue:
  - Duyệt từng action có thể có của state
  - Duyệt từng successor có thể có khi đi action đó
  - Lưu lại tuple (stateValue, action) sao cho stateValue là lớn nhất
- Hàm minValue: Tương tự maxValue, với stateValue là nhỏ nhất

3. Alpha-Beta Pruning

- Tương tự Minimax, nhưng có thêm tham số alpha, beta ở các hàm sử dụng alpha-beta pruning
- Alpha là giá trị tốt nhất của max, beta là giá trị tốt nhất của min
  Tại mỗi hàm maxValue, so sánh value tìm được với beta. Cắt nhánh nếu value > beta, nếu không thì gán lại alpha = max(alpha, value)
  Tại mỗi hàm minValue, so sánh value tìm được với alpha. Cắt nhanh nếu value < alpha, nếu không thì gán lại beta = min(beta, value)

4. Expectimax

- Sử dụng kỳ vọng của các giá trị con của state để quyết định đường đi
- Pacman vẫn gọi hàm maxValue tương tự 2 cách trên, chọn đường đi có value lớn nhất
- Ghost có thể chỉ chọn đường đi suboptimal, nên có thể xác định giá trị suboptimal này bằng kỳ vọng giá trị con: value_các_nhánh_con/số_các_nhánh_con.

5. Better evaluation function

- Phần lớn code giống evaluation function của ReflexAgent
- Không xét theo từng action mà xét theo state
- Có thêm trọng số để tính điểm theo food và ghost, trong đó foodWeight = 1, ghostWeight = 10, phạt nặng hơn trong trường hợp ghost ở gần.
