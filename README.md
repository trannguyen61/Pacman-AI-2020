1. Xác suất ở mỗi vị trí ma xuất hiện 
allPossible[p] = emissionModel[trueDistance] * self.beliefs[p]
xác suất noise dựa trên khoảng cách mahattan của pacman với ghost * xác suất ghost xuất hiện mỗi vị trí

2. xác suất ghost xuất hiện vị trí kế tiếp
allPossible[newPos] += prob * self.beliefs[oldPos]
= xác suất ở vị trí hiện tại * xác suất vị trí tiếp theo 

3. tính xác suất xuất hiện của ghost ở 1 vị trí
currentGhostDistribution[ghostPos]
tính khoảng cách giữa vị trí hiện tại với ghost gần nhất 
distGhost = self.distancer.getDistance(nPos, ghostp) 

4. 
initializeUniformly: tìm các particle
getBeliefDistribution: khởi tạo xác suất cho các particle 
observe: xác suất noise dựa trên khoảng cách mahattan của pacman với ghost * xác suất ghost xuất hiện mỗi vị trí
khởi tạo lại tập mẫu nếu xác suất ở các vị trí đều = 0

5. xác suất ở vị trí hiện tại * xác suất vị trí tiếp theo 