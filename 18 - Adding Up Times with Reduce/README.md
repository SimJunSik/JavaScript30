# JavaScript30 - 18 - Adding Up Times with Reduce

---

- 문자열로 표현된 시간을 아래와 같이 간단하게 float으로 파싱할 수 있다
  - ex> "04:18"
  ```
      const [mins, secs] = timeCode.split(":").map(parseFloat);
  ```
