# JavaScript30 - 07 - Array Cardio Day 2

---

- Array.prototype.some()
  - 조건식에 만족하는 요소가 하나라도 있다면 true 아니면 false
- Array.prototype.every()
  - 모든 요소가 조건식에 만족하면 true 아니면 false
- Array.prototype.find()
  - 조건식에 해당하는 요소 반환, 없으면 undefined
- Array.prototype.findIndex()
  - 조건식에 해당하는 요소의 index 반환, 없으면 -1
  - index를 통해 어떤 요소를 제거하려면 아래와 같이 slice를 통해 가능
  ```
    const newComments = [
        ...comments.slice(0, commentIndex),
        ...comments.slice(commentIndex + 1)
      ];
  ```
