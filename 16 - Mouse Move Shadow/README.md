# JavaScript30 - 16 - Mouse Move Shadow

---

- Element의 크기를 구하는 방법에는 여러가지가 있다.

  - offsetWidth, clientWidth, scrollWidth, getBoundingClientRect() 등

- offsetWidth, offsetHeight

  - 일반적으로 엘리먼트의 전체 크기를 알고 싶다면, `offsetWidth`와 `offsetHeight` 속성을 가져오면 된다.
    이 속성은 엘리먼트의 패딩과 보더, 스크롤바의 사이즈를 포함한 값을 리턴한다.

- clientWidth, clientHeight

  - 만약, 실제로 보여지고 있는 컨텐츠가 얼마만큼의 공간을 차지하고 있는지 확인하고 싶다면,
    clientWidth와 clientHeight 속성을 사용하는 것이 좋다.

  - 이 속성은 보더와 스크롤바의 크기를 제외한 실제 컨텐츠의 크기를 리턴한다. (패딩은 포함하고 있다)

- scrollWidth, scrollHeight

  - 만약, 보이는 것과 상관 없이 실제 컨텐츠 영역이 얼마만큼의 크기를 갖고 있는지 확인하고 싶다면,
    scrollWidth와 scrollHeight 속성을 확인하면 된다.

  - 이 속성은 전체 스크롤바를 사용하게 되어 숨겨진 영역까지 포함한 크기를 리턴한다.

- getBoundingClientRect()

  - 대부분의 경우엔 `getBoundingClientRect()`은 `offsetWidth`, `offsetHeight`와 거의 같은 값을 리턴한다.
    하지만, `transform`이 적용되어 있다면 조금 달라진다.

  - offsetWidth와 offsetHeight 속성은 엘리먼트의 레이아웃 크기를 리턴하는 반면,
    getBoundingClientRect()는 렌더링된 크기를 리턴한다.

  - 아래와 같은 경우, offsetWidth는 100을 리턴하지만 getBoundingClientRect()는 50을 리턴한다

  ```
    width: 100px;
    transform: scale(0.5);
  ```

  - offsetWidth 뿐 아니라, 위에서 언급한, clientWidth, scrollWidth 모두 tranform에 의해 변경된 값은 적용되지 않는다. 따라서, 최종 렌더링된 값을 가져오고 싶다면, offsetWidth 대신 getBoundingClientRect()를 사용하는 것이 좋다.
