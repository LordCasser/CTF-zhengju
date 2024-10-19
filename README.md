# CTF
我是刚入门安全的一名小白，尝试开始记录写写题，有时间的话也争取写写题解，慢慢进步。    20240713  16：12


; Attributes: fuzzy-sp

; void start()
public start
start proc near
xor     rbp, rbp
mov     rdi, rsp
lea     rsi, cs:0
and     rsp, 0FFFFFFFFFFFFFFF0h
call    $+5
mov     rsi, [rdi]
lea     rdx, [rdi+8]
xor     r9d, r9d
lea     r8, _term_proc
lea     rcx, _init_proc
lea     rdi, sub_404930
jmp     loc_44F6DE
start endp




进去之后
sub_404930 proc near

var_8= qword ptr -8

; __unwind {
push    rax
mov     rcx, rsi
movsxd  rdx, edi
lea     rax, sub_403860
mov     [rsp+8+var_8], rax
lea     rsi, unk_52F400
mov     rdi, rsp
xor     r8d, r8d
call    cs:off_531C08
pop     rcx
retn
; } // starts at 404930
sub_404930 endp
