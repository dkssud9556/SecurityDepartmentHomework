# ARP Spoofing

- MITM(Man In The Middle) : 통신을 하는 두 장비 사이에서 패킷을 가로채서 악용하는 기법.
  - Spoofing : TCP/IP의 구조적 결함을 이용해서 사용자와 시스템 권한을 얻고, 정보를 빼가는 수법
  - Snoofing : 네트워크 상에서 떠도는 중요 정보를 몰래 획득하는 수법
  - Sniffing : 네트워크 상에서 다른 상대방의 패킷 교환 정보를 훔쳐보는 수법

- ARP의 취약점 : ARP 응답의 송신자에 대한 인증을 하지 않는다.

- ARP spoofing
  - 두 통신자의 ARP 캐시 테이블을 위조하고, 중간에서 주고 받는 패킷들을 전다해주면서 패킷에 있는 정보를 가로채는 것이다.
  - 흔히 게이트웨이 IP를 스푸핑하여 외부로 전송하는 모든 패킷을 가로채거나 변조한다.
  - ARP 스푸핑이 성공적으로 먹히면 네트워크 상의 라우팅을 공격자가 바꿔서 효과적으로 중간자 공격을 수행할 수 있게 된다.
  - 특별한 도구를 사용하지 않으면 자신이 공격당하고 있다는 사실을 확인하기 어렵다.