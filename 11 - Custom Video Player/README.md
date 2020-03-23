# JavaScript30 - 11 - Custom Video Player

---

- video 의 주요 event 4가지

  - click
  - play
  - pause
  - timeupdate

- video의 주요 속성들

  - video.paused
  - video.currentTime
  - video.duration

- 다음과 같은 형태로 video를 play/pause 시킬 수 있다

```
  const method = video.paused ? "play" : "pause";
  video[method]();
```

- flex-basis

  - 플렉스 아이템의 초기 크기를 지정
  - box-sizing을 따로 지정하지 않는다면 콘텐츠 박스의 크기를 변경

  ```
      /* <'width'> 지정 */
      flex-basis: 10em;
      flex-basis: 3px;
      flex-basis: auto;

      /* 원본 크기 키워드 */
      flex-basis: fill;
      flex-basis: max-content;
      flex-basis: min-content;
      flex-basis: fit-content;

      /* 플렉스 아이템 내용 크기에 따라 조절 */
      flex-basis: content;

      /* 전역 값 */
      flex-basis: inherit;
      flex-basis: initial;
      flex-basis: unset;
  ```
