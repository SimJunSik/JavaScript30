# JavaScript30 - 22 - Follow Along Link Highlighter

---

- 아래처럼 js를 통해 동적으로 element를 만들 수 있다.

```
    const highlight = document.createElement('span');
    highlight.classList.add('highlight');
    document.body.appendChild(highlight);
```

- getBoundingClientRect()

  - JavaScript30 - 16 참고
  - `transform`을 사용하기 때문에 `getBoundingClientRect()` 를 사용해야 한다.

- 'mouseenter' vs 'mouseover'

  - mouseover는 직접 이벤트를 걸지않은 자식요소에 마우스 포인터가 와도 발생하지만 mouseenter는 오로지 자기 자신에게 마우스 포인터가 와야만 발생한다.

  - mouseover 이벤트는 이벤트 버블링\*이 적용되는 이벤트이기 때문에 내부의 div 태그 안에 들어가도 이벤트를 또 다시 발생시킨다. 반면에, mouseenter 이벤트는 문서 객체의 안에 있는지 외부에 있는지만 따지기 때문에 이벤트가 한 번만 발생하게 된다.
    - 캡처링 : window 로부터 이벤트가 발생한 요소까지 이벤트를 전파한다.
    - 버블링 : 이벤트가 발생한 요소부터 window 까지 이벤트를 전파한다.
