# Linux Run Level

리눅스 런레벨이란 시스템 관리를 위해 서비스 실행에 관련된 명령을 단계별로 구분하여 적용하는 것이다. 0 ~ 6까지 총 7개의 레벨이 있다.

---

각 RunLevel의 의미

- `RunLevel 0` : PowerOff
  - 시스템 종료를 의미한다.

- `RunLevel 1` : Rescue
  - 시스템 복구 모드를 실행한다. 관리자 쉘을 얻게 된다.

- `RunLevel 2` : Multi-User
  - NFS (Network File System)을 지원하지 않는 Multi-User 모드다. 런레벨 3과 유사하다.

- `RunLevel 3` : Full Multi-User
  - NFS를 지원하는 Multi-User 모드다. 리눅스를 실행하면 기본적으로 RunLevel 3으로 실행된다.

- `RunLevel 4` : Multi-User (unused)
  - 사용하지 않는 모드다. 하지만 RunLevel 3과 유사하고, 이 단계를 사용자 임의로 설정해서 사용하기도 한다.

- `RunLevel 5` : Graphical
  - RunLevel 3과 동일하지만 GUI를 지원하는 그래픽 유저 모드다.

- `RunLevel 6` : Reboot
  - 시스템 재부팅을 의미한다.

---

각 단계를 실행시키기 위해서 `init 런레벨` 명령어를 사용한다. (sudo가 필요하다)

`init 0`을 사용하면 리눅스가 종료되고, `init 6`을 사용하면 리눅스가 재부팅된다.

init 명령어보다 편하게 사용할 수 있는 shutdown, reboot같은 명령어를 사용해도 좋다.