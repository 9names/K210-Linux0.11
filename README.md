Linux0.11 with MMU for K210(This is ported from Linus's December 1991 Linux 0.11 code)  
This is my first linux project.  
You need compile this project with "make" tools in the Windows and Linux VM supporting minix filesystem(mkfs and mount).  
image.bin is final image which is combined by rootfs.bin(root filesystem) and system.bin(kernel image)  
You need Visual Studio 2019 to open the project and compile.

If building under linux:
Download the Kendryte binary toolchain or compile it yourself - makefile currently assumes an install location of ~/toolchain/kendryte-toolchain
Install the Mono c-sharp compiler (eg sudo apt install mono-mcs)
cd test_src
make -f Makefile.linux
sudo make -f Makefile.linux install

Upload the new image to your K210 (subsitute dan with your board type)
kflash image.bin -B dan -b 3000000 -t
