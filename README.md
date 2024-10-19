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
