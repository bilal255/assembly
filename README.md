# assembly
Include Irvine32.inc
.data
arr0 byte "if you have bsc enter 1 otherwise 0",0
arr byte "Enter your age:",0
arr1 byte "The candidate is eligible",0
arr2 byte "The candidate isn't  eligible",0
age dword ?
qual dword ?

.code
main proc

mov edx,offset arr
call writestring
call crlf
mov eax,0
call readint
cmp eax,22

je L3
jg L3
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
    mov edx,offset arr0
	call writestring
	call readint
	mov qual,eax
	cmp eax,1
	je L1
	jl skip
	jg skip

skip:
	mov edx,offset arr2
	call writeint 

call readint
exit
main endp
end main
