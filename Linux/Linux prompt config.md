# Linux 프롬프트 설정하기

우분투는 기본적으로 프롬프트가 '사용자@server:현재디렉토리$'로 설정되어 있다.

하지만 사용자에 따라 이러한 프롬프트가 불편한 사람이 있을 것이다.

프롬프트를 나타내는 프롬프트 스트링(PS1)이라는 것이 있다.

`echo $PS1` 명령어를 통해 현재 프롬프트 스트링을 알아낼 수 있다.

프롬프트 스트링을 변경하는 방법은 간단하다. `PS1="원하는프롬프트"` 방식으로 하면 된다.

예를 들어 `PS1="$"` 명령어를 사용하면 프롬프트가 $로 바뀐다.

그리고 프롬프트에 적용할 수 있는 여러가지 이스케이프 시퀀스들이 있다.

- \H : 호스트 이름
- \d : 오늘 날짜
- \n : 개행
- \r : 캐리지 리턴
- \t : 현재 시간 (in 24-hour)
- \T : 현재 시간 (in 12-hour)