# NetWork
1. [인터넷이란?](#인터넷이란)
2. [프로토콜이란?](#프로토콜이란)
3. [네트워크 가장자리(network edge)](#네트워크-가장자리network-edge)
4. [네트워크 코어(중심부/network core)](#네트워크-코어중심부network-core)
5. [프로토콜 계층과 서비스 모델](#프로토콜-계층과-서비스-모델)





# 인터넷이란?
## 인터넷의 구성요소
1.  네트워크의 가장자리(network edge)

    * 컴퓨터 or 서버 -> ("host" or "end system")이라 부름

2.  네트워크 코어(network core)

    * 라우터(스위치) : 사용자에게 전달되어야할 메시지를 목적지에 찾아갈 수 있게 하는 역할


3. 링크 : 물리적인 실제 회선  

<br/>

* 인터넷(Internet) : 네트워크들 속에서의 네트워크 -> 즉 네트워크들이 모인 곳에서의 네트워크를 말함

### 프로토콜(Protocols) : 인터넷에서 메시지를 보내고 받는 규칙

  * 인터넷 통신을 하기 위해서는 프로토콜 표준화가 매우 중요함

  * ex) TCP, IP, HTTP, Skype, 802.11 ...

### 인터넷 표준화(Internet standards)

  * IETF(Internet Engineering Task Force) : 인터넷 프로토콜의 표준화 기관

  * RFC(Request for comments) : IETF에서 RFC라는 표준안을 발표함

<br/>

# 프로토콜이란?
보내고 받는 메시지의 형식(format), 순서(Order), 액션(action)을 정의(약속)한다. 

<br/>

# 네트워크 가장자리(network edge)
* 종단 시스템(end system) : 인터넷에 연결되는 컴퓨터와 다른 장치들은 인터넷의 가장자리를 차지하고 있기 때문에 end system이라 한다.

	* ex) **데스크톱**(데스크톱 PC, 매킨토시, 리눅스 컴퓨터...), **서버**(웹과 전자메일 서버), **모바일 컴퓨터**(스마트폰, 태블릿, 랩톱)...

* 호스트(host) : 네트워크 애플리케이션을 호스팅하고 있는 end system을 지칭하는 말

	* 클라이언트 와 서버로 구분 

## 접속 네트워크(access network)
host 혹은 end system들을 네트워크에 연결시켜주는 놈

### access network를 구분짓는 요소

1. bandwidth(대역폭)
   
2. 다른 사람과 공유를 하는지 공유 유무

### access network 종류

1. DSL : Digital Subscriber Line, 전화선을 이용한 인터넷 서비스, 현재는 잘 쓰이지 않음

2. 케이블(cable) network : 케이블로 연결한 네트워크 서비스

3. home network : 집 내부에 구성하고 있는 네트워크
   1. 데스크톱을 home network 연결 -> home network을 케이블회사 or DSL(전화회사) 연결

4. 무선(Wireless) 네트워크
   1. 무선 랜(LAN) : 802.11b/g(WiFi)
   2. 광대역 무선 네트워크 : 셀룰러(3G, 4G, LTE)

<br/>

# 네트워크 코어(중심부/network core)
source에서 destination으로 사용자의 애플리케이션 메시지를 전달해 주는 것이 목표이다.  

### 전달해 주는 방식
1. 회선교환(packet switching)

2. 패킷교환(circuit switching )

## 회선교환(circuit switching)
<img width="431" alt="스크린샷 2022-08-05 오후 12 38 50" src="https://user-images.githubusercontent.com/87526189/183372743-f44c2142-350b-4979-ab7b-1778c9cafc70.png">  

주로 전화 네트워크에서 사용되는 방식으로 user가 call을 하면 call set up 과정을 거쳐서 둘 사이에 파이프로 연결된 것 처럼 연결할 수 있다.

### call set up에서 하는 일
1. source -> destination 전달되는 경로를 결정함(어떤 라우터 스위치를 경유할 것인지)
 
2. 그 경로상의 자원이 예약됨

경로상의 자원은 한정적이기 때문에 분할하여 여러사용자가 사용할 수 있도록 한다.

### 네트워크 자원을 분할하는 방법
1. FDM(frequency division multiplexing) : 주파수 분할 다중화

	* 주파수 대역폭을 기준으로 사용자별로 다른 대역을 할당해 준다

2. TDM(Time division multiplexing) : 시 분할 다중화 

	* 링크에 가용한 대역폭 전체를 사용자들이 사용할 수 있게 하되 시간을 기준으로 잘라서 시간을 할당함

## 패킷교환(packet switching)
circuit switching은  전화에서는 지속적인 연결이 필요하므로 적합했지만 컴퓨터 간의 통신에서는 데이터 네트워크인 인터넷에서는 Request가 올 때는 대량의 데이터가 발생하지만 한 동안은 데이터가 발생하지 않는다.  

따라서 circuit switching은 인터넷과 같은 데이터 네트워크에서는 비효율적이다. 그래서 등장하게 된 것이 packet switcing이다.

### 패킷교환(packet switcing)의 주요 개념
1. 예약이 없다. -> No call set up / No resource reservation
	* 필요가 발생하면 그때그때 마다 resource를 사용할 수 있게 한다.

2. 데이터를 패킷으로 잘라야한다.

3. 패킷의 목적지 주소가 명시되어 있어야한다.(예약어가 없기 때문)
	* 라우터는 패킷을 받으면 패킷의 목적지 주소를 보고 다음 라우터의 위치를 결정한다.  

4. 저장 후 전달 전송(store-and-forward)
	* 각 라우터는 패킷 하나를 다 받아야지만 목적지 정보를 파싱하고 다음 위치로 보낼 수 있기 때문에 패킷 전체가 도달 할 때 까지는 일단 받는 작업만 한다.

### 큐잉지연(queueing delay) 과 패킷 손실(loss)
패킷 스위치는 출력 버퍼를 가지고 있고, 링크로 송신하려는 패킷을 저장하고 있다.  

패킷이 한 링크로 전송하려고 했는데 그 링크가 다른 패킷을 전송하고 있다면, 도착한 패킷은 출력 버퍼에서 대기한다.  

이때 패킷은 출력버퍼에서 큐잉지연(queueing delay)을 겪게된다.  

버퍼의 공간은 유한하기 때문에 패킷으 로 꽉 차있을 수 있으며 이 경우 다른 패킷이 도착하면 패킷손실(packet loss)가 발생한다.  

<br/>

# 프로토콜 계층과 서비스 모델
인터넷은 매우 복잡한 시스템이다.  

인터넷은 다양한 애플리케이션과 프로토콜, 여러가지 종단 시스템(End System)과 종단 시스템 간의 연결, 라우터, 다양한 링크 수준의 매체가 있음을 보았다. 

이러한 복잡한 네트워크 구조를 어떻게 조직화 할 수 있을까?  

## 계층구조(layering)
프로토콜은 매우 방대하고 복잡하기 때문에 계층구조로 되어있다. 

### 계층구조의 장점
1. 복잡한 시스템의 조각들을 식별하고 그것들 관의 관계를 정의하는 것이 용이해진다.  

2. 업데이트와 유지보수가 쉬워진다.

    * 방대한 프로그램을 하나의 함수로 구현하면 유지보수하기 어려울 것이다. 하지만 기능별로 나눠서 함수로 구현하게 되면 유지보수하기 용이해질 것이다. 마찬가지로 방대한 프로토콜 시스템을 계층으로 나누면 유지보수와 업데이트하기 쉬워진다.

### 계층구조의 단점
1. 계층의 기능을 독립적으로 계층의 목적을 정의하고 목적에 맞춰서 기능을 구현하다보면 그 기능들 간에는 서로 겹쳐지는 부분이 발생할 수 있다.

2. 한 계층에서 최적으로 작동하기 위해서는 다른 계층에서 수집하고 있는 정보나 다른 계층에서만 알려지게되는 정보를 필요로 할 수 있다. 그럴때 엄격하게 계층을 구분해 놓으면 두 계층간에 커뮤니케이션이 있어야만 다른 계층에서 발생한 정보를 가져올 수 있기 때문에 오버헤드가 발생할 수 있다. 
 
     * -> 즉 어떤 계층의 기능을 구현하는 것이 최적이지 않을 수 있다.

### 인터넷의 5개 계층의 프로토콜 스택

![image](https://user-images.githubusercontent.com/87526189/183373019-709901a2-835a-4f8b-9bb6-d76a08aaa002.png)

1. 애플리케이션(application) : 네트워크 애플리케이션 프로그램을 지원하는 역할

    * 유저가 애플리케이션 프로그램에서 발생시킨 데이터를 어떻게 메시지로 만드느냐 하는 것이 애플리케이션 계층의 주된 역할

    * ex) web 애플리케이션 -> HTTP라는 프로토콜이 web 애플리케이션 프로그램을 지원하고 있다.

    * ex) email -> SMTP프로토콜

    * ex) 파일전송(file transfer) -> FTP

2. 트랜스포트(transport)

    * 애플리케이션 프로그램에서 만들어진 메시지를 목적지 프로그램으로 전달해주는 역할

    * process to process 전송을 수행하는 계층

    * TCP와 UDP라는 트랜스포트 프로토콜이 있음

3. 네트워크(network)

    * 트랜스포트 계층에서 process to process 전송을 수행하기 위해 host to host 전송을 네트워크 계층에게 부탁함

    * 라우팅(길찾기)을 통해 source host(SH)로 부터 destination host(DH)까지 배달해줌

4. 링크(link)

    * SH에서 DH까지 배달하기 위해서 hop by hop으로 네트워크 노드를 거쳐가야한다. 한 hop 전달하는 것을 링크에게 부탁함

5. 물리(physical)
   
    * 링크 계층에서 한 hop을 건너가기 위해 물리계층에게 transmission medium에다가 데이터를 실어 나르는 일을 부탁함

각 계층은 바로 아래 계층의 서비스를 이용하여 자신의 프로토콜 계층의 목표를 달성하게 된다.  

### **OSI 7계층의 모델**
위 프로토콜 스택이 유일한 프로토콜 스택이 아니다.  

1970년대 후반 ISO(International Organization for Standardization)은 컴퓨터 네트워크가 7계층으로 구성되어야 한다는 제안을 했는데 이를 OSI(Open System Interconnection)라고 부른다.

![image](https://user-images.githubusercontent.com/87526189/183402540-3b432c41-193a-4230-80ab-66c55f3d7ca2.png)

이들 계층 중 5개 계층의 기능은 비슷하게 이름 붙여진 인터넷 계층과 거의 비슷하 다. 따라서 OSI 참조 모델에 있는 2개의 추가 계층들(프레젠테이션 계층과 세션 계층) 만 살펴본다.

1. 프레젠테이션 계층 : 통신하는 애플리케이션들이 교환되는 데이터의 의미를 해석하도록 하는 서비스를 제공하는 것이다. 이들 서비스는 데이터 기술 뿐만 아니라 데이터 압축과 데이터 암호화를 포함한다.

2. 세션 계층 : 데이터 교환의 경계와 동기화를 제공한다. 이에는 체킹포인트와 회복 방법을 세우는 수단을 포함한다.

인터넷이 OSI참조 모델에서 찾을 수 있는 2개 계층이 없다는 사실은 두 가지 질문을 하게 만든다.  

1. 이들 계층이 제공하는 서비스는 중요하지 않은가?

2. 애플리케이션이 이 두 서비스중 하나를 요구하면 어떻게 되는가? 

<br/>

이에 대한 대답은 애플리케이션 개발자에게 달려있다.  

그 서비스 가 종요하다면 기 기능을 애플리케이션에 넣는 것은 애플리케이션 개발자에게 달려있다.
 
## 캡슐화(Encapsulation)
![스크린샷 2022-08-08 오후 8 04 58](https://user-images.githubusercontent.com/87526189/183404129-28e76109-c366-4940-a409-80322f1d575d.png)

### 세그먼트
애플리케이션 계층 메시지는 트랜스포트 계층으로 보내진다.  

트랜스포트 계층은 메시지에 수신 측 트랜스포트 계층에서 사용될 추가 정보(헤더 정보)를 더한다.  

애플리케이션 계층 메시지와 트랜스포트 계층 헤더정보는 모두 트랜스포트 계층 세그먼트를 구성한다.

트랜스포트 계층 세그먼트는 애플리케이션 계층 메시지를 캡슐화한다.

### 데이터그램
트랜스포트 계층은 세그먼트를 네트워크 계층으로 보내며 네트워크 계층은 출발지와 목적지 종단 시스템 주소와 동일한 헤더 정보를 추가하여 네트워크 계층 데이터그램을 만든다

### 프레임
데이터그램은 링크 계층으로 전달되고 링크 계층도 자신의 헤더 정보를 추가하고 링크 계층 프 레임을 만든다.

<br/>
