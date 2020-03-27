# JavaScript30 - 15 - LocalStorage

---

- window.localStorage

  - 읽기 전용 localStorage속성은 사용자 로컬의 Storage객체에 접근하게 해준다. localStorage는 sessionStorage와 비슷하다. 유일한 차이점은 localStorage에 저장된 데이터는 만료 기간이 없지만, sessionStorage에 저장된 데이터는 세션이 끝나면(브라우저가 종료되면) 지워진다는 것이다.

    - Storage 객체는 단순한 key-value 저장소이며, 이는 객체와 비슷하다. 하지만 이 데이터들은 페이지 로딩에도 온전하게 유지된다.
    - Storage.getItem()과 Storage.setItem() 메서드를 사용할 수 있다.
    - 아래 세 줄은 (동일한) colorSetting 엔트리에 값을 설정하는 방법이다.

    ```
        localStorage.colorSetting = '#a4509b';
        localStorage['colorSetting'] = '#a4509b';
        localStorage.setItem('colorSetting', '#a4509b');
    ```

    - sessionStorage는 페이지의 세션이 유지되는 동안 사용할 수 있는 각 origin별로 별도의 스토리지를 관리한다. (페이지 리로딩 및 복원을 포함한, 브라우저가 열려있는 한 최대한 긴 시간 동안)
    - localStorage도 같은 일을 하지만, 브라우저가 닫히거나 다시 열리더라도 유지한다.

  - localStorage또는 sessionStorage에 저장될 데이터는 프로토콜 페이지에 명시되어 있다.

  - 모든 key와 value는 항상 string으로 저장된다. (object와 integer 들은 string으로 자동 변환)

  - Web Storage API는 브라우저에서 쿠키를 사용하는 것보다 훨씬 직관적으로 key/value 데이터를 안전하게 저장할 수 있는 메커니즘을 제공한다.
