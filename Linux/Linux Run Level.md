# Linux Run Level

리눅스 부팅 순서

1. BIOS : 컴퓨터가 소프트웨어를 돌리기에 적당한 환경을 가지고 있는지 검사
2. Master Boot Record (MBR)
3. LILO or GRUB
4. Kernel
5. init : process number 1(PID=1)
   - /linuxrc : load modules / initialize devices / exits
   - /sbin/init
     - /etc/inittab : run boot scripts
       - /etc/init.d/rcS
         - /etc/rcS.d/S* scripts
         - /etc/rc.boot/*

6. Run Levels

   0 : Halt (종료)

   1 : Single-user mode (복구모드)

   2 : Multi-user mode

   3 : 우분투 default

   4 : Multi-user mode

   5 : Multi-user mode

   6 : Reboot



종료 방법

- poweroff
- shutdown
- halt
- init 0

재시작

- reboot
- shutdown
- init 6