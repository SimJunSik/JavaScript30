# JavaScript30 - 27 - Click and Drag

---

- css property

  - user-select

    - 브라우저에서 드래그나 더블 클릭을 사용한 텍스트 선택 등을 막으려면 몇 가지 방법이 있다. 자바스크립트를 사용 할 수 있고 CSS에서도 제공하는 user-select를 사용할 수 있다. user-select 사용방법은 아래와 같다.

    ```
        user-select: auto | all | none | text;
    ```

    - user-select는 이처럼 몇 가지 값을 선택할 수 있으며 기본값은 auto

      - auto : Default값으로 브라우저 허용시 텍스트 선택 가능
      - all : 더블클릭이 아닌 클릭 만으로도 선택이 가능
      - none : 텍스트 선택 안됨
      - text : 텍스트 선택이 가능

    - 실제 코드를 적용할 경우 브라우저 호환성을 위해서 아래와 같이 prefix를 많이 사용한다.

    ```
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
    ```

    - 페이지 전체를 선택되지 않게 하려면

    ```
        * {
            user-select: none;
        }
    ```

  - will-change

    - will-change는 변화가 예상되는 요소를 브라우저에게 미리 알려준다. 브라우저는 실제 요소가 변화되기 전에 적절하게 최적화를 할 수 있다. 큰 비용이 드는 변화도 최적화로 인해 페이지의 반응성을 증가시킬 수 있다.

    - will-change 속성은 4가지

      - will-change: auto;
        - 기본값으로 브라우저는 별다른 최적화를 실시하지 않는다.
      - will-change: scroll-position;
        - 스크롤 할 때 엘리먼트의 위치가 변경될 것을 알려준다. 이 값을 설정하면 브라우저는 스크롤 가능한 엘리먼트를 미리 최적화 하여 랜더링 한다. 한 번에 많은 양을 스크롤하거나 빠른 스크롤이 필요한 경우에 사용한다.
      - will-change: contents;
        - 엘리먼트의 컨텐츠가 변경될 것을 알려준다. 브라우저는 보통 엘리먼트의 랜더링 결과를 캐싱한다. 대부분의 엘리먼트가 변경되지 않고 변경되어도 위치가 바뀌는 정도의 미미한 변경만 발생하기 때문이다. 하지만 엘리먼트가 계속해서 변경되는 경우 브라우저 캐시는 무의미하게 된다. 이 속성을 사용하게 되면 캐시를 하지 않고 변경될 때마다 처음부터 랜더링하게 된다.
      - will-change: <custom-ident>;
        - 변경하고 싶은 속성을 사용할 수 있다. 쉼표(,)를 이용하여 두 개 이상의 속성을 사용할 수 있다. 크롬에서는 현재 6가지 속성(opacity, transform, top, left, right, bottom)만 적용된다.

    - 변화가 일어날 요소에 will-change를 직접 선언하면 적용이 되지 않는다.

    ```
        /* 변화할 요소와 will-change가 같이 있으므로 적용이 안 됨 */
        .box {
            transform: rotate(180deg);
            transition: transform 1s linear;
            will-change: transform;
        }
    ```

    - 그러므로 선택자 :hover, 자바스크립트 mouseenter 등을 통하여 미리 알려주어야 합니다.

    ```
        /* hover를 통해서 will-change를 선언 했으므로 적용 */
        .box:hover {
            will-change: transform;
        }
        .box {
            transition: transform 1s linear;
        }
        .box:active {
            transform: rotate(180deg);
        }
    ```

    - css animation 성능에 관한 여러 정보들
      - https://wit.nts-corp.com/2017/06/05/4571

  - perspective

    - perspective 는 사전적의미가 “원근법”으로 여기서도 3D속성이 적용된 요소의 멀고 가까운 상태를 지정할 수 있다. perspective 속성에 숫자값을 지정하게 되면 2D요소를 3D요소처럼 보여지게 원근법이 적용된 모양으로 랜더링된다.

  - nth-child

    - 특정 순서에 있는 요소를 선택할 때 사용하는 선택자다.

    - 형제 요소 중에서 특정 순서에 있는 요소를 선택할 때 사용한다.

    ```
        :nth-child( an+b )
    ```

    - a와 b는 정수입니다. 0과 음수도 가능합니다.

    - n에는 음이 아닌 정수, 즉 0, 1, 2, 3, …이 차례대로 대입됩니다.

    - an+b 대신에 even, odd를 넣을 수도 있습니다.
