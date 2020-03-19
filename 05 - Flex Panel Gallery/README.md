# JavaScript30 - 05 - Flex Panel Gallery

---

- display: flex 로 설정하면 flex-direction: row 가 default
- 현재 div가 display: flex 일 때
  - justify-content 로 가로선 상 정렬
    - flex-start: 요소들을 컨테이너의 왼쪽으로 정렬
    - flex-end: 요소들을 컨테이너의 오른쪽으로 정렬
    - center: 요소들을 컨테이너의 가운데로 정렬
    - space-between: 요소들 사이에 동일한 간격을 둠
    - space-around: 요소들 주위에 동일한 간격을 둠
  - align-items 로 세로선 상 정렬
    - flex-start: 요소들을 컨테이너의 꼭대기로 정렬
    - flex-end: 요소들을 컨테이너의 바닥으로 정렬
    - center: 요소들을 컨테이너의 세로선 상의 가운데로 정렬
    - baseline: 요소들을 컨테이너의 시작 위치에 정렬
    - stretch: 요소들을 컨테이너에 맞도록 늘림
  - flex-direction 으로 컨테이너 안에서 요소들이 정렬해야 할 방향 지정
    - row: 요소들을 텍스트의 방향과 동일하게 정렬
    - row-reverse: 요소들을 텍스트의 반대 방향으로 정렬
    - column: 요소들을 위에서 아래로 정렬
    - column-reverse: 요소들을 아래에서 위로 정렬
  - 자식 div들이 flex: 1 이면 부모 div에 꽉 차게 서로 균등한 공간을 차지
    - 자식 div 마다 flex 값을 조절해서 비율 조절 가능
- 아래와 같이 n번째 자식을 선택해서 css 적용 가능
  ```
    .panel p:nth-child(2) {
    font-size: 4em;
    }
  ```
  ```
    .panel > *:first-child {
      transform: translateY(-100%);
    }
    .panel.open-active > *:first-child {
      transform: translateY(0);
    }
    .panel > *:last-child {
      transform: translateY(100%);
    }
    .panel.open-active > *:last-child {
      transform: translateY(0);
    }
  ```
- addEeventListener에서 transitionend 적용시 원하는대로 안된다면
  callback 함수에서 e.propertyName을 통해 확인
