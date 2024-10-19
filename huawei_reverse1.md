


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
这个是题目给的二进制文件进来




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
找到main函数sub_404930,点进去之后



__int64 __fastcall sub_404930(int a1, __int64 a2)
{
  __int64 (__fastcall *v3)(); // [rsp+0h] [rbp-8h] BYREF

  v3 = sub_403860;
  return sub_423040(&v3, &unk_52F400, a1, a2, 0LL);
}
F5转换成代码，查看main函数里面的东西
