# JavaScript30 - 06 - Type Ahead

---

- javascript에서는 RegExp()를 통해 정규식 obj를 생성할 수 있다

  - RegExp(pattern, flags)
  - pattern
    - 정규 표현식을 나타내는 텍스트, 또는 ES5 이후에서는 다른 RegExp 객체 혹은 리터럴(리터럴의 경우 생성자 표기법에서만 가능). 패턴은 특수 문자를 포함할 수 있어, 일반적인 문자열 리터럴보다 더 넓은 범위의 값을 판별할 수 있습니다.
  - flags
    - (명시되어 있을 경우) 추가할 플래그를 담은 문자열. 기존의 객체를 패턴으로 입력한 경우 그 객체의 플래그가 flags 문자열로 바뀌며, 추가로 lastIndex가 0으로 초기화됩니다 (ES2015 이후). 기존의 정규 표현식 객체를 패턴으로 입력하고 flags를 명시하지 않았을 경우 기존 객체의 플래그(와 lastIndex 값)이 복제됩니다.
    - 종류
      - g : 전체 판별. 처음 일치에서 중단하지 않고, 문자열 전체를 판별합니다.
      - i : 대소문자 무시. u 플래그까지 활성화된 경우, 유니코드 대소문자 폴딩을 사용합니다.
      - m : 여러 줄. 시작 혹은 끝 문자(^과 \$)가 여러 줄에 적용되도록 합니다. 즉, 전체 입력 문자열의 맨 처음과 맨 끝뿐만이 아니라 (\n이나 \r로 구분되는) 모든 줄의 처음과 끝에 적용됩니다.
      - s : "dotAll". . 문자가 줄바꿈을 포함한 모든 문자에 일치합니다.
      - u : 유니코드. 패턴을 유니코드 코드 포인트 열로 처리합니다. (Binary strings 참조)
      - y : sticky. 이 정규 표현식의 lastIndex 속성에 명시된 인덱스에서만 판별하고, 이전/이후 인덱스에서 판별을 시도하지 않습니다.
  - 정규표현식 docs : https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/%EC%A0%95%EA%B7%9C%EC%8B%9D

- String.prototype.match()

  - str.match(regexp)
    - regexp : 정규식 개체입니다. RegExp가 아닌 객체 obj가 전달되면, new RegExp(obj)를 사용하여 암묵적으로 RegExp로 변환됩니다. 매개변수를 전달하지 않고 match()를 사용하면, 빈 문자열:[""]이 있는 Array가 반환됩니다.
  - 문자열이 정규식과 일치하면, 일치하는 전체 문자열을 첫 번째 요소로 포함하는 Array를 반환한 다음 괄호 안에 캡처된 결과가 옵니다. 일치하는 것이 없으면 null이 반환됩니다.

- String.prototype.replace()

  - str.replace(regexp|substr, newSubstr|function)
  - replace() 메서드는 어떤 패턴에 일치하는 일부 또는 모든 부분이 교체된 새로운 문자열을 반환합니다. 그 패턴은 문자열이나 정규식(RegExp)이 될 수 있으며, 교체 문자열은 문자열이나 모든 매치에 대해서 호출된 함수일 수 있습니다.
  - pattern이 문자열 인 경우, 첫 번째 문자열만 치환이 되며 원래 문자열은 변경되지 않습니다.

  ```
    const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';

    const regex = /dog/gi;

    console.log(p.replace(regex, 'ferret'));
    // expected output: "The quick brown fox jumps over the lazy ferret. If the ferret reacted, was it really lazy?"

    console.log(p.replace('dog', 'monkey'));
    // expected output: "The quick brown fox jumps over the lazy monkey. If the dog reacted
  ```
