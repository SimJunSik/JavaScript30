# JavaScript30 - 20 - Speech Detection

---

- SpeechRecognition

  - 해당 객체를 통해 음성인식을 쉽고 빠르게 사용할 수 있다.
  - SpeechRecognition.lang 을 통해 언어 선택 가능

  ```
      recognition.lang = "en-US";
      recognition.lang = "ko";
  ```

- 해당 예제는 npm install -> npm start 로 서버를 통해 실행해야 편하다.

  - recognition에서 'end' event가 발생할 때 마다 recognition.start() 를 호출하는데,
    서버를 통해 실행하지 않으면 [마이크 허용] dialog가 매번 뜬다.

- 개인적으로 지금까지 제일 재밌었던 예제, 이걸 기반으로 뭔가 재밌는걸 할 수 있을 것 같다.
