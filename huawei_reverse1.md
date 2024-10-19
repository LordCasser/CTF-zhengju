


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





__int64 sub_403860()
{
  __int64 v0; // rdx
  __int64 v1; // rax
  __int64 v2; // rdx
  __int64 v3; // r12
  __int64 v4; // rbx
  __int64 v5; // rax
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // r14
  unsigned int v9; // ecx
  _BYTE *v10; // r13
  unsigned __int64 i; // r9
  int v12; // edx
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned __int64 v15; // rbp
  unsigned __int64 v16; // r14
  __int64 v17; // r12
  __int64 v18; // rdi
  unsigned __int64 v19; // r15
  __int64 v20; // r12
  bool v21; // cf
  unsigned __int64 v22; // r12
  __int64 v23; // rax
  unsigned __int64 v24; // rsi
  __int64 v25; // rax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // r15
  unsigned __int64 v29; // r15
  unsigned int v30; // ebp
  char v31; // r13
  char v32; // r8
  char v33; // r14
  unsigned int v34; // ebp
  __int64 v35; // rbx
  __int64 v36; // r12
  __int64 v37; // r12
  __int64 v38; // r15
  unsigned __int64 v39; // rbx
  unsigned __int64 v40; // r13
  unsigned __int64 v41; // r12
  __int64 v42; // rbp
  unsigned __int64 v43; // rbp
  __int64 v44; // r15
  __int128 v45; // kr00_16
  __int64 v46; // r12
  __int64 v47; // rax
  __int64 v48; // rsi
  unsigned __int64 v49; // rdi
  unsigned __int64 v50; // rdi
  unsigned __int64 v51; // rdi
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // rdi
  unsigned __int64 v54; // rdi
  unsigned __int64 v55; // rdi
  unsigned __int64 v56; // rdi
  bool v57; // bp
  __int64 v58; // rsi
  __int64 v59; // rbx
  unsigned __int64 v60; // r12
  __int64 v61; // r15
  __int64 v62; // rax
  __int64 v63; // r13
  __int64 result; // rax
  unsigned __int64 v65; // rdx
  unsigned __int64 v66; // rbx
  void **v67; // r8
  unsigned __int64 v68; // rcx
  char *v69; // r15
  __int64 v70; // rdx
  unsigned __int64 v71; // rbp
  __int64 v72; // rcx
  __int64 v73; // r8
  __m128i v74; // xmm0
  __m128i si128; // xmm1
  __m128i v76; // xmm3
  unsigned __int64 v77; // rbx
  unsigned __int64 v78; // rbx
  __int64 v79; // rcx
  __int64 v80; // r8
  __m128i *v81; // rax
  __m128i *v82; // rbx
  __m128i v83; // xmm2
  __m128i v84; // xmm3
  __int64 v85; // rbx
  __int64 v86; // rdi
  __int64 v87; // rdi
  void **v88; // rdi
  __int64 v89; // [rsp+8h] [rbp-200h]
  __int128 v90; // [rsp+10h] [rbp-1F8h] BYREF
  __int128 v91; // [rsp+20h] [rbp-1E8h]
  __int128 v92; // [rsp+30h] [rbp-1D8h]
  __int64 v93; // [rsp+40h] [rbp-1C8h]
  unsigned __int64 v94; // [rsp+48h] [rbp-1C0h]
  unsigned __int64 v95; // [rsp+50h] [rbp-1B8h]
  unsigned __int64 v96; // [rsp+58h] [rbp-1B0h]
  __m128i v97; // [rsp+60h] [rbp-1A8h] BYREF
  __m256i v98; // [rsp+70h] [rbp-198h] BYREF
  __m128i v99; // [rsp+90h] [rbp-178h]
  __m128i v100; // [rsp+A0h] [rbp-168h]
  __int128 v101; // [rsp+B0h] [rbp-158h]
  unsigned __int64 v102; // [rsp+C0h] [rbp-148h]
  char v103; // [rsp+C8h] [rbp-140h]
  int v104; // [rsp+C9h] [rbp-13Fh]
  __int16 v105; // [rsp+CDh] [rbp-13Bh]
  char v106; // [rsp+CFh] [rbp-139h]
  void **v107; // [rsp+D8h] [rbp-130h]
  __int64 v108; // [rsp+E0h] [rbp-128h]
  __int64 v109; // [rsp+E8h] [rbp-120h]
  __int64 v110; // [rsp+F0h] [rbp-118h]
  __int64 v111; // [rsp+F8h] [rbp-110h] BYREF
  __int64 v112; // [rsp+100h] [rbp-108h]
  __int64 v113; // [rsp+108h] [rbp-100h]
  __m128i v114; // [rsp+110h] [rbp-F8h] BYREF
  void **v115; // [rsp+128h] [rbp-E0h]
  __m128i v116; // [rsp+130h] [rbp-D8h] BYREF
  __m128i v117; // [rsp+140h] [rbp-C8h] BYREF
  _QWORD v118[11]; // [rsp+150h] [rbp-B8h] BYREF
  char v119; // [rsp+1A8h] [rbp-60h]
  int v120; // [rsp+1A9h] [rbp-5Fh]
  __int16 v121; // [rsp+1ADh] [rbp-5Bh]
  char v122; // [rsp+1AFh] [rbp-59h]
  unsigned __int64 v123; // [rsp+1B0h] [rbp-58h]
  __int64 v124; // [rsp+1B8h] [rbp-50h]
  __int64 v125; // [rsp+1C0h] [rbp-48h]
  __int64 v126[8]; // [rsp+1C8h] [rbp-40h] BYREF

  v97.m128i_i64[0] = (__int64)&off_52F330;
  v97.m128i_i64[1] = 1LL;
  v98.m256i_i64[0] = 8LL;
  *(_OWORD *)&v98.m256i_u64[1] = 0LL;
  sub_425450(&v97);
  v111 = 0LL;
  v112 = 1LL;
  v113 = 0LL;
  v117.m128i_i64[0] = sub_424BE0();
  if ( sub_424C10(&v117, &v111) )
  {
    v97.m128i_i64[0] = v0;
    sub_402DF0(
      "called `Result::unwrap()` on an `Err` valueInvalidByteInvalidLengthInvalidLastSymbolInvalidPadding",
      43LL,
      &v97,
      &off_52F220,
      &off_52F340);
  }
  v1 = sub_404B10(v112, v113);
  sub_404FE0(&v97, &unk_45B0E8, v1, v2);
  v109 = v97.m128i_i64[0];
  if ( v97.m128i_i64[0] == 0x8000000000000000LL )
  {
    v117 = _mm_loadu_si128((const __m128i *)&v97.m128i_i8[8]);
    sub_402DF0(
      "called `Result::unwrap()` on an `Err` valueInvalidByteInvalidLengthInvalidLastSymbolInvalidPadding",
      43LL,
      &v117,
      &unk_52F200,
      &off_52F358);
  }
  v3 = v97.m128i_i64[1];
  v4 = v98.m256i_i64[0];
  *(_QWORD *)&v90 = 0LL;
  *((_QWORD *)&v90 + 1) = 1LL;
  *(_QWORD *)&v91 = 0LL;
  v5 = sub_4053A0(0x10000LL, 8LL);
  v89 = v3;
  if ( !v5 )
    sub_402910(8LL, 0x10000LL);
  v6 = v4 - 13;
  v95 = v4;
  v108 = v4;
  v110 = v5;
  if ( (unsigned __int64)(v4 - 13) < 3 )
  {
    v7 = 0LL;
  }
  else
  {
    v124 = v3 + v4;
    v116.m128i_i64[0] = v4 - 3;
    v125 = v3 + 3;
    v7 = 2LL;
    v115 = &off_52F2B8;
    v107 = &off_52F2E8;
    v8 = 0LL;
    v123 = v6;
    while ( 1 )
    {
      v10 = (_BYTE *)(v125 + v7);
      for ( i = v116.m128i_i64[0] - v7; ; --i )
      {
        v12 = *(_DWORD *)(v3 + v7) & 0xFFFFFF;
        v13 = (unsigned int)(-1640531527 * v12) >> 19;
        v14 = *(_QWORD *)(v5 + 8 * v13);
        *(_QWORD *)(v5 + 8 * v13) = v7;
        if ( v7 - v14 < 0x2000 && v12 == (*(_DWORD *)(v3 + v14) & 0xFFFFFF) )
          break;
        ++v7;
        ++v10;
      }
      if ( v7 >= v6 )
        break;
      v96 = i;
      v114.m128i_i64[0] = v14;
      v15 = v7 - v8;
      if ( v7 > v8 )
      {
        if ( v7 <= v95 )
        {
          v16 = v89 + v8;
          v17 = v91;
          while ( 1 )
          {
            v19 = 32LL;
            if ( v15 < 0x20 )
              v19 = v15;
            if ( v17 == (_QWORD)v90 )
              sub_404E40(&v90);
            *(_BYTE *)(*((_QWORD *)&v90 + 1) + v17) = v19 - 1;
            v20 = v17 + 1;
            *(_QWORD *)&v91 = v20;
            if ( (__int64)v90 - v20 >= v19 )
            {
              v18 = *((_QWORD *)&v90 + 1);
            }
            else
            {
              v21 = __CFADD__(v19, v20);
              v22 = v19 + v20;
              if ( v21 )
              {
                v86 = 0LL;
                goto LABEL_164;
              }
              if ( 2 * (__int64)v90 > v22 )
                v22 = 2 * v90;
              if ( v22 < 9 )
                v22 = 8LL;
              if ( (_QWORD)v90 )
              {
                v97.m128i_i64[0] = *((_QWORD *)&v90 + 1);
                v98.m256i_i64[0] = v90;
                v23 = 1LL;
              }
              else
              {
                v23 = 0LL;
              }
              v97.m128i_i64[1] = v23;
              sub_404DB0(&v117, (v22 & 0x8000000000000000LL) == 0LL, v22, &v97);
              if ( v117.m128i_i64[0] )
              {
                v86 = v117.m128i_i64[1];
                v6 = v118[0];
LABEL_164:
                sub_402910(v86, v6);
              }
              v18 = v117.m128i_i64[1];
              *((_QWORD *)&v90 + 1) = v117.m128i_i64[1];
              *(_QWORD *)&v90 = v22;
              v20 = v91;
            }
            v6 = v16;
            v16 += v19;
            v15 -= v19;
            sub_453DAD(v20 + v18, v6, v19);
            *(_QWORD *)&v91 = v91 + v19;
            v17 = v91;
            if ( !v15 )
              goto LABEL_32;
          }
        }
LABEL_170:
        sub_402EE0(v7, v108, v115);
      }
LABEL_32:
      v24 = v7 + 3;
      if ( v7 + 3 > v95 )
      {
        v107 = &off_52F300;
        v87 = v7 + 3;
        goto LABEL_167;
      }
      if ( v114.m128i_i64[0] + 3 > v95 )
      {
        v87 = v114.m128i_i64[0] + 3;
        goto LABEL_167;
      }
      v25 = v89 + v114.m128i_i64[0] + 3;
      v26 = v116.m128i_i64[0] - v7;
      v27 = v124 - v25;
      if ( v116.m128i_i64[0] - v7 >= v124 - v25 )
        v26 = v124 - v25;
      if ( v26 )
      {
        if ( v96 < v27 )
          v27 = v96;
        v28 = 0LL;
        while ( *v10 == *(_BYTE *)(v25 + v28) )
        {
          ++v28;
          ++v10;
          if ( v27 == v28 )
          {
            v28 = v26;
            break;
          }
        }
        v24 = v28 + v7 + 3;
        v29 = v28 + 3;
        if ( v24 < v7 )
LABEL_168:
          sub_402F50(v7, v24, &off_52F2D0, v26, v114.m128i_i64[0], v96);
      }
      else
      {
        v29 = 3LL;
        if ( v24 < v7 )
          goto LABEL_168;
      }
      v96 = v24;
      if ( v24 > v95 )
      {
        v7 = v96;
        v115 = &off_52F2D0;
        goto LABEL_170;
      }
      if ( v29 )
      {
        v30 = v7 + ~v114.m128i_i32[0];
        v31 = ((unsigned __int16)(v7 + ~v114.m128i_i16[0]) >> 8) - 32;
        v32 = -v114.m128i_i8[0];
        v114.m128i_i64[0] = v7 + (unsigned __int8)-v114.m128i_i8[0] + 255;
        v33 = (v7 + v32 - 1) & 0x1F;
        v34 = v30 >> 5;
        do
        {
          while ( 1 )
          {
            v35 = 262LL;
            if ( v29 < 0x106 )
              v35 = v29;
            if ( v29 >= 9 )
              break;
            v36 = v91;
            if ( (_QWORD)v91 == (_QWORD)v90 )
              sub_404E40(&v90);
            *(_BYTE *)(*((_QWORD *)&v90 + 1) + v36) = (v33 | (32 * v35)) - 64;
            *(_QWORD *)&v91 = v36 + 1;
            if ( v36 + 1 == (_QWORD)v90 )
              sub_404E40(&v90);
            *(_BYTE *)(*((_QWORD *)&v90 + 1) + v36 + 1) = v34;
            *(_QWORD *)&v91 = v36 + 2;
            v29 -= v35;
            if ( !v29 )
              goto LABEL_6;
          }
          v37 = v91;
          if ( (_QWORD)v91 == (_QWORD)v90 )
            sub_404E40(&v90);
          *(_BYTE *)(*((_QWORD *)&v90 + 1) + v37) = v31;
          *(_QWORD *)&v91 = v37 + 1;
          if ( v37 + 1 == (_QWORD)v90 )
            sub_404E40(&v90);
          *(_BYTE *)(*((_QWORD *)&v90 + 1) + v37 + 1) = v35 - 9;
          *(_QWORD *)&v91 = v37 + 2;
          if ( v37 + 2 == (_QWORD)v90 )
            sub_404E40(&v90);
          *(_BYTE *)(*((_QWORD *)&v90 + 1) + v37 + 2) = v114.m128i_i8[0];
          *(_QWORD *)&v91 = v37 + 3;
          v29 -= v35;
        }
        while ( v29 );
      }
LABEL_6:
      v7 = v96;
      v3 = v89;
      v9 = *(_DWORD *)(v89 + v96 - 2);
      v5 = v110;
      *(_QWORD *)(v110 + 8LL * ((-1640531527 * (v9 & 0xFFFFFF)) >> 19)) = v96 - 2;
      *(_QWORD *)(v5 + 8LL * ((-1640531527 * (v9 >> 8)) >> 19)) = v7 - 1;
      v8 = v7;
      v6 = v123;
      if ( v7 >= v123 )
        goto LABEL_67;
    }
    v7 = v8;
LABEL_67:
    if ( v7 > v95 )
    {
      v87 = v7;
      v107 = &off_52F318;
LABEL_167:
      sub_402E70(v87, v108, v107);
    }
  }
  v38 = v91;
  v95 -= v7;
  if ( v95 )
  {
    v39 = v3 + v7;
    v40 = v95;
    do
    {
      v43 = 32LL;
      if ( v40 < 0x20 )
        v43 = v40;
      if ( v38 == (_QWORD)v90 )
        sub_404E40(&v90);
      *(_BYTE *)(*((_QWORD *)&v90 + 1) + v38) = v43 - 1;
      v44 = v38 + 1;
      *(_QWORD *)&v91 = v44;
      if ( (__int64)v90 - v44 < v43 )
      {
        sub_401010(&v90, v44, v43);
        v44 = v91;
      }
      v41 = v39 + v43;
      v40 -= v43;
      sub_453DAD(*((_QWORD *)&v90 + 1) + v44, v39, v43);
      v42 = v91 + v43;
      *(_QWORD *)&v91 = v42;
      v38 = v42;
      v39 = v41;
    }
    while ( v40 );
  }
  else
  {
    v42 = v91;
  }
  v45 = v90;
  sub_405380(v110, 0x10000LL, 8LL);
  sub_4051A0(&v97, &unk_45B0E8, *((_QWORD *)&v45 + 1), v42);
  v46 = v97.m128i_i64[1];
  v47 = 786997LL;
  v48 = 0x100003600LL;
  v49 = (unsigned __int8)aBeouifiuqgawvg[786996];
  if ( v49 <= 0x20 )
  {
    while ( _bittest64(&v48, v49) )
    {
      v50 = (unsigned __int8)aBeouifiuqgawvg[v47 - 2];
      if ( v50 > 0x20 || !_bittest64(&v48, v50) )
      {
        --v47;
        break;
      }
      v51 = (unsigned __int8)aBeouifiuqgawvg[v47 - 3];
      if ( v51 > 0x20 || !_bittest64(&v48, v51) )
      {
        v47 -= 2LL;
        break;
      }
      v52 = (unsigned __int8)aBeouifiuqgawvg[v47 - 4];
      if ( v52 > 0x20 || !_bittest64(&v48, v52) )
      {
        v47 -= 3LL;
        break;
      }
      v53 = (unsigned __int8)aBeouifiuqgawvg[v47 - 5];
      if ( v53 > 0x20 || !_bittest64(&v48, v53) )
      {
        v47 -= 4LL;
        break;
      }
      if ( v47 == 5 )
      {
        v47 = 0LL;
        break;
      }
      v54 = (unsigned __int8)aBeouifiuqgawvg[v47 - 6];
      if ( v54 > 0x20 || !_bittest64(&v48, v54) )
      {
        v47 -= 5LL;
        break;
      }
      v55 = (unsigned __int8)aBeouifiuqgawvg[v47 - 7];
      if ( v55 > 0x20 || !_bittest64(&v48, v55) )
      {
        v47 -= 6LL;
        break;
      }
      v56 = (unsigned __int8)aBeouifiuqgawvg[v47 - 8];
      if ( v56 > 0x20 || !_bittest64(&v48, v56) )
      {
        v47 -= 7LL;
        break;
      }
      v47 -= 8LL;
      v49 = (unsigned __int8)aBeouifiuqgawvg[v47 - 1];
      if ( v49 > 0x20 )
        break;
    }
  }
  if ( v98.m256i_i64[0] != v47 )
  {
    v57 = 0;
    v58 = v97.m128i_i64[0];
    if ( !v97.m128i_i64[0] )
      goto LABEL_103;
    goto LABEL_102;
  }
  v57 = (unsigned int)sub_4539A0(v97.m128i_i64[1], aBeouifiuqgawvg, v98.m256i_i64[0]) == 0;
  v58 = v97.m128i_i64[0];
  if ( v97.m128i_i64[0] )
LABEL_102:
    sub_405380(v46, v58, 1LL);
LABEL_103:
  if ( (_QWORD)v45 )
    sub_405380(*((_QWORD *)&v45 + 1), v45, 1LL);
  if ( !v57 )
  {
    v97.m128i_i64[0] = (__int64)&off_52F370;
    v97.m128i_i64[1] = 1LL;
    v98.m256i_i64[0] = 8LL;
    *(_OWORD *)&v98.m256i_u64[1] = 0LL;
    result = sub_425450(&v97);
    goto LABEL_147;
  }
  sub_455EC0(&v97, v89, v108);
  v59 = v97.m128i_i64[1];
  v60 = v98.m256i_i64[0];
  if ( v98.m256i_i64[0] )
  {
    if ( v98.m256i_i64[0] < 0 )
    {
      v61 = 0LL;
    }
    else
    {
      v61 = 1LL;
      v62 = sub_405370(v98.m256i_i64[0], 1LL);
      if ( v62 )
      {
        v63 = v62;
        goto LABEL_112;
      }
    }
    sub_402910(v61, v60);
  }
  v63 = 1LL;
LABEL_112:
  sub_453DAD(v63, v59, v60);
  if ( 2 * v97.m128i_i64[0] )
    sub_405380(v59, v97.m128i_i64[0], 1LL);
  if ( !sub_403330(
          v63,
          v60,
          "flag{}qQ3CGmaxwxFbcAD1Eruz6NbR0fMqoERDsNKVPMFf2kw=Flag: \nUtf8Errorvalid_up_toerror_lenFromUtf8ErrorbyteserrorNoneSomeusize overflow when calculating b64 length/home/explorer/.cargo/registry/src/mirrors.ustc.edu.cn-4affec411d11e50f/base64-0.22.1/src/encode.rsVec is sized conservativelyinternal error: entered unreachable code: /home/explorer/.cargo/registry/src/mirrors.ustc.edu.cn-4affec411d11e50f/base64-0.22.1/src/engine/mod.rsinteger overflow when calculating buffer sizeInvalid UTF8",
          5LL) )
  {
    v88 = &off_52F380;
    goto LABEL_176;
  }
  v66 = v65;
  if ( v65 )
  {
    if ( v60 <= v65 )
    {
      if ( v60 != v65 )
        goto LABEL_118;
    }
    else if ( *(char *)(v63 + v65) <= -65 )
    {
LABEL_118:
      v67 = &off_52F398;
      v68 = v60;
      goto LABEL_130;
    }
  }
  v69 = (char *)(v65 + v63);
  if ( !sub_403330(
          v65 + v63,
          v60 - v65,
          "}qQ3CGmaxwxFbcAD1Eruz6NbR0fMqoERDsNKVPMFf2kw=Flag: \nUtf8Errorvalid_up_toerror_lenFromUtf8ErrorbyteserrorNoneSomeusize overflow when calculating b64 length/home/explorer/.cargo/registry/src/mirrors.ustc.edu.cn-4affec411d11e50f/base64-0.22.1/src/encode.rsVec is sized conservativelyinternal error: entered unreachable code: /home/explorer/.cargo/registry/src/mirrors.ustc.edu.cn-4affec411d11e50f/base64-0.22.1/src/engine/mod.rsinteger overflow when calculating buffer sizeInvalid UTF8",
          1LL) )
  {
    v88 = &off_52F3B0;
LABEL_176:
    sub_4029C0(v88);
  }
  v68 = v66 + v70 + 1;
  v67 = &off_52F3C8;
  v71 = v70 + 1;
  if ( v68 < v66 )
    goto LABEL_130;
  if ( v66 )
  {
    if ( v60 <= v66 )
    {
      if ( v60 != v66 )
        goto LABEL_130;
    }
    else if ( *v69 <= -65 )
    {
LABEL_130:
      sub_4030B0(v63, v60, v66, v68, v67);
    }
  }
  if ( v66 + v70 != -1LL )
  {
    if ( v68 >= v60 )
    {
      if ( v68 != v60 )
        goto LABEL_130;
    }
    else if ( *(char *)(v63 + v68) <= -65 )
    {
      goto LABEL_130;
    }
  }
  v126[0] = v66 + v63;
  v126[1] = v70 + 1;
  v119 = 0;
  v117 = (__m128i)xmmword_45B0C8;
  *(__m128i *)v118 = _mm_loadu_si128((const __m128i *)&xmmword_45B0D8);
  memset(&v118[2], 0, 72);
  if ( v71 >= 0x40 )
  {
    v118[2] = v71 >> 6;
    sub_4053D0(&v117, v69, v71 >> 6, v68, &off_52F3C8);
    v69 += v71 & 0xFFFFFFFFFFFFFFC0LL;
    v71 &= 0x3Fu;
  }
  sub_453DAD(&v118[3], v69, v71);
  v119 = v71;
  v102 = v118[10];
  v103 = v71;
  v104 = v120;
  v105 = v121;
  v106 = v122;
  v74 = _mm_load_si128(&v117);
  si128 = _mm_load_si128((const __m128i *)v118);
  v76 = _mm_load_si128((const __m128i *)&v118[4]);
  *(_OWORD *)&v98.m256i_u64[2] = *(_OWORD *)&v118[2];
  v101 = *(_OWORD *)&v118[8];
  v100 = _mm_load_si128((const __m128i *)&v118[6]);
  v99 = v76;
  *(__m128i *)v98.m256i_i8 = si128;
  v97 = v74;
  v77 = (v118[2] << 9) | (8 * (unsigned int)(unsigned __int8)v71);
  v98.m256i_i8[(unsigned __int8)v71 + 24] = 0x80;
  if ( (unsigned __int8)v71 != 0x3FLL )
    sub_453E04((char *)&v98.m256i_u64[3] + (unsigned __int8)v71 + 1, 0LL);
  v78 = _byteswap_uint64(v77);
  if ( ((unsigned __int8)v71 ^ 0x38u) > 7 )
  {
    v102 = v78;
    sub_4053D0(&v97, &v98.m256i_u64[3], 1LL, v72, v73);
  }
  else
  {
    sub_4053D0(&v97, &v98.m256i_u64[3], 1LL, v72, v73);
    v92 = 0LL;
    v91 = 0LL;
    v90 = 0LL;
    v93 = 0LL;
    v94 = v78;
    sub_4053D0(&v97, &v90, 1LL, v79, v80);
  }
  v114 = v97;
  v116 = _mm_load_si128((const __m128i *)&v98);
  v81 = (__m128i *)sub_405370(32LL, 1LL);
  if ( !v81 )
    sub_402910(1LL, 32LL);
  v82 = v81;
  v83 = _mm_load_si128(&v116);
  v84 = _mm_load_si128(&v114);
  *v81 = _mm_packus_epi16(
           _mm_shufflehi_epi16(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v84, (__m128i)0LL), 27), 27),
           _mm_shufflehi_epi16(_mm_shufflelo_epi16(_mm_unpackhi_epi8(v84, (__m128i)0LL), 27), 27));
  v81[1] = _mm_packus_epi16(
             _mm_shufflehi_epi16(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v83, (__m128i)0LL), 27), 27),
             _mm_shufflehi_epi16(_mm_shufflelo_epi16(_mm_unpackhi_epi8(v83, (__m128i)0LL), 27), 27));
  sub_4051A0(&v97, &unk_45B0E8, v81, 32LL);
  sub_405380(v82, 32LL, 1LL);
  v85 = v97.m128i_i64[1];
  if ( v98.m256i_i64[0] == 44
    && !(unsigned int)sub_4539A0(
                        v97.m128i_i64[1],
                        "qQ3CGmaxwxFbcAD1Eruz6NbR0fMqoERDsNKVPMFf2kw=Flag: \nUtf8Errorvalid_up_toerror_lenFromUtf8ErrorbyteserrorNoneSomeusize overflow when calculating b64 length/home/explorer/.cargo/registry/src/mirrors.ustc.edu.cn-4affec411d11e50f/base64-0.22.1/src/encode.rsVec is sized conservativelyinternal error: entered unreachable code: /home/explorer/.cargo/registry/src/mirrors.ustc.edu.cn-4affec411d11e50f/base64-0.22.1/src/engine/mod.rsinteger overflow when calculating buffer sizeInvalid UTF8",
                        44LL) )
  {
    if ( v97.m128i_i64[0] )
      sub_405380(v85, v97.m128i_i64[0], 1LL);
    v117.m128i_i64[0] = (__int64)v126;
    v117.m128i_i64[1] = (__int64)sub_404A80;
    v97.m128i_i64[0] = (__int64)&off_52F3E0;
    v97.m128i_i64[1] = 2LL;
    v98.m256i_i64[0] = (__int64)&v117;
    *(_OWORD *)&v98.m256i_u64[1] = 1uLL;
    result = sub_425450(&v97);
  }
  else
  {
    if ( v97.m128i_i64[0] )
      sub_405380(v85, v97.m128i_i64[0], 1LL);
    v97.m128i_i64[0] = (__int64)&off_52F370;
    v97.m128i_i64[1] = 1LL;
    v98.m256i_i64[0] = 8LL;
    *(_OWORD *)&v98.m256i_u64[1] = 0LL;
    result = sub_425450(&v97);
  }
  if ( v60 )
    result = sub_405380(v63, v60, 1LL);
