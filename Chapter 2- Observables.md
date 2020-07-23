# Chapter 2: Observables


## 1. what is an observable?
 : 이벤트 시퀀스를 비동기적으로 생성하는 기능. 이 때 Observable이 지속적으로 이벤트를 발생시키는 것을 emit라고 한다.

### Lifecycle Of an observable
이벤트 | 특징 
---|:---:
`next ` | 다음(최신) 값을 전송하는 이벤트
`error ` | Observable이 값을 배출하다 에러 방출 시,  ``error`` 를 emit 후 종료하는 이벤트
`complete ` | 성공적으로 이벤트 시퀀스를 종료시키는 이벤트. 더이상 값을 emit 하지 않는다.



![completed](./img/completed.png)
next를 통해 1,2,3을 emit 하는 Observable

![error]( ./img/error.png)
세번의 tap 이벤트를 emit후, complete 를 통해 종료되는 Observable



