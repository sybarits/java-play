# 자동차 경주 게임

* 이 게임은 nextstep에서 진행한 교육을 들으면서 작성한 게임이다.
* 자동차 경주게임을 구현했다. 
* 게임의 자세한 설명은 기능 요구 사항과 구현 기능 목록을 참고한다.

## 프로그램 특징

* Event Driven Architecture를 가진다.
* Application에 main 메소드가 있다.
* GameStatus에 이벤트가 정의 되어 있다.
* GameControll에 각 이벤트에 수행되어야 할 메소드들이 정의 되어있다.
* ControllerMapper에 event와 수행할 함수를 맵핑한다.
* Method Reference를 위해 Service에 FunctionalInterface로 인터페이스를 정의한다. 여기에서 모든 Exception 처리를 일괄 하도록 한다.
* Test code 를 작성하였다.



## 기능 요구 사항

* 기본적으로 1부터 9까지 서로 다른 수로 이루어진 3자리의 수를 맞추는 게임이다.
* 같은 수가 같은 자리에 있으면 스트라이크, 다른 자리에 있으면 볼, 같은 수가 전혀 없으면 포볼 또는 낫싱이란 힌트를 얻고, 그 힌트를 이용해서 먼저 상대방(컴퓨터)의 수를 맞추면 승리한다.
* e.g. 상대방(컴퓨터)의 수가 425일 때, 123을 제시한 경우 : 1스트라이크, 456을 제시한 경우 : 1볼 1스트라이크, 789를 제시한 경우 : 낫싱
* 위 숫자 야구 게임에서 상대방의 역할을 컴퓨터가 한다. 컴퓨터는 1에서 9까지 서로 다른 임의의 수 3개를 선택한다. 
* 게임 플레이어는 컴퓨터가 생각하고 있는 3개의 숫자를 입력하고, 컴퓨터는 입력한 숫자에 대한 결과를 출력한다.
* 이 같은 과정을 반복해 컴퓨터가 선택한 3개의 숫자를 모두 맞히면 게임이 종료된다.
* 게임을 종료한 후 게임을 다시 시작하거나 완전히 종료할 수 있다.


## 구현 기능 목록
* 자동차 이름을 사용자로부터 입력 받아 파싱 후 유효성 체크하고 저장
  * 자동차 리스트를 저장하는 클래스
  * 자동차 하나의 정보를 저장하는 클래스
  * 자동차 이름을 저장하는 래퍼 클래스
* 사용자로부터 자동차가 몇번 움직일 것인지 입력받고 유효성 체크 및 저장
  * 자동차가 움직일 정보를 저장하는 래퍼 클래스 
* 자동차가 랜덤 숫자에 따라 진행하거나 멈추는 기능
* 우승자를 판단하여 출력
* 에러처리
  * 람다를 랩핑하는 클래스
* 위와 같은 동작들을 제어하는 클래스와 게임 상태를 저장하는 클래스



## 게임 실행 예시

```
경주할 자동차 이름을 입력하세요(이름은 쉼표(,)를 기준으로 구분).
pobi,crong,honux
시도할 회수는 몇회인가요?
5

실행 결과
pobi : -
crong : -
honux : -

pobi : --
crong : -
honux : --

pobi : ---
crong : --
honux : ---

pobi : ----
crong : ---
honux : ----

pobi : -----
crong : ----
honux : -----

pobi : -----
crong : ----
honux : -----

pobi, honux가 최종 우승했습니다.
```

## 과제 제출 과정
* [과제 제출 방법](https://github.com/next-step/nextstep-docs/tree/master/precourse)