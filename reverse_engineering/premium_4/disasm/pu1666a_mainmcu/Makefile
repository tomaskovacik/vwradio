diff: out.bin
	openssl sha1 out.bin | cut -d ' ' -f 2 > out.sha1
	diff pu1666a_mainmcu.sha1 out.sha1

out.bin: out.lst
	python ../lst2bin.py out.lst out.bin

out.lst: pu1666a_mainmcu.asm
	asf2mc8 -l pu1666a_mainmcu.asm
	mv pu1666a_mainmcu.lst out.lst
	rm -f out.hlr

clean:
	rm -f out.*

all: clean out.bin diff
