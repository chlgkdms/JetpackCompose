## Compose

: Jetpack Compose는 Android를 위한 현대적인 선언형 UI 도구 키트

명령형으로 변환하지 않고도 앱 UI를 렌더링할 수 있게 하는 선언형 API 제공

 ➡️ 앱 UI를 더 쉽게 작성하고 유지관리할 수 있도록 지원

### 선언형 프로그래밍 패러다임

지금까지 Android 뷰 계층 구조는 UI 위젯의 트리로 표시할 수 있었음

사용자 상호작용 등의 이유로 앱의 상태 변경 시,

현재 데이터를 표시하기 위해 UI 계층 구조를 업데이트해야함

UI를 업데이트하는 가장 일반적인 방법은 

```java
findViewbyId()
```

와 같은 함수를 사용하여 트리를 탐색하고 메소드를 호출해 변경하는 것이였음

But, 뷰를 수동으로 변경하면 오류 발생 가능성 ⬆️

또한 두 업데이트가 예기치 않은 방식으로 충돌할 경우 잘못된 상태를 야기하기도 쉬움



이러한 이유들로 인해, Android는 선언형 UI 모델로 전환하기 시작

선언형 UI 모델로 전환할 경우,

처음부터 화면 전체를 개념적으로 재생성한 후 필요한 변경사항만 적용하는 방식으로 작동.

### 간단한 구성 가능한 함수

![mmodel-simple](https://developer.android.com/static/images/jetpack/compose/mmodel-simple.png?hl=ko)

Compose를 사용하면 데이터를 받아서 UI 요소를 내보내는 *구성 가능한* 함수 집합을 정의하여 사용자 인터페이스를 빌드할 수 있음

- 함수는 `@Composable` 주석으로 주석이 지정. 

  모든 구성 가능한 함수에는 이 주석이 있어야 함

  이 주석은 이 함수가 데이터를 UI로 변환하기 위한 함수라는 것을 Compose 컴파일러에알림

- 함수는 데이터를 받음 

  구성 가능한 함수는 매개변수를 받을 수 있으며 이 매개변수를 통해 앱 로직이 UI를 형성할 수 있음

  이 예에서 위젯은 사용자의 이름을 부르면서 환영할 수 있도록 `String`을 받음

- 함수는 UI에 텍스트를 표시 

  이를 위해 실제로 텍스트 UI 요소를 생성하는 `Text()` 구성 가능한 함수를 호출

  구성 가능한 함수는 다른 구성 가능한 함수를 호출하여 UI 계층 구조를 내보냄

- 함수는 아무것도 반환하지 않음 

  UI를 내보내는 Compose 함수는 UI 위젯을 구성하는 대신 원하는 화면 상태를 설명하므로 아무것도 반환할 필요가 없음.
