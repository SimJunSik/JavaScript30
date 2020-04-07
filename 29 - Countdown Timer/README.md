# JavaScript30 - 29 - Countdown Timer

---

- setTimeout(fn, delay)

  - 일정시간 후 함수를 실행한다.

- setInterval(fn, delay)

  - 일정시간 마다 함수를 실행한다.

- clearInterval(setInterval로 생성된 변수)

  - setInterval로 반복하고 있는걸 멈추게한다.

- Date()

  - 생성방법

    - new Date();
    - new Date(value);
    - new Date(dateString);
    - new Date(year, monthIndex[, day[, hour[, minutes[, seconds[, milliseconds]]]]]);

  - 두 자리 연도는 1900년대로

  ```
    var date = new Date(98, 1); // Sun Feb 01 1998 00:00:00 GMT+0000 (GMT)

    // Deprecated method, 98 maps to 1998 here as well
    date.setYear(98);           // Sun Feb 01 1998 00:00:00 GMT+0000 (GMT)

    date.setFullYear(98);       // Sat Feb 01 0098 00:00:00 GMT+0000 (BST)
  ```

  - 수행시간 측정

  ```
    // Date 객체 사용
    var start = Date.now();

    // 시간이 오래 걸리는 작업을 여기 배치합니다
    doSomethingForALongTime();
    var end = Date.now();
    var elapsed = end - start; // 경과 시간, 밀리초.
  ```

  ```
    // 내장 메서드 사용
    var start = new Date();

    // 시간이 오래 걸리는 작업을 여기 배치합니다.
    doSomethingForALongTime();
    var end = new Date();
    var elapsed = end.getTime() - start.getTime(); // 경과 시간, 밀리초.
  ```
