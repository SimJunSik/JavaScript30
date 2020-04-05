# JavaScript30 - 25 - Event Capture, Propagation, Bubbling and Once

---

- Event Bubbling

  - 예제에서 `div class='three'` 를 클릭하면 console창에 three -> two -> one 이 전부 출력
  - div 태그 한 개만 클릭했을 뿐인데 왜 3개의 이벤트가 발생되는 걸까? 그 이유는 브라우저가 이벤트를 감지하는 방식 때문이다.
  - 브라우저는 특정 화면 요소에서 이벤트가 발생했을 때 그 이벤트를 최상위에 있는 화면 요소까지 이벤트를 전파시킨다. 따라서, 클래스 명 three -> two -> one 순서로 div 태그에 등록된 이벤트들이 실행된다.
  - 여기서 주의해야 할 점은 각 태그마다 이벤트가 등록되어 있기 때문에 상위 요소로 이벤트가 전달되는 것을 확인할 수 있다. 만약 이벤트가 특정 div 태그에만 달려 있다면 위와 같은 동작 결과는 확인할 수 없다.
  - 이와 같은 하위에서 상위 요소로의 이벤트 전파 방식을 이벤트 버블링(Event Bubbling)이라고 한다.
    “Trigger clicks all the way up”

- Event Capture

  - 이벤트 캡쳐(Event Capture)는 이벤트 버블링과 반대 방향으로 진행되는 이벤트 전파 방식이다.
  - addEventListener() API에서 옵션 객체에 capture:true를 설정해주면 된다. 그러면 해당 이벤트를 감지하기 위해 이벤트 버블링과 반대 방향으로 탐색한다.
    - 기본값은 capture: false
    ```
        div.addEventListener("click", logText, {
            capture: true,
            once: false,
        })
    ```
    - 여기서 once: true로 설정하면 해당 이벤트는 한 번만 실행된다.
  - capture: true 인 상태에서 `div class='three'` 를 클릭하면 one -> two -> three 순으로
    즉, 최상위 부모부터 이벤트들이 실행된다.(Bubbling과 반대)

- 위와 같은 현상들이 발생하는걸 방지하고 싶다면 아래와 같이 stopPropagtion()을 사용한다.

  ```
      function logText(e) {
          console.log(this.classList.value);
          // e.stopPropagation(); // stop bubbling!
          // console.log(this);
      }
  ```

- Event Delegation(이벤트 위임)

  - 앞에서 살펴본 이벤트 버블링과 캡쳐는 사실 이벤트 위임을 위한 선수 지식이라고 해도 과언이 아니다. 이벤트 위임은 실제 바닐라 JS로 웹 앱을 구현할 때 자주 사용하게 되는 코딩 패턴이다.
  - 이벤트 위임을 한 문장으로 요약해보면 ‘하위 요소에 각각 이벤트를 붙이지 않고 상위 요소에서 하위 요소의 이벤트들을 제어하는 방식’이다.
  - 아래와 같이 한다면 js를 통해 새로운 요소를 추가했을 때, 새로 추가한 요소에는 이벤트가 적용되지 않음
    - input들에 직접 이벤트를 걸어주는 방식

  ```
      <h1>오늘의 할 일</h1>
      <ul class="itemList">
          <li>
              <input type="checkbox" id="item1">
              <label for="item1">이벤트 버블링 학습</label>
          </li>
          <li>
              <input type="checkbox" id="item2">
              <label for="item2">이벤트 캡쳐 학습</label>
          </li>
      </ul>
  ```

  ```
      var inputs = document.querySelectorAll('input');
      inputs.forEach(function(input) {
          input.addEventListener('click', function(event) {
              alert('clicked');
          });
      });
  ```

  ```
      // 새 리스트 아이템을 추가하는 코드
      var itemList = document.querySelector('.itemList');

      var li = document.createElement('li');
      var input = document.createElement('input');
      var label = document.createElement('label');
      var labelText = document.createTextNode('이벤트 위임 학습');

      input.setAttribute('type', 'checkbox');
      input.setAttribute('id', 'item3');
      label.setAttribute('for', 'item3');
      label.appendChild(labelText);
      li.appendChild(input);
      li.appendChild(label);
      itemList.appendChild(li);
  ```

  - 아래처럼 input들에 직접 이벤트를 거는 것이 아니라 상위 요소인 ul에 이벤트를 걸어주면 해결된다.
    - 이벤트 버블링을 이용한 것이다.
    - 이렇게만 작성하면 ul의 모든 자식요소들 즉, label에도 해당 이벤트가 걸리기 때문에
      input에만 걸리도록 개선해야 한다.

  ```
      var itemList = document.querySelector('.itemList');
      itemList.addEventListener('click', function(event) {
          alert('clicked');
      });
  ```
