# JavaScript30 - 23 - Speech Synthesis

---

- SpeechSynthesisUtterance

  - Web Speech API 의 SpeechSynthesisUtterance인터페이스 는 음성 요청을 나타낸다. 음성 서비스가 읽어야하는 내용과 읽는 방법에 대한 정보 (예 : 언어, 음높이 및 음량)가 포함되어 있다.
  - SpeechSynthesisUtterance.lang :발언 언어를 가져오고 설정
  - SpeechSynthesisUtterance.pitch : 발화를 말할 피치를 가져오고 설정
  - SpeechSynthesisUtterance.rate : 발화가 말하는 속도를 가져오고 설정
  - SpeechSynthesisUtterance.text : 음성을 말할 때 합성 될 텍스트를 가져오고 설정
  - SpeechSynthesisUtterance.voice : 발화에 사용되는 음성을 가져오고 설정
  - SpeechSynthesisUtterance.volume : 발언을 할 음량을 가져오고 설정

  - 이 인터페이스 addEventListener()의 속성에 이벤트 리스너를 지정하거나 할당 하여 이러한 이벤트를 listen
    boundary(onboundary) : 발화가 단어 나 문장 경계에 도달하면 시작
    end(onend) : 발화가 말을 마치면 시작
    error(onerror) : 발화를 성공적으로 말하지 못하게하는 오류가 발생하면 시작
    mark(onmark) : 발화가 명명 된 SSML "mark"태그에 도달하면 시작
    pause(onpause) : 발화가 도중에 일시 중지되면 시작
    resume(onresume) : 일시 정지 된 발언이 재개되면 시작
    start(onstart) : 발언이 시작되기 시작하면 시작
