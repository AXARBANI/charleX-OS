
# charleX OS logo

<pre>
        _                _     __  __
   ___| |__   __ _ _ __| | ___\ \/ /
 / __| '_  \ / _` | '__| |/ _ \\  /
| (__| | | | (_| | |  | |  __//  \
\___|_| |_|\__,_|_|  |_| \___/_/\_\

        	  ___  ____  
        	 / _ \/ ___|
        	| | | \___ \
        	| |_| |___) |
        	 \___/|____/


</pre>

# charleX OS
charleX is simple OS ...
kernel written with c programming language, and reference of this code is bacilica OS.
i still working to make better kernel than this one, and many features will added to this project . i wanna create the free and open source OS  like gnu/linux , *BSD ,... and you can support us . if you like this project,  give star to project  and send better code to us .

# compile and run
$as --32 boot.s -o boot.o

$gcc -m32 -c kernel.c -o kernel.o -std=gnu99 -ffreestanding -O1 -Wall -Wextra

$gcc -m32 -c utils.c -o utils.o -std=gnu99 -ffreestanding -O1 -Wall -Wextra

$gcc -m32 -c char.c -o char.o -std=gnu99 -ffreestanding -O1 -Wall -Wextra

$ld -m elf_i386 -T linker.ld kernel.o utils.o char.o boot.o -o charleX.bin -nostdlib

$grub-file --is-x86-multiboot charleX.bin

$mkdir -p iso/boot/grub

$cp charleX.bin iso/boot/charleX.bin

$cp grub.cfg iso/boot/grub/grub.cfg

$grub-mkrescue -o charleX.iso iso

$qemu-system-i386 charleX.iso

#Automatic compile and run

$./makefile

#report bug or problems

send bug or anythings : amzy0zone@gmail.com

thanks for reading this ! :)
