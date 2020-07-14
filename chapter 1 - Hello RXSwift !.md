## chapter 1 : Hello RXSwift !


rx = reactivex = reactive + extension


RxSwift is a library for composing asynchronous and event-based code by using observable sequences and functional style operators, allowing for parameterized execution via schedulers.

관찰 가능한 시퀀스를 사용하여 비동기식 및 이벤트 기반 프로그램을 구성하기 위한 라이브러리 

옵저버 패턴을 사용하여, 여러가지 기능 및 문제를 해결해주는 오퍼레이터 지원.

### 비동기 처리 소개 
1. 버튼 탭 계속 누를 때 
2. 인터넷에서 사진 다운로드 시
3. 디스크에 저장 시 
4. 오디오 음악 재생 시


### Cocoa and UIKit Asynchronous APIs(= Apple에서 제공하던 비동기 코드 API)

모바일 앱 base이기 때문에 비동기처리가 필요

1. Notification center : 디바이스 회전, 키보드 숨김/펼침 과 같은 이벤트 발생 시 실행되는 코드 
2. delegation pattern: 임의의 시간에 다른 클래스나 api 실행시 정의되는 메소드. (ex. remote 알림이 뜰때, 그리고 특정 코드가 언제 수행되거나 얼마나 시간이 걸릴지 모를 때) 
3. GCD: 다수의 일이 한번에 일어나거나, 다른 일들이 서로 다른 우선순위로 이뤄줘야 하는 처리 등
4. closures: 분리된 코드 블록들로 각 클래스 간 코드 실행 여부, 횟수 등을 결정할 수 있다. 

전형적 클래스들의 대부분이 비동기 처리를 하고, 모든 UI component들은 비동기를 상속받는다. 


*그러나, API를 통한 복합적 비동기 코드는 부분적으로 나누어 쓰기가 어렵다.*

###Async한 Code를 짤 때 고민해야할 두가지

1. 코드들의 실행순서
2. 공유되어진 mutable한 데이터 

### 비동기 프로그래밍을 할 때 필요한 용어
* 기본용어를 이해하면 더 쉽게 이해할 수 있다

1. State (Share mutable state): 한 기능을 수행 시, 여러 곳에서 상태가 바뀌는 상황에서 비동기 적인 state를 관리하는 것은 쉽지 않기 때문에 rx에서 이를 해결할 수 있다.

2. 명령형 프로그래밍(Imperative Programming): method명 만으로 각각이 하는 일을 알 수 없으며, 올바른 순서대로 작동하는지 또한 알 수 없다.

3. Side Effect: 각각의 코드에 대해 어떠한 코드가 Side Effect를 일으키는지(단순한 데이터 처리 및 출력 여부)를 알 수 있어야 한다.

4. 선언적 코드(Declarative Code): 
	- 명령형 프로그래밍에선 원하는 대로 상태 변경, 
	- 함수형 코드에서는 Side Effect를 발생시킬 수 없다. 

5. Reactive Systems(반응형 시스템): 
	- 반응(Responsive) : 최신 상태 유지
	- 복원력(Resilient): 각각의 행동은 고유하게 정의, 에러 복구를 위한 유연한 제공
	- 탄력성(Elastic): 다양한 작업 부하 처리
	- 메시지 기반(Message driven): 메시지 기반 통신으로 재사용성 up, 고유 기능 개선
	
	
### Foundation of RXSwift 	
``` Rx의 세가지 구성요소 : Observable, Operator, Schedulers 	```	


+ ObservableType Protocol
 	- next: 최신(다음)값 전송 이벤트
 	- error: Observable이 값을 방출하다 에러 발생 시 이벤트
 	- complete: 성공적으로 이벤트 시퀀스 종료 시킴 (더이상 값 발생 x)
+ Observable 
	- 관찰자 시점으로 실시간 반응,  UI를 업데이트하거나 들어오는 데이터 처리 및 활용 가능


### App architectrue 
Rx와 MVVM이 잘 맞는 이유 : MVVM은 뷰모델이 Observable하게 필요한 데이터를 가져가야 하며, View Model은 View에 대해 아무것도 몰라야 하는 것이 특징. `View와 View Model을 바인딩하기 위한 효과적인 도구가 RxSwift 이다. `
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	


