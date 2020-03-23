# JavaScript30 - 12 - Ket Sequence Detection

---

- Array.prototype.splice()

  - 배열에서 요소를 제거 및 반환하는 함수

  ```
    const a = [0, 1, 2, 3, 4, 5];

    // 2번 배열부터 3개 제거.
    const b = a.splice(2, 3);

    console.log(a); // 결과 : [0, 1, 5]
    console.log(b); // 결과 : [2, 3, 4]
  ```

  - start 값이 - 라면, array의 뒤에서부터 해당 값 만큼부터 시작
