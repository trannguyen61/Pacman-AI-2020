1. Depth First Search

- Sử dụng stack để lưu trữ: (Trạng thái tiếp theo, đường đi tới trạng thái đó)
- Mỗi khi duyệt 1 node sẽ kiểm tra xem:

* Node là goal state => Return đường đi
* Node không phải goal state và chưa có trong lịch sử: Đánh dấu vào array node đã thăm và push vào stack

2. Breadth First Search

- Sử dụng queue để lưu trữ: (Trạng thái tiếp theo, đường đi tới trạng thái đó)
- Mỗi khi duyệt 1 node sẽ kiểm tra xem:

* Node là goal state => Return đường đi
* Node không phải goal state và chưa có trong lịch sử: Đánh dấu vào array node đã thăm và push vào queue

3. Uniform Cost Search

- Sử dụng priority queue để lưu trữ, lấy cost đến goal là giá trị cần lấy priority
- Lưu trữ: (Trạng thái tiếp theo, đường đi tới trạng thái đó, cost để tới trạng thái đó)
- Mỗi khi duyệt 1 node sẽ kiểm tra xem:

* Node là goal state => Return đường đi
* Node không phải goal state và chưa có trong lịch sử: Đánh dấu vào array node đã thăm và push vào queue

4. A\*

- Giống UCS, nhưng priority là cả cost để tới trạng thái hiện tại + cost từ trạng thái hiện tại tới goal

5. Finding all corners

- getStartState trả lại (trạng thái vị trí, array chứa các góc đã tới)
- Goal state khi trạng thái hiện tại chưa thăm và là góc
- Duyệt từng hướng đi của pacman nếu không chạm tường:

* Không là góc thì push vào array 1 successor gồm (trạng thái, array chứa các góc đã tới)
* Là góc thì push vào array 1 successor gồm (trạng thái, array chứa các góc đã tới + góc vừa duyệt)

6. Corners heuristic

- Trả về cost để đi từ vị trí hiện tại và chạm tất cả corner một cách ngắn nhất sử dụng A\*
- Mỗi lần tới góc thì cập nhật vị trí hiện tại
- Tính khoảng cách từ điểm hiện tại tới góc và chọn góc gần nhất để đi
- Trả về cost ngắn nhất để tới tất cả các góc

7. Eating all the dots

- Sử dụng A\* để trả về giá trị nhỏ nhất có thể để ăn hết food trong bản đồ
- Sử dụng problem.heuristicInfo để lưu trữ giá trị cost ở 1 vị trí để có thể dùng lại nếu duyệt qua node đó
- Priority là cost để đến node đó + cost để đạt goal (ăn hết food)

8. Find path to closest dot

- Dùng UCS có sẵn trong file search.py để tìm
