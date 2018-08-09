---
layout: post
title: " -------- "
subtitle: <span class="evidence"> -------- </span>
date: 2018-01-01
author: NoonGam
category: Study
tags: Network Linux
comments: true
finished: true
---



## Keep Alive

TCP KEEP-ALIVE는 옵션으로써 컨셉은 심플 합니다.
A – B가 서로 Connection이 Establish된 상태에서 (3-handshake)
지정된 시간(OS 설정 값 또는 어플리케이션 설정) 동안 서로
패킷 교환(Exchange)이 없을경우 payload가 없는 probe(프로토스 유닛 아님) 패킷을
보냅니다.
만약 정상일 경우 connection을 유지하고, 그렇지 않을 경우는 장애로
판단해서 본인 Connection도 close 합니다.

그러면 Keep-Alive를 어떨때 사용하면 좋냐면..

1. Checking for dead peers
A-B가 연결된 경우 B시스템이 장애로 인해서 restart될 경우 A는 keep-alive 설정에 의해 probe 패킷을 보내고, B는 RST(Rest)을 응답 합니다.

2. Preventing disconnection
A - NAT - B 일 경




## NAT

<a> NAT (Network Address translation) - 1개의 공인 IP에 N개의 사설 IP를 매핑하는 주소 변환 방식 </a>
```
1개의 공인 아이피

NAT은 IPv4의 주소 부족 문제를 해결하기 위해서 고안되었으며, 사설 또는 로컬 네트워크 주소를 사용하는 망에서 외부 public망에 접근하기 위해서 네트워크 주소를 변환하는 것을 말합니다.

NAT를 방식으로 구분하면 첫째,수동으로 외부 공인 IP와 사설 IP를 1:1로 매핑하는 정적 NAT (Static NAT) 방식, 둘째, 사설 IP 주소를 풀(Pool)화하여 공인 주소로 자동 매핑하는 동적 NAT 방식 (Dynamic NAT), 셋째 가정에서 주로 사용하는 공유기에 사용되는 방식으로 IP 주소 뿐만 아니라 포트 번호까지도 포함시켜 내부 호스트를 구분하는 NAPT 또는 PAT(Port Address Translation) 방식으로 나눌수 있습니다.

또한 NAT를 기능을 중심으로 구분하면, 첫째 외부망에서 볼 때 내부망의 여러 호스트들이 단일한 NAT 서버로 만 보이게하는 기법인 IP Masquerading, 둘째, 내부망의 여러 호스트들이 외부망과 트랜스포트계층에서 각각 별도로 연결짓게 할 수 있는 Port Forwarding (포트 포워드), 셋째 각 포트별로 트래픽을 균형있게 하는 Load Balancing으로 나눌 수 있습니다.

1. 인터넷 IP를 한정되어 있는데 라우터에게는 자신의 아이피 하나만 알려주고, 공유기(NAT 보유)는 자신의 내부에 있는 사설 IP만 가지고 있다.

2. public ip와 private IP를 사용하면서 그 사이에 방화벽(Firewall)을 설치하여 사설 IP를 보호하는 수단으로 활용할 수 있습니다. 외부에서 사설망으로 들어오기 위해서는 해당 IP를 알아야 하지만, NAT을 활용하여 공유기(NAT)의 public ip만 라우터 테이블에 등록합니다.
따라서 외부 침입자가 공격하기 위해서는 사설망의 내부 사설 IP주소를 알아야 하기 때문에 공격이 불가능해지므로 내부 네트워크를 보호할 수 있게 됩니다.



```


<br><br><br>

## HTTP Keep Alive

```
일단 결론적으로 말하면 TCP-KeepAlive 와 HTTP-KeepAlive는 전혀
다름.

TCP는 OS에 제어, HTTP 어플리케이션(웹 서버) 제어.

HTTP-KeepAlive는 HTTP/1.1 스펙 하지만 사실 클라이언트에서
하는게 없고 다 서버에서 담당.

쿨라이언트-서버가 주어진 시간에 요청이 계속 들어 오면
커넥션 연장 만약 그렇지 않을 경우 서버에서 커넥션을 끊음.

이런 이유는 매번 커넥션을 생성하면 성능이 떨어지기 때문

서버에서 설정하면 클라이언트 해더에 아래와 같이 표시됨

Keep-Alive: timeout=5, max=100
Connection: Keep-Alive

두번 요청 하면

Keep-Alive: timeout=5, max=99
Connection: Keep-Alive

timeout : 단위는 초 즉 커넥션 유지 시간 5초
max는 : 위에서 보면 최초 100에서 두번째는 -1된 99. 즉, 아무리 keep-alive로 유지를 한다고
해도 허가된 요청수. 해당 요청수가 넘으면 reconnect

```



<br><br><br>

## 예시







<br><br><br>

## 참고 자료
* http://tldp.org/HOWTO/TCP-Keepalive-HOWTO/overview.html

<fieldset id="gpg-fieldset">
 샘플 파일
</fieldset>
