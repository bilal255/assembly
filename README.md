# assembly
Include Irvine32.inc
.data

arr byte "Enter your age:",0
arr1 byte "The candidate is eligible",0
arr2 byte "The candidate isn't  eligible",0
age dword ?


.code
main proc

mov edx,offset arr
call writestring
call crlf
mov eax,0
call readint
cmp eax,22

je L1
jg L2
jl L3

L1:
 
    mov edx,offset arr1
	call writestring
	jmp skip
L2:

    mov edx,offset arr1
	call writestring
	jmp skip
L3:
    mov edx,offset arr2
	call writestring
	jmp skip

skip:


call readint
exit
main endp
end main'
