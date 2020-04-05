# JavaScript30 - 26 - Stripe Follow Along Nav

---

- js를 통해 div에 class를 등록시킬 때, 순서를 주고싶다면 아래와 같이 한다.

```
    this.classList.add('trigger-enter');
    setTimeout(() => this.classList.contains('trigger-enter') && this.classList.add('trigger-enter-active'), 150);
```

- 이번 예제에서는 `transform` 속성을 사용하기 때문에 요소의 크기를 가져올 때
  `getBoundingClientRect()` 를 사용했다.

```
    const dropdownCoords = dropdown.getBoundingClientRect();
    const navCoords = nav.getBoundingClientRect();
```

- css 선택자
  - 하위 선택자
    - .a .b : `div class='a'` 아래에 있는 `div class='b'` 들을 선택
      - 사이에 요소가 더 있어도 상관없다.
      ```
          <div class='a'>
              <div>
                  <div class='b'></div>
              </div>
          </div>
      ```
  - 자식 선택자
    - .a > .b : `div class='a'` 바로 아래에 있는 `div class='b'` 들을 선택
      - 한단계 아래에 있는 자식요소만 선택된다.
      ```
          <div class='a'>
              <div class='b'></div>
          </div>
      ```
  - 형제 선택자
    - .a ~ .b : `div class='a'` 의 형제 요소 중 `div class='b'` 들을 선택
  - 인접 형제 선택자
    - .a + .b : `div class='a'` 의 형제 요소 중 첫번째 `div class='b'` 를 선택
