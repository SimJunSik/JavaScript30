# JavaScript30 - 17 - Sort Without Articles

---

- javascript regular expression
  - Regular exppresstion flags
    - g : 전역 검색
    - i : 대소문자 구분 없는 검색
    - m : 다중행(multi-line) 검색
    - s : .에 개행 문자도 매칭(ES2018)
    - u : 유니코드 패턴을 유니코드 코드 포인트의 나열로 취급
    - y : "sticky" 검색을 수행. 문자열의 현재 위치부터 검색을 수행.
    - 정규식에 플래그를 포함시키려면 아래와 같이
    ```
        var re = /pattern/flags;
    ```
    ```
        var re = new RegExp("pattern", "flags")
    ```
  - docs) https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/%EC%A0%95%EA%B7%9C%EC%8B%9D
