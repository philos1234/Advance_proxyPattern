
# Advance_proxyPattern
프록시패턴 공부


## 프록시 패턴 개요

![image](https://user-images.githubusercontent.com/48795102/146339307-63cbec1e-968b-49ce-9647-9425b35ff45c.png)

- 클라이언트가 요청한 결과를 대리자(proxy)를 통해 간접적으로 요청하는 패턴
  - 접근제어 및 캐싱 , 부가 기능 추가(데코레이터 패턴)을 구현할 수 있음

(프록시 체인으로도 구성될 수 있다)
![image](https://user-images.githubusercontent.com/48795102/146340278-c59b9917-c86a-4382-aee4-d16fa08acbb4.png)

##### 대체 가능성
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
 
 
 ## 동적 프록시 (Dynamic Proxy)
 ###### 동적 프록시 코드 패키지 ->  hello.proxy.config.v2_dynamicproxy
 
 JDK의 리플렉션(reflection)을 이용해 클래스나 메서드의 메타 정보를 활용하여 프록시를 동적으로 호출
 동적 프록시 기술을 사용하여 프록시 객체를 동적으로 런타임에 만들어 사용 가능
 단, JDK 동적 프록시는 인터페이스를 기반으로 하므로, 인터페이스가 필수이다.
 
 다음과 같은 InvocationHandler를 구현한 Handler를 만들어 사용
 ![image](https://user-images.githubusercontent.com/48795102/146938419-1c38c899-66e1-4ca7-9489-ac85a24ae511.png)

- Object proxy : 프록시 자신
- Method method : 호출한 메서드
- Object[] args: 메서드를 호출할 때 전달한 인수


### 동적 프록시 구성도
![image](https://user-images.githubusercontent.com/48795102/146940415-d87b4b2b-8095-4414-8524-af42b3b9f30a.png)

이와 같이 동적프록시가 InvocationHandler를 호출하는 방식
 
 
 
 
=======
# Advance_proxyPattern
프록시패턴 공부


## Ⅰ. 프록시 패턴 개요

![image](https://user-images.githubusercontent.com/48795102/146339307-63cbec1e-968b-49ce-9647-9425b35ff45c.png)

- 클라이언트가 요청한 결과를 대리자(proxy)를 통해 간접적으로 요청하는 패턴
  - 접근제어 및 캐싱 , 부가 기능 추가(데코레이터 패턴)을 구현할 수 있음

(프록시 체인으로도 구성될 수 있다)
![image](https://user-images.githubusercontent.com/48795102/146340278-c59b9917-c86a-4382-aee4-d16fa08acbb4.png)

##### 대체 가능성
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



### 프록시 패턴 vs 데코레이터 패턴
둘을 구분하는 기준은 무엇인가? 
-> 의도(Intent)

 프록시 패턴 : 다른 개체에 대한 접근을 제어하는데 주 목적
 
 데코레이터 패턴 : 객체에 추가 책임(기능)을 동적으로 추가, 기능 확장에 초점
 
 
 ## Ⅱ. 동적 프록시 (Dynamic Proxy)
 ###### 동적 프록시 코드 패키지 ->  hello.proxy.config.v2_dynamicproxy
 
 JDK의 리플렉션(reflection)을 이용해 클래스나 메서드의 메타 정보를 활용하여 프록시를 동적으로 호출
 동적 프록시 기술을 사용하여 프록시 객체를 동적으로 런타임에 만들어 사용 가능
 단, JDK 동적 프록시는 인터페이스를 기반으로 하므로, 인터페이스가 필수이다.
 
 다음과 같은 InvocationHandler를 구현한 Handler를 만들어 사용
 ![image](https://user-images.githubusercontent.com/48795102/146938419-1c38c899-66e1-4ca7-9489-ac85a24ae511.png)

- Object proxy : 프록시 자신
- Method method : 호출한 메서드
- Object[] args: 메서드를 호출할 때 전달한 인수


### 동적 프록시 구성도
![image](https://user-images.githubusercontent.com/48795102/146940415-d87b4b2b-8095-4414-8524-af42b3b9f30a.png)

이와 같이 동적프록시가 InvocationHandler를 호출하는 방식

 
 
  ## Ⅲ. 스프링이 지원하는 프록시 (Proxy Factory)

타겟 클래스가 인터페이스가 있는 경우에는 JDK 동적 프록시를, 그렇지 않은 경우에는 CGLIB을 이용해야한다. 이 두 기술을 함께 사용하기 위해 스프링에서는 동적 프록시를 편리하게 사용할 수 있도록
프록시 팩토리를 제공한다.

  ![image](https://user-images.githubusercontent.com/48795102/147201739-7b5783ad-c48f-4eea-ac52-e011740a6886.png)
  
이 두 기술을 함께 사용할 때, 부가 기능(데코레이터 프록시)을 적용하기 위해 Advice라는 개념이 도입되었다. 따라서 InvocationHandler(JDK 인 경우)나 MethodInterceptor(CGLIB인 경우)를 신경쓰지 않고 Advice를 호출하면 된다.

![image](https://user-images.githubusercontent.com/48795102/147202093-bf3b1271-ea1e-4b5b-9560-6f7121e393aa.png)


**ProxyTargetClass 옵션을 사용하면 인터페이스가 있어도 CGLIB을 사용하고, 클래스기반 프록시를 사용한다**
 
  ###### 프록시 팩토리 코드 ->  ../test/java/hello/proxy/proxyfactory
