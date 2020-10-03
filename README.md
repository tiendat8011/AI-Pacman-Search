# Bài tập Project 1 AI Pacman-Search
## Đề bài :  http://ai.berkeley.edu/search.html

## Điểm autograder
- Question q1: 3/3
- Question q2: 3/3
- Question q3: 3/3
- Question q4: 3/3
- Question q5: 3/3
- Question q6: 0/3
- Question q7: 0/4
- Question q8: 0/3
- **Total**: 15/25

## Question1 
- Duyệt trạng thái bằng thuật toán DFS sử dụng Stack
    - Lấy start statestate và kiểm tra có phải GoalState không. Nếu có thì return [].
    - Khởi tạo 1 stack để lưu những state chuẩn bị xét, state vào sau thì sẽ được xét trước, 1 list visited để lưu những state đã xét.
    - Push start state, path[](để lưu đường đi đến state đó) vào trong stack để bắt đầu duyệt cây statestate.
    - Duyệt state cho đến khi stack empty, pop ra stack cuối cùng mới được thêm và kiểm tra goalState, nếu phải return path[], còn không thì thêm state vào trong visited để duyệt những lần sau không thêm state đã duyệt vào stack.
    - Lặp những trạng thái tiếp theo và hành động đến trạng thái đó và push vào trong stack.

## Question2 
- Giống Question1 nhưng thay stack(LIFO) bằng Queue(FIFO)

## Question3 
- Giống Question1 nhưng thay stack(LIFO) bằng PriorityPriorityQueue với tham số priority = cost đến state đó.
- Khi push vào PriorityQueue thì push object gồm(state, path, cost) và tham số prority.

## Question4 
- Giống Question3 nhưng thay tham số priority = priority + heuristic.

## Question5
- Function getStartState(self) 
    - Return vị trí startState sử dụng startingPosition = startingGameState.getPacmanPosition().

- Function isGoalState(self, state)
    - Lặp các corners có trong corners của mapmap. Nếu corner đã ăn thì append vào list visited các corner đã qua.
    - Nếu đã ăn hết 4 corner thì return true, else return false.

- Function getSuccessors(self, state)
    - Lấy độ dài của dx, dy để đi đến state tiếp theo, khởi tạo độ của state tiếp theo = int(x + dx), int(y + dy).
    - Check xem state tiếp theo có là wall không, nếu không cập nhật tọa độ của nextState.
    - Check nextState đã visited hay không, nếu không thì append vào successor ((tọa độ next_state, list những successer đã visitedvisited), action, cost)
