# Advance_proxyPattern
프록시패턴 공부


## 개요

![image](https://user-images.githubusercontent.com/48795102/146339307-63cbec1e-968b-49ce-9647-9425b35ff45c.png)

- 클라이언트가 요청한 결과를 대리자(proxy)를 통해 간접적으로 요청하는 패턴
  - 접근제어 및 캐싱 , 부가 기능 추가(데코레이터 패턴)을 구현할 수 있음

(프록시 체인으로도 구성될 수 있다)
![image](https://user-images.githubusercontent.com/48795102/146340278-c59b9917-c86a-4382-aee4-d16fa08acbb4.png)

###### 대체 가능성
서버와 프록시가 같은 인터페이스를 사용함으로써 클라이언트는 코드를 변경하지 않고 프록시 객체로 요청을 날릴 수 있음

![image](https://user-images.githubusercontent.com/48795102/146341377-c76d129f-03f0-4f37-a193-9ab658c21bb4.png)



### 1. 프록시 패턴 적용 코드
![image](https://user-images.githubusercontent.com/48795102/146342516-1c21a28c-408e-4276-96cc-bd27025527c4.png)

###### 프록시 패턴 패키지 -> hello.proxy.pureproxy



### 2. 데코레이터 패턴 적용 코드
![image](https://user-images.githubusercontent.com/48795102/146342609-db49c84b-6e23-44fb-a51d-d83064a13c0f.png)

데코레이터 패턴은 여러 프록시를 체이닝 하여 사용할 수 있다. 
![image](https://user-images.githubusercontent.com/48795102/146342850-849020cf-f5bb-4dd9-b767-8fe3e1cc4c43.png)

###### 데코레이터 패턴 패키지 -> hello.proxy.pureproxy.decorator



## 프록시 패턴 vs 데코레이터 패턴
둘을 구분하는 기준은 무엇인가? 
-> 의도(Intent)

 프록시 패턴 : 다른 개체에 대한 접근을 제어하는데 주 목적
 
 데코레이터 패턴 : 객체에 추가 책임(기능)을 동적으로 추가, 기능 확장에 초점
 
