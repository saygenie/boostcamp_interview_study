# 운영체제

## 동기, 비동기, 블로킹, 논블로킹

### concurrent vs parallel vs distributed

### Synchronous/Asynchronous
> 호출한 함수의 반환값을 받아야 다음 상태로 넘어가는 동기
> 호출한 함수의 반환값과 상관 없이 자신의 일을 진행하는 비동기

Synchronous/Asynchronous는 호출되는 함수의 작업 완료 여부를 누가 신경쓰냐가 관심사다.
호출되는 함수에게 callback을 전달해서, 호출되는 함수의 작업이 완료되면 호출되는 함수가 전달받은 callback을 실행하고, 호출하는 함수는 작업 완료 여부를 신경쓰지 않으면 Asynchronous다.
호출하는 함수가 호출되는 함수의 작업 완료 후 리턴을 기다리거나, 또는 호출되는 함수로부터 바로 리턴 받더라도 작업 완료 여부를 호출하는 함수 스스로 계속 확인하며 신경쓰면 Synchronous다.


### Blocking / Non-Blocking

Blocking : 작업 완료 후, 반환.
Non-Blocking : 작업 완료 전이더라도, 반환해 줌.

## 1. Sync blocking

[과정]
1. client가 vendor에게 req를 날린다
2. vender는 연산 결과를 다 마치고 나서야 반환을 해준다.
3. client는 반환값을 받아야 다음 일을 처리하기 때문에, 아무일도 못함.
4. 드디어 vendor가 값을 반환해주고 다음 일을 처리한다.

## 2. Async blocking
[과정]
1. client가 vendor에게 요청
2. client는 callback이 오면 그냥 수행하기 때문에, 신경 안쓰고 작업 수행
3. 그런데, vendor는 blocking이어서 완료시까지 반환해주지 않는다.
4. 완료 후, callback() 함수가 수행되고 해당 task 종료.

그렇기 때문에, 가장 쓸모 없는 방식.

## 3. Sync-nonblocking
1. client가 vendor에게 요청
2. vender는 nonblocking이기 때문에, 바로 값을 반환해준다.
3. 그런데 작업 처리가 미완이라면, 특정 플래그를 줘서 완료 여부를 식별 (EWOULDBLOCK이 미완료)
4. 일단, 반환 값을 받았기 때문에, 다른 일을 수행할 수 있다.
5. 하지만 완료시켜야 하기 때문에, 계속해서 vendor에게 질의를 던진다. 이 과정을 polling 이라고 한다.
6. 완료 메시지가 vendor에게서 오면 끝

![img](https://t1.daumcdn.net/cfile/tistory/253D9E475516150118)
### NonBlocking-Sync

앞에서 살펴본대로 조합해보면 NonBlocking-Sync는 호출되는 함수는 바로 리턴하고, 호출하는 함수는 작업 완료 여부를 신경쓰는 것이다. 신경쓰는 방법이 기다리거나 물어보거나 두 가지가 있었는데, NonBlocking 함수를 호출했다면 사실 기다릴 필요는 없고 물어보는 일이 남는다.
즉, NonBlocking 메서드 호출 후 바로 반환 받아서 다른 작업을 할 수 있게 되지만, 메서드 호출에 의해 수행되는 작업이 완료된 것은 아니며, 호출하는 메서드가 호출되는 메서드 쪽에 작업 완료 여부를 계속 문의한다.


## Nonblocking-Async

[ref](https://homoefficio.github.io/2017/02/19/Blocking-NonBlocking-Synchronous-Asynchronous/)


![](https://i.imgur.com/dUMM3XZ.png)
![](https://i.imgur.com/P7ENl70.png)
![](https://i.imgur.com/pETOK8L.png)
![](https://i.imgur.com/7L70rsF.png)
---
