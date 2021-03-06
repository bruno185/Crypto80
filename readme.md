# Apple II Crypto

A very basic program to encrpt/decrypt any file, using a secret phrase EORed with the file to encrpt/decrypt.
It is written in assembly language only (Merlin). It uses MLI ProDOS calls for disk access.
Applesoft is not required.

## Features
* works with ProDOS 8 (not tested on GS)
* User can chage PREFIX
* user can encrpt or decrypt any file
* the program adapts itself to 40 ou 80 col. mode.

The last feature was intersting to realise. The non obvious thing (for me) is that the character sets (normal and atl), does not behave wether you are in 40 ou 80 column mode.

Note : if A file is encrypted to B file, and B file is encrypted to C file, A = C, because of EOR.

Encrypt adds ".K" at the end of file name.
Decrypt adds ".D" at the end of file name.

## Requirements to compile and run
Here is my configuration:
* Visual Studio Code with 2 extensions 
-> Merlin32 : https://marketplace.visualstudio.com/items?itemName=olivier-guinart.merlin32 : 6502 code hightliting 
-> https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner : running batch file with right-clic.

* Merlin32 cross compiler : http://brutaldeluxe.fr/products/crossdevtools/merlin/

* Applewin (emulator) : https://github.com/AppleWin/AppleWin

* Applecommander (disk utility) : http://applecommander.sourceforge.net/

* Ciderpress : https://a2ciderpress.com/


Note : 
DoMerlin.bat puts all things together. It needs a path to Merlin32 directory, to Applewin, and to Applecommander.
DoMerlin.bat is to be placed in project directory.
It compile source (*.s) with Merlin32, copy 6502 binary to a disk image (containg ProDOS), and launch Applewin with this dis in S1,D1.

# Todo
File name length is not tested. This can be imporant since encrypting adds ".K" to the file name (so length = length +2).

Lower part of screen should be limited in a window, to avoid the all screen scrolling.

Port to Mouse Graphic ToolKit, for a fancier look, and more functions.