LABEL_147:
  if ( v109 )
    result = sub_405380(v89, v109, 1LL);
  if ( v111 )
    return sub_405380(v112, v111, 1LL);
  return result;
}
这个是v3 = sub_403860;这个部分函数








__int64 __fastcall sub_423040(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // eax
  void *v11; // rcx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rsi
  __int64 v19; // rax
  __int64 v20; // rbx
  __int128 v24[8]; // [rsp+20h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+A0h] [rbp-50h]
  __int64 v26; // [rsp+B0h] [rbp-40h]
  __int64 v27; // [rsp+B8h] [rbp-38h] BYREF
  char v28[48]; // [rsp+C0h] [rbp-30h] BYREF

  *(_QWORD *)&v24[0] = 0LL;
  *(__int128 *)((char *)v24 + 8) = xmmword_51CA90;
  do
  {
    if ( (unsigned int)sub_4516D7(v24, 3LL, 0LL) != -1 )
    {
      if ( ((BYTE6(v24[0]) & 0x20) == 0 || (unsigned int)sub_44F9C6((unsigned int)"/dev/null", 2, 0, v7, v8, v9) != -1)
        && ((BYTE14(v24[0]) & 0x20) == 0 || (unsigned int)sub_44F9C6((unsigned int)"/dev/null", 2, 0, v7, v8, v9) != -1) )
      {
        if ( (BYTE6(v24[1]) & 0x20) != 0 )
          goto LABEL_20;
        goto LABEL_21;
      }
LABEL_37:
      sub_44F78E();
    }
    v10 = *(_DWORD *)sub_44F780();
  }
  while ( v10 == 4 );
  if ( v10 > 0x16 )
    goto LABEL_37;
  v11 = &loc_401800;
  if ( !_bittest((const int *)&v11, v10)
    || (unsigned int)sub_44F86F(0LL, 1LL) == -1
    && *(_DWORD *)sub_44F780() == 9
    && (unsigned int)sub_44F9C6((unsigned int)"/dev/null", 2, 0, v12, v13, v14) == -1 )
  {
    goto LABEL_37;
  }
  if ( (unsigned int)sub_44F86F(1LL, 1LL) == -1
    && *(_DWORD *)sub_44F780() == 9
    && (unsigned int)sub_44F9C6((unsigned int)"/dev/null", 2, 0, v15, v16, v17) == -1 )
  {
    goto LABEL_37;
  }
  if ( (unsigned int)sub_44F86F(2LL, 1LL) != -1 || *(_DWORD *)sub_44F780() != 9 )
    goto LABEL_21;
LABEL_20:
  if ( (unsigned int)sub_44F9C6((unsigned int)"/dev/null", 2, 0, v7, v8, v9) == -1 )
    goto LABEL_37;
LABEL_21:
  v18 = 1LL;
  switch ( a5 )
  {
    case 0:
      goto LABEL_25;
    case 1:
      byte_5322E1 = 1;
      goto LABEL_26;
    case 2:
      goto LABEL_24;
    case 3:
      v18 = 0LL;
LABEL_24:
      byte_5322E1 = 1;
LABEL_25:
      if ( sub_4519B0(13LL, v18) == -1 )
      {
        *(_QWORD *)&v24[0] = &off_530500;
        *((_QWORD *)&v24[0] + 1) = 1LL;
        *(_QWORD *)&v24[1] = v28;
        *(__int128 *)((char *)&v24[1] + 8) = 0LL;
        v27 = sub_425FF0(v28, v24);
        sub_40B0E0(&v27);
        sub_42B320();
      }
LABEL_26:
      qword_5322D0 = sub_44F391(30LL, v18);
      *(_OWORD *)(__readfsqword(0) - 56) = 0LL;
      v25 = 0LL;
      memset(v24, 0, sizeof(v24));
      v26 = 0LL;
      sub_4518E5(11LL, 0LL, v24);
      if ( !*(_QWORD *)&v24[0] )
      {
        if ( !byte_5322E0 )
        {
          byte_5322E0 = 1;
          qword_5322D8 = sub_42AE50(1LL);
        }
        DWORD2(v25) = 134217732;
        *(_QWORD *)&v24[0] = sub_42AC90;
        sub_4518E5(11LL, v24, 0LL);
      }
      sub_4518E5(7LL, 0LL, v24);
      if ( !*(_QWORD *)&v24[0] )
      {
        if ( !byte_5322E0 )
        {
          byte_5322E0 = 1;
          qword_5322D8 = sub_42AE50(1LL);
        }
        DWORD2(v25) = 134217732;
        *(_QWORD *)&v24[0] = sub_42AC90;
        sub_4518E5(7LL, v24, 0LL);
      }
      qword_5322B0 = a3;
      qword_5322B8 = a4;
      *(_QWORD *)&v24[0] = 0LL;
      v19 = sub_423840(v24);
      sub_423650(v19);
      v20 = (*(int (__fastcall **)(__int64))(a2 + 40))(a1);
      if ( dword_5321E4 != 4 )
      {
        LOBYTE(v27) = 1;
        *(_QWORD *)&v24[0] = &v27;
        sub_401DB0(v24);
      }
      sub_42B990();
      return v20;
    default:
      sub_402AC0(
        "internal error: entered unreachable code/rustc/eeb90cda1969383f56a2637cbd3037bdf598841c/library/alloc/src/vec/mod.rs/rust/deps/gimli-0.29.0/src/read/line.rs/rustc/eeb90cda1969383f56a2637cbd3037bdf598841c/library/core/src/num/wrapping.rs/rust/deps/gimli-0.29.0/src/read/index.rs.debug_abbrev.debug_addr.debug_aranges.debug_cu_index.debug_info.debug_line.debug_line_str.debug_loc.debug_loclists.debug_ranges.debug_rnglists.debug_str.debug_str_offsets.debug_tu_index.debug_types",
        40LL,
        &off_530510);
  }
}
这个部分是sub_423040(&v3, &unk_52F400, a1, a2, 0LL);函数
