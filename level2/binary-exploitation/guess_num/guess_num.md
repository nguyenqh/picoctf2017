# Guess the number

(solved without looking at source code)

notice at *main+199, the input number has been shifted right (shrl is logical shift right on long integer)

the resultant number is treated as the address of the function to be called next

we want to call the win(), which is located at 0x0804852b, so the input must be 0x804852b? where ? is any digit since it will disappear after shift-righting.

The problem here is that what is 0x804852b0 equal to?
It is a negative number since the first bit is 1.
To find the number, we compute the two's complement of the unsigned integer 0x804852b0.

The number is -(0x100000000 - 0x804852b0) = -2142743888

Solution:
$ (echo '-2142743888'; cat) | nc shell2017.picoctf.com 13532