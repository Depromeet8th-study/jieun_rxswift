## Chapter 3: Subjects

> `subject`: 실시간으로 Observable에 값을 추가하고 Subscriber에게 방출할 때에 사용

### Subject Type 
타입 | 특징 
---|:---:
`AysncSubject ` | complete 될 때까지 이벤트는 발생되지 않으며, complete 가 되면 마지막 이벤트를 발생하고 종료된다. 
`PublishSubject ` | **subscribe 된 시점 이후**부터 발생한 이벤트를 전달한다. subscribe 되기 이전의 이벤트는 전달하지 않는다. 
`BehaviorSubject ` | 기본적으로는 publish 와 크게 다르지 않지만 초기 값을 가진 subject이다. subscribe 가 발생하면 즉시 현재 저장된 값을 이벤트로 전달한다. 마지막 이벤트 값을 저장하고 싶을 때 사용한다.
`ReplaySubject ` | n개의 이벤트를 저장하고 subscribe 가 되는 시점과 상관없이 모든 이벤트를 전달한다.


### Hot Observable vs Cold Observable
> 방출 되는 시점에 따라 분류

#### 1. Hot Observable
- 생성과 동시에 이벤트를 방출하기 시작하는 Observable.
- Subscribe 되는 시점과 상관없이 Observer 에게 이벤트를 중간부터 전송한다.

####  2. Cold Observable
- Subscribe 되는 시점부터 이벤트를 생성해 방출한다.

[관련 링크](https://brunch.co.kr/@tilltue/18) 는 여기에 !!


