# JavaScript30 - 03 - CSS Variables

---

- CSS에서 변수를 사용할 수 있다
  - 변수 선언
    - --변수이름: 변수값;
  - 변수를 정의하면, 변수를 정의한 요소와 그 하위 요소에서 그 변수를 사용할 수 있다.
    만약, 어느 곳에서나 사용할 수 있게 하려면 :root에 정의할 것
  - 변수 사용
    - 속성: var(--변수이름)
- 함수 내부에서 this를 사용할 때, normal function과 arrow function은 다르게 작용한다

  - arrow function은 this뿐만 아니라 arguments, super or new.target도 Binding 하지 않는다
  - arrow function은 자신을 포함하는 외부 scope에서 this를 계승받는다.
    즉, 자신만의 this를 생성하지 않는다. (Lexical this)
  - this.prefix가 (A)에서는 'Hi' 를 나타내지만 (B)에서는 undefined가 찍힌다.

  ```
  function Prefixer(prefix) {
      this.prefix = prefix;
  }

  Prefixer.prototype.prefixArray = function (arr) {
      console.log(this.prefix);// (A)
      return arr.map(function (x) {
          return this.prefix + ' ' + x; // (B)
      });
  };

  var pre = new Prefixer('Hi');
  console.log(pre.prefixArray(['Lee', 'Kim']));
  ```

  - arrow function에서는 내부 함수여도 this가 arrow function이 선언된 곳에서 상위의 context를 가리키므로
    Prefixer객체 pre를 가리키게 된다. 즉, this.prefix가 Hi를 가리켜 개발자가 예상한대로 작동한다.

  ```
  function Prefixer(prefix) {
      this.prefix = prefix;
  }

  Prefixer.prototype.prefixArray = function (arr) {
      return arr.map(x => `${this.prefix}  ${x}`);
  };

  const pre = new Prefixer('Hi');
  console.log(pre.prefixArray(['Lee', 'Kim']));
  ```

  - arrow function을 사용하면 안되는 경우

  1. 객체의 메소드를 정의할 때
  2. 생성자 함수를 정의할 때
  3. addEventListener 함수의 콜백 함수에서 사용하면 this가 상위 context를 가리킴

  - 참고) https://jeong-pro.tistory.com/110
