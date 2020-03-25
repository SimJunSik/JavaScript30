# JavaScript30 - 13 - Slide in on Scroll

---

- lodash

  - 자바스크립트 유틸리티 라이브러리
  - 유틸리티 라이브러리로 array, collection, date, number, object 등이 있으며, 데이터를 쉽게 다룰 수 있도록 도와준다.
    ex> 배열 안에 중복 값을 제거하기 / object 배열 안에 특정 값만 추출하기 etc.
  - 특히, 자바스크립트에서 배열 안의 객체들의 값을 핸들링할때 유용하다.
  - 자주 사용되는 기능

    - filter

      - 배열 안에 요소들 중, 특정 값만 filter하고 싶을때 사용

      ```
          var users = [
              { 'user': 'barney', 'age': 36, 'active': true },
              { 'user': 'fred',   'age': 40, 'active': false }
          ];

          _.filter(users, function(o) { return !o.active; });
          // => objects for ['fred']

          _.filter(users, { 'age': 36, 'active': true });
          // => objects for ['barney']

          _.filter(users, ['active', false]);
          // => objects for ['fred']

          _.filter(users, 'active');
          // => objects for ['barney']
      ```

    - map

      - 배열 안에 객체들의 요소 중, 특정 요소만 빼서 배열로 만들고 싶은 경우 사용

      ```
          var users = [
              { 'user': 'barney' },
              { 'user': 'fred' }
          ];

          _.map(users, 'user');
          // => ['barney', 'fred']
      ```

    - uniqBy
      - 배열 안에 객체들의 요소 중복을 제거하고 싶을 때 사용 (추가로, uniq 함수는 배열의 중복을 제거)
      ```
          _.uniqBy([{ 'x': 1 }, { 'x': 2 }, { 'x': 1 }], 'x');
          // => [{ 'x': 1 }, { 'x': 2 }]
      ```
    - 외에도 굉장히 많음

  - 공식문서 : https://lodash.com/docs/4.17.15

- 해당 예제에서는 lodash의 debounce를 가져다 쓰지 않고 직접 구현함

  - debounce() 메소드는 이벤트에 의해 특정 함수가 여러번 반복 실행될 수 경우에 사용하며 정해진 지연시간동안 반복된 호출을 딱 1번만 호출하도록 제어해준다.

  - 해당 예제에서는 scroll이 너무 빈번하게 일어나지 않게 하기위해 wait값 만큼 delay를 준다.

  - 해당 예제의 debounce() 로직에 대해 확실하게 익히기
