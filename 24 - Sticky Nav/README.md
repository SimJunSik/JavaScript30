# JavaScript30 - 24 - Sticky Nav

---

- 이 예제에서 구현한 sticky 효과는 `position` property 로도 적용 가능
  - position: sticky
  - top, left, right, bottom 중 하나의 속성 필수
  ```
      nav {
          background: black;
          top: 0;
          width: 100%;
          transition: all 0.5s;
          position: sticky;
          z-index: 1;
      }
  ```
  - 이 예제에서는 nav의 `offsetTop`을 가져와서 `fixed-nav` class를
    add / remove 시키는 방식으로 구현
