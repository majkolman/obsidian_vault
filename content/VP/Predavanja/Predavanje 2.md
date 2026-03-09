![[VarProg1.pdf]]

Slide 10 naprej

gets lahko povzroci stack smashing
	prebran string brez eof

Stack Canary
	preden pozenes f das na stack vrednost

	ko se vrnes pogledas ce je vrednost ista

aseembly kode je 
objdump -d <ime>

![[VarProg2.pdf]]

gdb:
c -> continue
ni -> next instruction
disass <ime> -> dissasembly
x/<num>gx <addr>
