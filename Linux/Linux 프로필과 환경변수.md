# Linux 프로필과 환경변수

- Run Level 단계가 끝나면 로그인 화면이 나온다.

- 로그인을 성공하면 `/etc/profile`과 `~/.profile` 두가지 설정 파일을 읽는다.

- `/etc/profile`은 모든 사용자의 설정을 담고 있고, `~/.profile`은 현재 로그인한 사용자의 설정을 담고 있다. (`~/.profile`은 숨김 파일이다.)

- `/etc/profile` 파일에 기본적으로 입력되어 있는 내용들이 있고, 그 파일에 명령어를 적어두면 우분투를 부팅했을 때 모든 사용자가 그 명령어를 실행한다.

- `/etc/profile` 파일에 `alias bb='ls -l'`과 같은 명령어를 입력해두고 껏다 키면 bb 별칭을 사용할 수 있다.

- 또는 `/etc/profile.d` 파일 안에 스크립트를 만들면 만든 스크립트를 알아서 읽어낸다.

- `~/.profile`도 `/etc/profile`과 마찬가지로 스크립트에 명령어를 추가하면 사용할 수 있다. 하지만 다른 사용자는 사용할 수 없다.

- `~/.bash_logout` 파일을 만들어서 작성하면 로그아웃할 때 실행할 스크립트를 지정할 수 있다.

- `/etc/environment`
  - 환경 변수를 설정하기 위한 파일
  - PAM (Pluggable Authentication Modules)이 읽어들인다.