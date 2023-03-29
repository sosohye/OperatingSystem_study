

defs.h : 구조체 + 함수 원형 정의

---
# system call

syscall.c : fetching arguments + system calls ( sysfile.c + sysproc.c )


user.h : system calls + ulib.c
usys.S : 모든 system calls에 대하여syscall.h의 번호를 eax 레지스터에 저장한뒤 traps.h의 T_SYSCALL가 인터럽트를 발생


---