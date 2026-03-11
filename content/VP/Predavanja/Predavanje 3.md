![[VarProg2.pdf]]

Page 11 onwards.

==Vaje recap== - [[VP/Vaje/Vaje 3|Vaje 3]]

C primer 4:
v while loopu gre prek allocated space in bo uint8_t resetu na 0.

C primer 5:
IOS exploit.

Return oriented programming

leave ->
	rsp = rbp (stack pointer nastavi na rbp, kjer bodo uporabni podatki)
	pop rbp (rbp prestavi na shranjen rbp od zunanje funkcije, rsp se prestavi za 8 bytov nizje)

ret ->
	pop rip (rsp se prestavi za 8 bytov nizje, loadamo returnAddress)

Gadgets so vnaprej narejeni optimizacijski ukazi. Namesto na funkcijo lahko skocimo na poljuben gadget.
Za loadanje argumentov lahko skocimo na gadget pop rbx; ret, ki bo v rbx loadu 8 bytov pod return address in skocil na 8 bytov pod tem.
Za nalaganje argumentov v registre za argumente 0 in 1 uporabimo gadget, ki skoci na drug gadget in nato v win.

ropr <ime> | grep 'pop rsi'
