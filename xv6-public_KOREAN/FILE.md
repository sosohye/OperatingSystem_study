

defs.h : 구조체 + 함수 원형 정의

---
# system call

syscall.c : fetching arguments + system calls ( sysfile.c + sysproc.c )


user.h : system calls + ulib.c

usys.S : 모든 system calls에 대하여syscall.h의 번호를 eax 레지스터에 저장한뒤 traps.h의 T_SYSCALL가 인터럽트를 발생

---

# trap & interrupt

mmu.h = memory management unit

mmu.h 에는 Gate descriptors for interrupts and traps가 있는데
cs(code segment selector)(0,1번째 비트는 cpl을 의미)

게이트란 인텔 프로세서들에서 정의해서 사용하는 특이한 구조인데, 게이트는 시스템에 서로 다른 privilege 레벨의 핸들러 혹은 procedure 를 호출하기 위해서 정의하고 있는 일종의 'gateway' 와 같은 역할을 하는 구조체이다. 이 구조체에는 호출할 핸들러 혹은 procedure 의 주소에 대한 정보, privilege level 에 대한 정보와 같은 것들이 담겨져 있다. 주로 이러한 게이트들은 64비트의 크기를 가진다. 인텔에서 정의하는 게이트는 call gate, task gate, interrupt gate, trap gate 등이 존재하며, IDT 에 들어갈 수 있는 게이트는 여기서 call gate 를 제외한 세가지 gate 들이다.

---

#